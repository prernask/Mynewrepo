testing purpose


```
sudo yum install git
```

Connecting to EC2, Installing Git, Cloning a Repo, and Running Python Script

This guide details the commands and steps you followed when:

SSH into an AWS EC2 instance

Installing Git

Cloning your GitHub repository

Running a Python script

1. SSH into EC2 Instance
ssh -i Desktop/awskey/110-pem ec2-user@3.110.134.232


You used a private key (110-pem) for authentication.

The first time you connect, SSH warns you that the host is unknown and asks if you want to continue.

You accepted by typing yes, and the host key was permanently saved.

2. Update System & Install Git

Once inside the EC2 instance:

sudo yum update -y


This ensures system packages are up to date.

In your case, the system responded “Nothing to do.”, meaning it was already up to date.

Check Git:

git --version


Output: -bash: git: command not found

Git was not installed initially.

Install Git:

sudo yum install git


This will fetch Git and its dependencies.

You confirmed the installation by typing y when prompted.

After installation completed:

git --version


Now showed: git version 2.50.1

3. Configure Git User Identity

Set your name and email so commits you make are properly attributed:

git config --global user.name "Prerana Karande"
git config --global user.email "karandeprerna@gmail.com"


Verify settings:

git config --list


Output showed your name and email:

user.name=Prerana Karande
user.email=karandeprerna@gmail.com

4. Clone GitHub Repository

Clone your repo:

git clone https://github.com/prernask/Mynewrepo.git


This created a folder named Mynewrepo containing the repository’s files.

Enter it:

cd Mynewrepo


List the files:

ls


You saw: LICENSE, README.md, helloworld.py

5. Running the Python Script

First check Python version:

python --version


It returned “command not found” (Python not mapped to python alias).

Check Python3:

python3 --version


Output: Python 3.9.23

Run the script:

python3 helloworld.py


Output: hello world!

View file contents:

cat helloworld.py


Contents are:

print("hello world!")

Summary & Notes

You successfully connected via SSH to your EC2 instance.

You updated the system (though nothing changed) and installed Git.

You configured Git with your name/email.

You cloned a GitHub repository.

You ran a Python script successfully that prints “hello world!”.

