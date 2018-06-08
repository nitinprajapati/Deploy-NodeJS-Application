# Deploy-NodeJS-Application
  How to deploy NodeJS application as a service in Linux step by step.
  Here are the steps by which you can deploy Nodejs application by installing Nodejs as a service run in background. Whenever you start   your server NodeJS service will start automatically.

## Getting Started

### Install Node.js Server in Linux

  sudo apt-get install curl python-software-properties
  curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -(Replace 8.x to another version if want to change)
  sudo apt-get install nodejs

### Verify Node.js installed successfully
  sudo node -v (will return the Node.js version)

### Deploy Nodejs package
  Create folder in /var/nodejscode/Package and copy all code inside it(Or you can also change the code directory)
  sudo chmod 777 /var/nodejscode/Package (Giving read write permission if application needed)
  
### Configure NodejsDeploymenScript.sh sheel script
  YourApplicationName: Change it to you application name
  Server'sUserName: Change it to your server user name
  Select your environment type: Select your environment(Commanly used Production & Development)
  Port: Server port on which you want to run your nodejs server
  Application directory: Your application directory(/var/nodejscode/Package)
  App starting point: You starting script name(Bin/www)
  
  
### Install Nodejs as a service
  sudo cp /var/nodejscode/Package/NodejsDeploymenScript.sh /etc/init.d/NodeService  (Assuming downloaded file reside in the mentioned location)
  sudo chmod a+x /etc/init.d/NodeService
  sudo update-rc.d NodeService defaults
  
### Check installed service
  sudo service NodeService start
  sudo service NodeService stop
  sudo service NodeService restart
 
## Authors

* **Nitin Kumar** - *Initial work* - [Nitin Kumar](https://github.com/nitinprajapati)
