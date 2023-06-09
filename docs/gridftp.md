# Setting up GridFTP from Archer2 to Jasmin

The now-recommended method for transferring data between ARCHER2 and JASMIN is using GridFTP using certificate authentication.  This allows data transfers to run on the ARCHER2 serial nodes using certificate-based authentication rather than SSH.  Certificates are valid for up to a month from initiation and can be easily extended/regenerated for longer running simulations.

These instructions show how to setup your GridFTP certificate in order to run the `pptransfer` task on the ARCHER2 serial nodes to push the data across to JASMIN from ARCHER2 `/work` disk. 

**Note:** In order to use GridFTP to JASMIN you must have access to the **hpxfer (High Performance Data Transfer Service)**. Access can be requested via the [JASMIN Accounts Portal](https://accounts.jasmin.ac.uk/).

## Obtaining a JASMIN short-lived credential

* Login to ARCHER2.

* Change directory to your ARCHER2 work directory - `/work/n02/n02/USERNAME`.  

* [First Time Only] "Bootstrap trust" to setup your local certificate store with those needed to interact with the JASMIN server.
~~~
  $ $UMDIR/bin/onlineca-get-trustroots-wget.sh -U https://slcs.jasmin.ac.uk/trustroots/ -b
  Bootstrapping Short-Lived Credential Service root of trust.
  Trust roots have been installed in /home/n02/n02/USERNAME/.globus/certificates.
~~~

* Obtain a short-term credential (this must be called `cred.jasmin`) using your JASMIN accounts portal username USERNAME.
~~~
$ $UMDIR/bin/onlineca-get-cert-wget.sh -U https://slcs.jasmin.ac.uk/certificate/ -l USERNAME -o ./cred.jasmin
~~~
When prompted for a passphrase, this is the password associated with your **JASMIN** account portal account (**NOT your SSH passphrase**)

* Change the permissions on the newly-created `cred.jasmin` file so that it is only readable by you.

  `$ chmod 600 cred.jasmin`

This credential is valid, by default, for 30days.  You can see the validity period by inspecting the certificate using the following command:
~~~
$ openssl x509 -in cred.jasmin -noout -startdate -enddate
notBefore=Mar 11 17:32:59 2022 GMT
notAfter=Apr 10 17:32:59 2022 GMT
~~~

This means you can use this certificate for the following 30days, after which you will need to repeat this step to obtain a new one.

A fuller explanation of the process is given in the document [Data Transfer Tools: GridFTP (certificate-based authentication)](https://help.jasmin.ac.uk/article/3808-data-transfer-tools-gridftp-cert-based-auth)
