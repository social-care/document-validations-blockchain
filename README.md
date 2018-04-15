# Social Care Document Validation with Hyperledger Blockchain Technology

This project is based on this [Hyperledger Developer Tutorial](https://hyperledger.github.io/composer/latest/tutorials/developer-tutorial.html).

### Pre requisites
To run this locally, it is necessary to install [Hyperledger Development Tools](https://hyperledger.github.io/composer/latest/installing/development-tools.html).

### Build

From the application directory, run the following command:
```sh
$ composer archive create -t dir -n .
```
After the command has run, a business network archive file called `social-care@0.0.1.bna` has been created in the current directory.

### Running locally

**You have to get a fabric up and runnig before installing this**:

1. To install the business network, from the tutorial-network directory, run the following command:
```sh
$ composer network install \
    --card PeerAdmin@hlfv1 \
    --archiveFile social-care@0.0.1.bna
```
2. To start the business network, run the following command:
```sh
$ composer network start \
    --networkName social-care \
    --networkVersion 0.0.1 \
    --networkAdmin admin \
    --networkAdminEnrollSecret adminpw \
    --card PeerAdmin@hlfv1 \
    --file networkadmin.card
```
3. To import the network administrator identity as a usable business network card, run the following command:
```sh
$ composer card import --file networkadmin.card
```
4. To check that the business network has been deployed successfully, run the following command to ping the network:
```sh
$ composer network ping --card admin@social-care    
```
### REST API

To create the REST API, navigate to the tutorial-network directory and run the following command:
```sh
$ composer-rest-server
```
Enter `admin@tutorial-network` as the card name.

Select **never use namespaces** when asked whether to use namespaces in the generated API.

Select **No** when asked whether to secure the generated API.

Select **Yes** when asked whether to enable event publication.

Select **No** when asked whether to enable TLS security.
