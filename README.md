 we can automate the continuous delivery process by writing pipeline script in Jenkins to upload the artifacts into Sonatype Nexus repository.
We will see step by step process starting from Nexus Installation, repository creation, etc..

Binary file management is most important in software development.
There are multiple repository system available in the market to store the Artifacts or, the Binary files.

Sonatype Nexus Installation:

Step1: Java8 Installation
sudo yum install java-1.8.0-openjdk.x86_64 -y

Step2: Install Nexus
cd /opt
sudo wget https://sonatype-download.global.ssl....
sudo tar -zxvf nexus-3.0.2-02-unix.tar.gz
sudo mv nexus-3.0.2-02 nexus

sudo adduser nexus
sudo passwd nexus

sudo chown -R nexus:nexus /opt/nexus

sudo vi /opt/nexus/bin/nexus.rc
run_as_user="nexus"

sudo ln -s /opt/nexus/bin/nexus /etc/init.d/nexus

su - nexus

service nexus start

Default login:
user: admin
password: admin123

In jenkins dashboard in global credential we need to give the usename and password and need to generate the Id that Id needs to upload in pipeline
Plugins 2 plugins need to upload
1.Nexus artifact
2.pipeline utility.
