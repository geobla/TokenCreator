# TokenCreator
How to install truffle &amp; ganache on Linux and create a crypto token.


## Dependencies

1. [Node.js](https://nodejs.org/en/) (Best option to be installed using nvm).
2. Python (Is already installed on Linux).
3. [pyenv](https://github.com/pyenv/pyenv) (If you want to run different python versions)
4. [Ganache](https://trufflesuite.com/ganache/) Download the app image and make it executable.
5. [node-gyp](https://github.com/nodejs/node-gyp) (We will use it to install some node dependencies.)

```bash
npm install -g node-gyp
```
6. [Truffle](https://trufflesuite.com/) (Create, compile, test and run smart contracts)
```bash
npm install -g truffle
```
Check if it is correctly installed:
```bash
npx truffle
``` 
7. [React](https://github.com/facebook/create-react-app) If you've previously installed 
```create-react-app``` globally via ```npm install -g create-react-app```, we recommend 
you uninstall the package using ```npm uninstall -g create-react-app``` or ```yarn global 
remove create-react-app``` to ensure that npx always uses the latest version.\
To run a react app:
```bash
npx create-react-app <name-of-your-app>
```
```bash
cd <name-of-your-app>
```
```bash
npm start
```
8. [Git](https://git-scm.com/) (Check if installed, else install.)
9. Metamask (Find your browser's specific extension).
10. Redux Devtools (Find your browser's specific extension).    
11. [Infura](https://infura.io/) (Set up an account).
12. [Heroku](https://heroku.com/) (Set up an account).

## Create a project

1. We start by creating a react app:
```bash
create-react-app <your-preffered-app-name>
```
2. Go to the new react directory:
```bash
cd <your-react-name-you-just-created>
```
3. Open your IDE (VS Code, or any other) inside this directory.
You will see that react created a bunch of directories and files.
![This is an image](/assets/images/pic1.png)

4. To check if React opens correctly, open the Terminal 
inside the React's directory and run:
```bash
npm run start
```
This will start a local web server on port 3000, and a new window 
will open in your browser with the React logo on it.
![This is an image](/assets/images/pic2.png)

5. ```app.js``` (inside ```/src``` directory) is the file where we can manipulate
the front end of the webpage. Like ```index.html``` .

## Add dependencies for this project.

The dependencies that we are going to install will be added inside the 
```package.json``` file, that is already installed by React.

So inside the React app directory run:
```bash
npm i @truffle/hdwallet-provider 
```
```bash
npm i apexcharts babel-polyfill 
```
```bash
npm i babel-preset-env 
```
```bash
npm i babel-preset-es2015 
```
```bash
npm i babel-preset-stage-2 
```
```bash
npm i babel-preset-stage-3 
```
```bash
npm i babel-register 
```
```bash
npm i bootstrap 
```
```bash
npm i chai 
```
```bash
npm i chai-as-promised 
```
```bash
npm i chai-bignumber 
```
```bash
npm i dotenv 
```
```bash
npm i lodash 
```
```bash
npm i moment 
```
```bash
npm i openzeppelin-solidity 
```  
```bash
npm i react-apexcharts 
```
```bash
npm i react-bootstrap 
```
```bash
npm i react-redux 
```
```bash
npm i redux 
```
```bash
npm i redux-logger 
```
```bash
npm i reselect 
```
```bash
npm i solidity-coverage
```
```bash
npm i truffle
```
```bash
npm i truffle-flattener
```
```bash
npm i truffle-hdwallet-provider-privkey
```
```bash
npm i web3
```
This will install the latest versions of the above needed dependencies
inside the ```node_modules``` directory.

The changes can be seen if you check the ```package.json``` file, before
and after.

You should by now have a ```package-lock.json``` file created, which contains
all the dependencies that node should run.

## Create a truffle project.

1. Check that you are inside the React app directory and open Terminal there. 
2. Run:
```bash
truffle init
```
This will create some new files and directories, like a ```contracts``` directory, which
contains a ```Migrations.sol``` file, which is an Ethereum smart contract.
![This is an image](/assets/images/pic3.png)
This contract is responsible for publishing all our smart contracts to the blockchain.

Move the `contracts` directory inside the `src` directory.

It also created a ```truffle-config.js``` file, which contains all the truffle configurations.
![This is an image](/assets/images/pic4.png)
To save you a lot of headache, copy my ```truffle-config.js``` and replace it with yours.


It also created a ```test``` directory where we can run tests for the smart contracts.

## Use JavaScript ES6 as default with truffle.

Because of the need to use javascript async functions, we must config truffle to use ES6
as default.

To config truffle for this, we must create a ```.babelrc``` file (always inside the working directory).

So from IDE, create this file, or just download and import mine. (Don't forget to add a dot (.) before the file name.


## Create a .env file.

We will need a ```.env``` file to keep our credentials (like MetaMask login info, etc).

Create one with your IDE and **DON'T FORGET** to add it, to the ```.gitignore``` file. 






