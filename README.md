# Ansible with ec2
### Prerequisites:
* Ubuntu 18.04


* AWS access credentials


* Python 3
  * pip3
  * boto
  * boto3
  * awscli
    

* Ansible


### Installation Instructions:  
1. Perform a simple update and upgrade.  
    1. `sudo apt-get update -y`
    2. `sudo apt-get upgrade -y`
    

2. Install Python3 and pip3.  
    1. `sudo apt-get install python3`
    2. `sudo apt-get install python3-pip`
    

3. Install required python modules.
    1. `pip3 install boto boto3`
    2. `pip3 install awscli`
    

4. Install Ansible.
   1. `sudo apt-get update -y`
   2. `sudo apt-get install software-properties-common -y`
   3. `sudo apt-add-repository ppa:ansible/ansible`
   4. `sudo apt-get update -y`
   5. `sudo apt-get install ansible -y`
    

### How to set up ansible:
1. Everything we will need to access is in `/etc/ansible`
    1. `cd /etc/ansible`


2. First fix the hosts file to use python3.
    1. `sudo nano hosts`
    2. At any point in the file you should add this: 
       ```
       [local]
       localhost ansible_python_interpreter=/usr/bin/python3
       ```
    

3. Now we have to setup the ansible vault.
    1. `sudo mkdir group_vars`
    2. `cd group_vars`
    3. `sudo ansible-vault create pass.yml` - create this with a password you remember
    4. You are now in a text editor, this part is complicated.
    

4. Entering the information.
    1. You should now press `i` once, this puts you into insert mode.
    2. You are now free to type in your aws credentials in the following format.
        ```
        aws_access_key = YOUR_KEY_HERE
        aws_secret_ket = YOUR_SECRET_HERE
        ```
    3. Once that is done you should press `esc`, you are now in command mode.
        1. Enter `:wq`, you should see it at the bottom left.
        2. now press enter and you should be done!
    

5. 