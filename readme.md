Tasks:
Create a Jenkins pipeline which will be triggered using Git when push will happen on Develop branch.
Pipeline will pull the content to a folder.
Create 2 nodes for two different jobs. -->1. push to test -->2. Push to prod.
Once push made to test, copy git files to test server.
Once push made to prod, copy git files to prod server.
Create a pipeline in Jenkinsto:
Once push is made to develop branch, trigger job test. This will copy git files to test node.
If test job is successful, prod job should be triggered and copy files to prod node.

===> SOLUTIONS <===

==Requirement==
1. AWS account
2. GitHub account

Step --> Create GitHub repository then clone repository to local system. Create develop branch and add some file to commit and push on GitHub.

(Create a file on master before making any push to develop to make other branch eligible to make push)

Step --> Launch an instance and connect it then install Jenkins and java.
Commands:

  sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
  echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
  sudo apt-get update
  sudo apt-get install Jenkins
  sudo apt install openjdk-17-jdk -y

Step --> Connect Jenkins using instance public IP (e.g- instance-IP:8080)

Step --> Create two instance (test and prod node), connect update and install java.

	Sudo apt update -y
	Sudo apt install openjdk-17-jdk -y

Step --> Add both instances on Jenkins as test and prod node.

Step --> Create a webhook so that jobs would be triggered by GitHub.

Step --> Create freestyle test and prod jobs on jenkins.

Step --> Create a new file or update existing file on develop then commit and push to develop branch.

Verify jobs on jenkins.
