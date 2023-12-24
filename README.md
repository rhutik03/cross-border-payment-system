# Blockchain Based Cross Border Payment System

Cross Border Payment is a private blockchain application based on Hyperledger. This project aims to facilitate the tracking and processing of cross-border payments.

## Project Description

This project is a blockchain application developed on the Hyperledger framework. It includes smart contracts used for tracking, validating, and processing cross-border payments. A network has been established for transactions between different banks, ensuring transparent monitoring of payment processes.

## Installation

To run this project in a local development environment, you can follow the steps below:

Requirements:
   - Docker
   - Nodejs 

### Terminal Commands

### Starting the Network and Running the Application

1. Navigate to the `cbps-network` directory:

```bash
cd cbps-network
```

2. Run the following command to start the network and create a channel:

```bash
./network.sh up createChannel -c bankschannel -ca -s couchdb0
```

3. Deploy the chaincode by running the following command:

```bash
./network.sh deployCC -c bankschannel -ccn bank -ccp ../crossBorderPayment/chaincode-go/ -ccl go -ccep "OR('Org1MSP.peer','Org2MSP.peer')"
```

4. Navigate to the `crossBorderPayment/application` directory:

```bash
cd ../crossBorderPayment/application
```

5. Install the required dependencies using npm:

```bash
npm install
```

6. Run the following commands to enroll the admin users:

```bash
node enrollAdmin.js org1
node enrollAdmin.js org2
```

7. Start the application by running the following command:

```bash
node app.js
```
If there are no errors, the explorer interface will be accessible at `http://localhost:3000`.

![Bank and Customer LogIn/SignUp Page](demo-images/mainpage.png)


8. Creating Banks

![Creating Banks](demo-images/creatingaccnts.png)
Bank Details
![Details Bank1](demo-images/bank1details.png)
![Details Bank2](demo-images/bank2details.png)

