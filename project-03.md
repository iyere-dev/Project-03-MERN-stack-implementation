# MERN STACK IMPLEMENTATION

## A SIMPLE TO_DO APPLICATION

BACKEND CONFIGURATION

`sudo apt update`

![updating packages](./images/backend_configuration/)

`sudo apt upgrade`

![upgrading packages](./images/backend_configuration/upgrading_packages_page1.png)

![upgrading packages](./images/backend_configuration/upgrading_packages_page2.png)

get the location of Node.js software from Ubuntu repositories

`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

![getting location of nodejs software](./images/backend_configuration/getiing_locatio_of_nodejs_software.png)

install nodejs on the server

`sudo apt-get install -y nodejs`

The command above installs both nodejs and npm. NPM is a package manager for Node like apt for Ubuntu, it is used to install Node modules & packages and to manage dependency conflicts

![installing nodejs](./images/backend_configuration/installing_node_js.png)

verify node installation

`node -v`

![verifying node installation](./images/backend_configuration/verifying_node_installation.png)

verify node installation

`npm -v`

![verifying node installation NPM](./images/backend_configuration/verifying_node_installation_NPM.png)

Application Code Setup
Create a new directory for your To-Do project:

`mkdir Todo`

![creating new directory for T0-Do project](./images/backend_configuration/creating_new_directory_Todo.png)

verify Todo directory has been created

`ls`

![verifying Todo directory creation](./images/backend_configuration/verifying_Todo_directory_creation.png)

change directory to Todo directory

`cd Todo`

![changing to Todo directory](./images/backend_configuration/changing_to_Todo_directory.png)

Next, you will use the command npm init to initialise your project, so that a new file named package.json will be created. This file will normally contain information about your application and the dependencies that it needs to run. Follow the prompts after running the command. You can press Enter several times to accept default values, then accept to write out the package.json file by typing yes.

`npm init`

![initialising project](./images/backend_configuration/initialising_project.png)

Run the command ls to confirm that you have package.json file created

`ls`

![confirming package.json file has been created](./images/backend_configuration/confirming_creation%20_of_package.json_file.png)



### INSTALL expressjs

Remember that Express is a framework for Node.js, therefore a lot of things developers would have programmed is already taken care of out of the box. Therefore it simplifies development, and abstracts a lot of low level details. For example, Express helps to define routes of your application based on HTTP methods and URLs.

`npm install express`

![installing express](./images/install_expressjs/install_express.png)

create index.js file

`touch index.js`

`ls`

![comfirming index.js file has been created](./images/install_expressjs/confirming_creation_of_index.js.png)

install the dotenv module

`npm install dotenv`

![installing the dotenv module](./images/install_expressjs/installing_dotenv_module.png)

open index.js file and paste barebones configuration below 


const express = require('express');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

app.use((req, res, next) => {
res.header("Access-Control-Allow-Origin", "\*");
res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
next();
});

app.use((req, res, next) => {
res.send('Welcome to Express');
});

app.listen(port, () => {
console.log(`Server running on port ${port}`)
});


`vim index.js`

![pasting configuration in index.js file](./images/install_expressjs/pasting_configuration.png)

start server to see if it works

`node index.js`

![confirming server has started](./images/install_expressjs/starting_server.png)

