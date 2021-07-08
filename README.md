# Easy-Install-ERPNext-13
Step wise installation guide for ERPNext.

### 1) Login to the console, initially as a root user.
### 2) `sudo adduser your-username` //command to add new user
###      For example: `sudo adduser user1` 
#####                           - set the password for new user
#####                           - enter the information asked
### 3) `sudo usermod -aG sudo your-username` // to add new user to the sudoers list
### 4) Then logout of the system and log back in as the new user using `su - your-username`
### 5) `sudo apt update && sudo apt upgrade -y` // to update and upgrade the packages
### 6) Run Command `export LC_ALL=C.UTF-8`
### 7) `wget https://raw.githubusercontent.com/frappe/bench/develop/install.py` //to download file
### 8) `python3 install.py --verbose --production --user your-username --frappe-branch version-13 --erpnext-branch version-13` // to install file
####                              -enter mysql password
####                              -enter administrator password
### 9)After successful installation go to the assigned IP Address and login through the `Administrator` Id and the admin password given at the time of installation. 
