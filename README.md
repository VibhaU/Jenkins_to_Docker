# Jenkinsfile_to_run_Docker_Container
Setting a Jenkins pipeline to run Docker application
On EC2 instance, install jdk by using following cmd
apt install openjdk-17-jdk

------------------------------------------------------------------
# Install packages jenkin key:

------------------------------------------------

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/" | \
  sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

-----------------------------------------------------------
sudo apt install Jenkins -y

# [Note: to run the Jenkins we need to add jdk package, below is the cmd]

apt install openjdk-17-jdk

systemctl start Jenkins

systemctl enable jenkins

systemctl status Jenkins

-----------------------------------------------

# To install docker

apt install docker.io -y

------------------------------------------

# Installing webserver which is nginx

apt install nginx -y

-----------------------------------

cat /var/lib/jenkins/secrets/initialAdminPassword

--------------------------------------------
# Permission for user
chown -R jenkins:jenkins /var/www/html

-------------------------------------------------------- 
# Adding Webhook

http://[public ip]/job/Docker_and_jenkins/

with Jenkins pipeline replace above "job" with below cmd

http://[public ip]/github-webhook/

--------------------------------------------
