# TokenCreator
How to install truffle &amp; ganache on Linux and create a crypto token.

## Table Of Contents
1. [Dependencies](#dependencies)
2. [Add dependencies for this project](#add-dependencies-for-this-project)
3. [Create a Truffle Project](#create-a-truffle-project)
4. [Use JavaScript ES6 as default with Truffle](#use-javascript-es6-as-default-with-truffle)
5. [Create an .env file](#create-a-env-file)
6. [Create your Token](#create-your-token)
7. [Compile the Token.sol contract](#compile-the-tokensol-contract)
8. [Deploy the Token to the BlockChain](#deploy-the-token-to-the-blockchain-ganache-for-now)

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


## Create your Token

Inside the `./contracts/` directory we will create our Token smart contract, 
next to the `Migrations.sol` contract.

With the help of your IDE, create the `Token.sol` contract.

1. First we create a very basic structure for the token contract, just to test that
everything is working properly.

Most of the code will be taken fom the [ethereum ERC20 standard.](https://github.com/ethereum/eips/issues/20)

We can start with this code:
```solidity
// SPDX-License-Identifier: MIT
pragma solidity >=0.4.22 <0.9.0;

contract Token {
    string public name = "Harmonius";
}
```

2. Once we are done with our basic code, we open the **Ganache** app and select **QuickStart**.

Ganache provides us with a personal blockchain, with 10 free eth accounts, each funded with 100 ETH. 
![This is an image](/assets/images/pic5.png)

At the top (RPC SERVER), you can see that it provides us with the local **IP** and **PORT**. **(127.0.0.1:7545)** 
This is the port that will connect us to its node.

Those settings must be imported in the `truffle-config.js` file. But if you copied my folder, you have them already 
configuerd.

## Compile the `Token.sol` contract.

In your terminal (always check that you are in the right directory) run:
```bash
truffle compile
```
Now if you check the `./src/abis/` directory you will see that 2 new json files are created, `Migrations.json`
and `Token.json`.

Those are the files that contain the **ABI** and **ByteCode** of the contracts we asked to compile.

## Deploy the Token to the blockchain (Ganache for now).

To deploy our token to the blockchain we need the **Migrations** script, which we already have.

But it needs some changes, because now it has a generic code.

The `migrations` contracts help us change the blockcain state.

So whenever we create a new smart contract or whenever we make an exchange, we are actually
changing its state.

Don't confuse the `./src/contracts/Migrations.sol` file with the `/migrations/1_initial_migration.js` file.

It is the second directory that we need now.

They are **numbered** for a reason. Truffle needs to know in which **order to run** them.

1. Inside the `migrations` directory, create a a js file named `2_deploy_contracts.js`.

2. Copy the code from the `1_initial_migration.js` to the `2_deploy_contracts.js`.

3. Wherever it says the word `Migrations` change it with the word `Token`. 

Your code should now look like this:
```javascript
const Token = artifacts.require("Token");

module.exports = function (deployer) {
  deployer.deploy(Token);
};
``` 
Doing this change, we are telling truffle to search for info, in the `./src/abis/Token.json/` file.

4. Now in terminal run:
```bash
truffle migrate
``` 
In the terminal you will see that both js files where deployed, and a buch of info, like **transaction
hash, gas used, total cost**, etc. ![This is an image](/assets/images/pic6.png)

Also if we check the ganache app, we will see that the first address has less ETH now, because it was
used for the transaction. 
![This is an image](/assets/images/pic7.png)

Truffle always uses the first account to deploy contracts.

We can see that the block state has changed. We have 4 new blocks created. ![This is an image](/assets/images/pic8.png)  

And we also have 4 transactions. ![This is an image](/assets/images/pic9.png)

If you go inside one of them by selecting it, you get more info, like in etherscan.


## Truffle console.

You can acces the truffle console by running this command in terminal:
```bash
truffle console
```
You will see `truffle(development)>` is now showing up
<pic10>

This way you can interact with your contracts.

If we want to fetch our Token smart contract that we just deployed we run:
```bash
const token = await Token.deployed(); 
```
- `Token` = name of `const` that we defined inside the `/migrations/2_deploy_contracts.js` file.
- `deployed` = Fetches a deployed copy. 
- `await` = (ES6 JS). Every time we fetch data from the blockchain it will be asynchronous. We have to wait for the result to come back.

More info about async js, can be found in js promises lessons.

Once you run the command you will see that it outputs `undefind`.

Don't be scared. There is no error. Just run the `const` name we asigned to it. In our case:
```bash
token
```
Now you will see a lot of info about the specific contract.
<gif1>  













