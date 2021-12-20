# PolkaSign Usage Document

This document explains how to use Polkasign to create a contract and sign the entire process of chaining with multiple signers.

## Apply test coins

Polkasign currently uses the SubDAO chain and has deployed a test chain by itself for preliminary testing. Because it is a test chain, it is very simple to apply for test coins. There are some public keys built into polkadot Apps for testing. 

Open the browser account page of the SubDAO test chain, [http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/accounts,](http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/accounts,) you can see that Alice has a lot of native coins, You can transfer some to your own account.


## Home page

Go to the polkasign homepage, you can see your account and balance. If it is a local compilation and deployment, directly visit [http://127.0.0.1:3000/.](http://127.0.0.1:3000/.)


The Queue column on the right represents a list of contracts that are waiting to be signed, and History represents a list of contracts that have been signed. 

Click New Contract to create a new contract.

## Create Contract

### Upload contract

The first step requires you to upload the contract PDF file, which will then be uploaded to ipfs for storage, and the metadata will be saved on the chain.


### Add a signatory


Click Add a signer to add the substrate address of the person who needs to sign. After the addition is complete, click Review to enter the next step.

### View contract file


Check whether the contract is complete, click Next to submit the contract on the chain.

### Upload contract to chain


In this step, check whether the contract and the signer are correct, and then you can click the Send button to start the chain.


First, the contract file will be uploaded to ipfs to ensure that it will not be tampered with.


Then a signature box will pop up, and you need to enter a password to sign the transaction on the chain. After signing, wait for a while, the page will prompt whether the chain is successful.

### Signing the contract

Enter the page waiting to sign the contract, expand the contract details, and click view to sign the contract on the chain. It should be noted that if you are not the contract creator, you are also viewing the contract to be signed on this page.

### View unsigned contracts

Click Contracts in the left column, select Queue, enter the list of contracts to be signed by the user, and expand the contract details. You can see that no one has completed the signature.

>Note: If the signatory does not have you, the corresponding contract information cannot be found, even if the signature is submitted by calling the contract, it will be rejected.

### Sign it

Click the view button to enter the signing page.


Click the My Signatures button on the right, select the corresponding signature area, and perform a handwritten signature.


The PDF page on the left shows your handwritten signature, and the right side shows your handwritten signature metadata. Click the Send button to digitally sign and wind up the chain.




After the transaction is confirmed, check your contract list.


It shows that you have signed it. At this time, you need to notify your partner to log in to polkasign to sign the contract.

### Signing by collaborator

After the collaborator logs in to polkasign, he also finds the corresponding contract and clicks the View button to enter the signing page.


The main contract document is displayed on the left, and the signature information of other people is displayed at the same time. The partner can click the My Signarures button to make a handwritten signature at the corresponding location. The right side of the page displays the signature information of all signers.


Click the Send button, perform a digital signature, and wait for the transaction to be on the chain. Return to the homepage after success, you can find that the contract has been classified in the History column, expand the view, and find that the contract has been signed. The status changes to Finished.


## Create a contract with sign

polkasign supports directly signing the contract and uploading it to the chain when creating a contract, avoiding two transactions. In some scenarios, the process of contract creators can be simplified.

### Upload contract

The same steps as before to create a contract.


### Choose co-signer

The same as the previous steps of creating a contract.


### View and sign the contract

This step is slightly different from before. To view the contract document, you can click the My Signature button on the right to sign the handwritten signature at the corresponding position.


### Submit Digital signature to chain

Click send to send it on the chain. At this time, you will be asked to digitally sign the file hash and upload it to the chain.




When you return to the homepage, you will find that you have created the contract and signed it at the same time, and then notify the partner to sign it.


## View own contract

Polkasign can view the contracts that have been created, waiting to be signed, and signed from 3 pages. Waiting for the signing of the contract, the historical contract page has been explained when signing the contract. Next, introduce the My Contracts page.


### The info of contract

On the list, click the eye icon in the Operation column to view the chain information of the contract. Including contract name, creation time, storage information, etc.


### Download contract files

On the list, click the download icon in the Operation column to download the contract master file directly.

