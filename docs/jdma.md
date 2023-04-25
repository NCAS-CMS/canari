# Migration of UM Data to JASMIN Elastic Tape

Instructions on how to setup your environment for migration of data to JASMIN Elastic Tape as part of the UM workflow. 

## Setup and initialise JDMA on JASMIN

Before you can use the JDMA to migrate data to Elastic Tape you must install the jdma client on JASMIN and initialise some user settings.
 
1. Install JDMA client software:
    * Login to a JASMIN sci machine
    * Load python2:  
      `module load jaspy/2.7`
    * Create a virtual environment in your home directory:  
      `virtualenv ~/jdma_venv_py2`
    * Activate the virtual environment:  
      `source ~/jdma_venv_py2/bin/activate`
    * Install the jdma client into the virtualenv:  
      `pip install git+https://github.com/cedadev/jdma_client`

2. Follow instructions in the [Setting up the user, user settings and user info](https://cedadev.github.io/jdma_client/docs/build/html/jdma_client/tutorial.html#setting-up-the-user-user-settings-and-user-info) section of the JDMA Tutorial.

### Setup connection to JASMIN sci nodes

You need to configure your ssh settings to connect to the Jasmin sci nodes, in order to submit the JDMA requests. 

1. Add the following to your `~/.ssh/config` file on PUMA:
~~~
# JASMIN
Host login1
Hostname login1.jasmin.ac.uk
User <jasmin_username> 
IdentityFile ~/.ssh/<jasmin-ssh-key>
ForwardAgent yes
ControlMaster auto
ControlPath /tmp/ssh-socket-%r@%h-%p
ControlPersist yes

Host sci? cylc1
Hostname %h.jasmin.ac.uk

Host sci* cylc*
User <jasmin_username>
IdentityFile ~/.ssh/<jasmin-ssh-key>
ForwardAgent yes
ProxyCommand ssh -Y login1 -W %h:%p
ControlMaster auto
ControlPath /tmp/ssh-socket-%r@%h-%p
ControlPersist yes
~~~

2. Add your JASMIN ssh-key to your ssh-agent:
    * `ssh-add ~/.ssh/<jasmin-ssh-key>`

3. Test connection to JASMIN:
    *  `ssh sci3.jasmin.ac.uk`
    * You should be logged into the JASMIN sci node without prompt for your JASMIN passphrase.

4. Add path to Rose/Cylc to your `~/.bash_profile` on JASMIN:
~~~
if [[ $(hostname) = sci*.jasmin.ac.uk || $(hostname) = cylc*.jasmin.ac.uk ]]; then
  # Rose/cylc on jasmin-sci & Lotus nodes
  export PATH=/apps/jasmin/metomi/bin:$PATH
fi
~~~

