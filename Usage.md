# PolkaSign Usage Document

This document explains how to use Polkasign to create a contract and sign the entire process of chaining with multiple signers.

## Apply test coins

Polkasign currently uses the SubDAO chain and has deployed a test chain by itself for preliminary testing. Because it is a test chain, it is very simple to apply for test coins. There are some public keys built into polkadot Apps for testing. 

Open the browser account page of the SubDAO test chain, [http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/accounts,](http://47.243.43.150:3000/?rpc=ws%3A%2F%2F43.133.174.232%3A9944#/accounts,) you can see that Alice has a lot of native coins, You can transfer some to your own account.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-5.png)

## Home page

Go to the polkasign homepage, you can see your account and balance. If it is a local compilation and deployment, directly visit [http://127.0.0.1:3000/.](http://127.0.0.1:3000/.)

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-6.png)

The Queue column on the right represents a list of contracts that are waiting to be signed, and History represents a list of contracts that have been signed. 

Click New Contract to create a new contract.

## Create Contract

### Upload contract

The first step requires you to upload the contract PDF file, which will then be uploaded to ipfs for storage, and the metadata will be saved on the chain.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-8.png)

### Add a signatory

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-9.png)

Click Add a signer to add the substrate address of the person who needs to sign. After the addition is complete, click Review to enter the next step.

### View contract file

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-10.png)

Check whether the contract is complete, click Next to submit the contract on the chain.

### Upload contract to chain

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-11.png)

In this step, check whether the contract and the signer are correct, and then you can click the Send button to start the chain.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-13.png)

First, the contract file will be uploaded to ipfs to ensure that it will not be tampered with.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-14.png)

Then a signature box will pop up, and you need to enter a password to sign the transaction on the chain. After signing, wait for a while, the page will prompt whether the chain is successful.

### Signing the contract

Enter the page waiting to sign the contract, expand the contract details, and click view to sign the contract on the chain. It should be noted that if you are not the contract creator, you are also viewing the contract to be signed on this page.

### View unsigned contracts

Click Contracts in the left column, select Queue, enter the list of contracts to be signed by the user, and expand the contract details. You can see that no one has completed the signature.

>Note: If the signatory does not have you, the corresponding contract information cannot be found, even if the signature is submitted by calling the contract, it will be rejected.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-15.png)

### Sign it

Click the view button to enter the signing page.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-16.png)

Click the My Signatures button on the right, select the corresponding signature area, and perform a handwritten signature.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-17.png)

The PDF page on the left shows your handwritten signature, and the right side shows your handwritten signature metadata. Click the Send button to digitally sign and wind up the chain.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-18.png)

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-19.png)

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-20.png)

After the transaction is confirmed, check your contract list.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-21.png)

It shows that you have signed it. At this time, you need to notify your partner to log in to polkasign to sign the contract.

### Signing by collaborator

After the collaborator logs in to polkasign, he also finds the corresponding contract and clicks the View button to enter the signing page.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-22.png)

The main contract document is displayed on the left, and the signature information of other people is displayed at the same time. The partner can click the My Signarures button to make a handwritten signature at the corresponding location. The right side of the page displays the signature information of all signers.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-23.png)

Click the Send button, perform a digital signature, and wait for the transaction to be on the chain. Return to the homepage after success, you can find that the contract has been classified in the History column, expand the view, and find that the contract has been signed. The status changes to Finished.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-24.png)

## Create a contract with sign

polkasign supports directly signing the contract and uploading it to the chain when creating a contract, avoiding two transactions. In some scenarios, the process of contract creators can be simplified.

### Upload contract

The same steps as before to create a contract.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-25.png)

### Choose co-signer

The same as the previous steps of creating a contract.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-26.png)

### View and sign the contract

This step is slightly different from before. To view the contract document, you can click the My Signature button on the right to sign the handwritten signature at the corresponding position.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-27.png)

### Submit Digital signature to chain

Click send to send it on the chain. At this time, you will be asked to digitally sign the file hash and upload it to the chain.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-28.png)

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-29.png)

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-30.png)

When you return to the homepage, you will find that you have created the contract and signed it at the same time, and then notify the partner to sign it.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-31.png)

## View own contract

Polkasign can view the contracts that have been created, waiting to be signed, and signed from 3 pages. Waiting for the signing of the contract, the historical contract page has been explained when signing the contract. Next, introduce the My Contracts page.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-32.png)

### The info of contract

On the list, click the eye icon in the Operation column to view the chain information of the contract. Including contract name, creation time, storage information, etc.

![](https://raw.githubusercontent.com/SubDAO-Network/polkasign-docs/main/graphics/image-33.png)

### Download contract files

On the list, click the download icon in the Operation column to download the contract master file directly.

