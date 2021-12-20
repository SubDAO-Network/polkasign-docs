The Polkasign project consists of three parts, namely the front-end, the query back-end, and the ink! contract. The front-end is the main part of user interaction. The query back-end provide query requirements of contract data. The main function of the ink! contract is for the user to deposit the agreement and verify the signature on the chain.

## Substrate chain and browser

Polkasign uses SubDAO's test chain for testing and development, and could deployed to any parachain or public chain that supports ink! contracts. Currently SubDAO has a corresponding test chain. 

Browser address: [http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/contracts](http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/contracts) 

Chain ws address: ws://43.133.174.232:9944

## Ink! contracts

repo: [https://github.com/remote-freeman/polkasign-contract](https://github.com/remote-freeman/polkasign-contract) 

The contract mainly includes the contract metadata saving, signature data verifying and saving, contract master file saving, and other information handle, maintaining the entire process of signing a contract, and verifying the signatures submitted by users to ensure the validity of contract signing.

### Compile

Install the compilation tool cargo-contract, which must be version 0.11.

```plain
cargo install cargo-contract --vers ^0.11 --force --locked
```
Then directly execute the command in the project root directory, and the compilation result is in the release directory. The .contract file is used to deploy the contract in the substrate chain, and the .json file is the abi file of the contract.
```plain
bash ./build.sh
```

### Deploy Contract

Open the SubDAO browser, [http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/contracts,](http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/contracts,) enter Developer->Contracts, click upload & deploy code, select the previous step The generated polkasign.contract file.


Enter Next, input the owner of the contract, and endowment a certain number of tokens.


Click Deploy, after signing and submitting, wait until the chain result. If you see the contracts.Instantiated event, it means that the contract is successfully deployed and you can see the newly deployed contract in the browser.



Expand the messages to test the contract, and view the address of the contract for subsequent configuration.

## Query backend

repo: [https://github.com/remote-freeman/polkasign-backend](https://github.com/remote-freeman/polkasign-backend)

It is mainly used to monitor the contract generated info, like the contract and the submitted signature, contract document description, and other information, then used to on the front-end of Polkasign.

### Modify Config

The ws port of the link and the contract address need to be modified before deployment. Modify in the file subscriber/subscribe.js:

```plain
// replace substrate ws endpoint
const ws_endpoint = "43.133.174.232:9944";
// replace the previous deployed contract address
const polkasign_address = "xxxxxxx";
```

### Compile

Execute in the project root directory:

```plain
go build -o server ./server.go
```
Install npm dependencies:
```plain
cd subscriber
nvm install 14.16.0
nvm use 14.16.0
npm install -g yarn
yarn
```

### Deploy

Deploying the query backend consists of two parts, one is the GraphQL server, and the other is the contract monitoring. 

Start the GraphQL server:

```plain
nohup ./server &
```
The default listening port is 8080.
Start the contract monitoring module:

```plain
cd subscriber
nohup node subscribe.js &
```
Check the corresponding nohup.out log file to confirm that the service started successfully. At the same time, you can open the page [http://127.0.0.1:8080/](http://127.0.0.1:8080/) to perform a simple query test.


## Front-end

repo: [https://github.com/remote-freeman/subdao-polkasign](https://github.com/remote-freeman/subdao-polkasign)

Users use polkasign products through the front-end, including uploading contract documents, signing contracts, uploading handwritten information, etc., and interacting with the on-chain ink! contract and querying the back-end.

### Modify Config

It is necessary to modify the chain ws port of the front-end link and the interactive contract address before compiling. 

Modify the corresponding position in the file src/config/constants.ts:

```plain
export default {
  sign: {
    // replace the previous deployed contract address
    5: '5GfegVT1wheGfz87UZWxxLJvW9KynN9qzqfvYxaerjwa2P1j'
  }
}
// replace substrate ws endpoint
export const ws_endpoint = 'ws://43.133.174.232:9944'
```

### Compile

Enter the main directory of the project and execute

```plain
nvm install 14.16.0
nvm use 14.16.0
yarn
yarn build
```

### Deploy

The compiled output is in the out directory. We need to deploy the front-end in ngnix, open the nginx configuration file to increase the front-end file proxy.

>Open the /etc/nginx/sites-enabled/default file in Linux and add the following configuration.
>Open the /usr/local/etc/nginx/nginx.conf file in the mac and add the following configuration.
```plain
server {
        listen 3000 default_server;
        # the compile out dir path, like /home/work/out
        root /home/work/out;
 
        location / {
                root /home/work/out;
        }
        # point to your query back-end addr
        location /query {
                proxy_pass http://localhost:8080/query;
        }
}
```
Use a browser to open [http://127.0.0.1:3000,](http://127.0.0.1:3000,) you can start using polkasign.
