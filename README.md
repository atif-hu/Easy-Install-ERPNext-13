# Easy-Install-ERPNext-13
Step wise installation guide for ERPNext.

#### 1) Login to the console through ssh to a server `ssh root@[IP]`, initially as a root user.
#### 2) `sudo adduser your-username` //command to add new user
#####      *For example: "sudo adduser `user1`"*
- set the password for new user
- enter the information asked
#### 3) `sudo usermod -aG sudo your-username` // to add new user to the sudoers list
#####      *For example: "sudo usermod -aG sudo `user1`"*

#### 4) Then logout of the system using `exit` and login again as a root user.
#### 5) `sudo apt update && sudo apt upgrade -y` // to update and upgrade the packages
#### 6) Run Command `export LC_ALL=C.UTF-8`
#### 7) `wget https://raw.githubusercontent.com/frappe/bench/develop/install.py` //to download file
#### 8) `python3 install.py --verbose --production --user your-username --frappe-branch version-13 --erpnext-branch version-13` // to install file
- enter mysql password
- enter administrator password
#### 9) After successful installation go to the assigned IP Address and login through the `Administrator` Id and the admin password given at the time of installation.

___


# How to give user root privileges?

#### 1) Login to the console through ssh to a server `ssh root@[IP]`, as a root user.
#### 2) Ensure `user` has sudo access using `sudo visudo` command.
- The following sudoers file will popup- ![Screenshot (63)](https://user-images.githubusercontent.com/67437879/125202270-77eb2800-e290-11eb-9f60-25a519d3b38b.png)
- Under the section `# Allow members of group sudo to execute any command` add `%your-username ALL=(ALL:ALL) NOPASSWD:ALL` to get sudo access.
#### 3) Login with your user-name using `su your-username`
#### 4) Generate SSH key using `ssh-keygen`
- Enter the default file to save the key and you can keep passphrase empty
#### 5) Copy `authorize_keys` from `root` user to `your-username` ssh directory `/home/ubuntu/.ssh` using `sudo cp /root/.ssh/authorized_keys /home/your-username/.ssh/authorized_keys`
#### 6) Make everything in .ssh owned by your user: 
- `sudo chown -R your-username:your-username /home/your-username/.ssh`
#### 7) Change permission 644 and make it readable only by your user:
- `sudo chmod 644 /home/your-username/.ssh/authorized_keys`

        
