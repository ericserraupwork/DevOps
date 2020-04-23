# DevOps with jenkins

### Overview
Jenkins is a free and open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery
### Install
+ command to install
    + `wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -`
    + `sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`
    + `sudo apt update`
    + `sudo apt install jenkins`
    + `sudo usermod -aG docker jenkins`
    + if you got error - `Failed to start LSB: Start Jenkins at boot time`
        + `sudo apt install openjdk-8-jdk`
    + `sudo service jenkins start`
    + `sudo systemctl enable jenkins`
    
+ use below reference to install jenkins
    + `https://www.linode.com/docs/development/ci/automate-builds-with-jenkins-on-ubuntu/`
    + `https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-18-04`
    + `https://bobcares.com/blog/failed-to-start-lsb-start-jenkins-at-boot-time/`

### Set up Jenkins
+ Use your browser to navigate to default server address
    + `http://<LINODE_IP_OR_HOSTNAME>:8080`
+ Copy the temporary administrator password and use it to log in
    + `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
+ Choose Install suggested plugins to start downloading the standard plugins
![Relevance feedback image](https://github.com/ericserraupwork/DevOps/blob/master/screenshots/j2.PNG)
+ When the plugin installation finishes, you will be asked to create a new administrative user
+ Click on Start using Jenkins to display the application dashboard
+ As mentioned earlier, this guide will use the new Blue Ocean interface, so you will need to click the Manage Jenkins link on the sidebar

+ reference
    + `https://www.linode.com/docs/development/ci/automate-builds-with-jenkins-on-ubuntu/`
        
           