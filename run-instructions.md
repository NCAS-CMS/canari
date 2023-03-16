# Running a member of the CANARI Large Ensemble.

Thank you for running a member of the CANARI Large Ensemble! Please follow these steps:

## 1. Prerequisites
These things need to be sorted out before you can start your run:
### 1.1 Environment
Your access to, and communication and data transfer between
1. Archer2
2. Puma, including the Met Office Science Repository Service
3. JASMIN, including CANARI group workspace and Elastic Tape

### 1.2 Specific information about your ensemble member
You will have been provided with the settings that apply for the member of the Large Ensemble (LE) you are running.
These settings are valid for this member specifically, please ask for help if you are unsure about them. They include:
- the name and location of the restart files

## 2. Make a copy of the CANARI LE master suite
1. Log on to puma.
2. Take a copy of u-cn134:
   - Run `rosie go`
   - Search u-cn134 in the search field on the top right
   - Right-click the suite and click Copy Suite
   - Accept the New suite project (Coupled Climate) in the follow on window
   - Also accept the settings in the next window (project, title, etc.)
   - Make a record of the ID of the newly created suite. It is u-cv465 for the purpose of these instructions.
   - Exit the `rosie go` application. 

![copy-suite](https://user-images.githubusercontent.com/74788610/225705405-d097ebc6-0d00-4be2-b8fa-73fa2f906167.png)
![u-cv465](https://user-images.githubusercontent.com/74788610/225708842-ab944bab-ed2d-4e4b-8537-2886bfe7f428.png)

## 3. Edit your CANARI LE suite
