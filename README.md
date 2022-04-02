# simple-jenkins-cicd
Simple Hello World Web Application Deploy Through CI/CD Pipeline

Requirement for this project
1.Setup Jenkins on AWS Platform
https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/

2.Setup Git on Jenkins Server
yum install git -y

3.Download Apache Maven 3.8.5 on Jenkins Server
sudo su
cd /opt
wget https://dlcdn.apache.org/maven/maven-3/3.8.5/binaries/apache-maven-3.8.5-bin.tar.gz
tar -xvzf apache-maven-3.8.5-bin.tar.gz
mv apache-maven-3.8.5 maven
cd mavan/bin
cd ~

#edit the bash profile and check the path of jvm and append into the file
#check jvm path
find / -name java-11*

#your .bash_profile should same as mine
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi
M2_HOME=/opt/maven
M2=/opt/maven/bin
JAVA_HOME=/usr/lib/jvm/java-11-openjdk-11.0.13.0.8-1.amzn2.0.3.x86_64
# User specific environment and startup programs

PATH=$PATH:$HOME/bin:$JAVA_HOME:$M2_HOME:$M2

export PATH

#To check the setup is correct for maven
source .bash_profile
echo $PATH

#output example 
/sbin:/bin:/usr/sbin:/usr/bin:/root/bin:/usr/lib/jvm/java-11-openjdk-11.0.13.0.8-1.amzn2.0.3.x86_64:/opt/maven:/opt/maven/bin


4.Navigate to jenkins console in global tool configuration and add the jdk installation
Select add jdk and add below java path
/usr/lib/jvm/java-11-openjdk-11.0.13.0.8-1.amzn2.0.3.x86_64


5. Add maven installation in jenkins console
Select add maven and add below maven path
/opt/maven