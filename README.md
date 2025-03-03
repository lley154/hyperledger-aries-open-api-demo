# Hyperledger Aries OpenAPI Demo
## Setup

Install docker desktop for either Mac, Windows or Linux https://docs.docker.com/desktop/

### Faber
Open a terminal window for Faber
```
git clone https://github.com/openwallet-foundation/acapy
cd acapy/demo
LEDGER_URL=http://test.bcovrin.vonx.io ./run_demo faber --events --no-auto --bg
```
After the docker has started, use the following command to show the output of the logs
```
docker logs -f faber
```
Open a browser tab and confirm you can access the Swagger APIs for Faber at http://localhost:8021

### Alice
Open another terminal window for Alice
```
LEDGER_URL=http://test.bcovrin.vonx.io ./run_demo alice --events --no-auto --bg
```
After the docker has started, use the following command to show the output of the logs
```
docker logs -f alice
```
Open a browser tab and confirm you can access the Swagger APIs for Alice at http://localhost:8031.

## Creating a Connection
Using Faber's API http://localhost:8021, find and execute the ```/out-of-band/create-invitation``` endpoint.

Please use the following payload for creating an invitation:
```
{
     "alias": "Faber",
     "handshake_protocols": ["https://didcomm.org/didexchange/1.0"],
     "auto_accept": true,
     "multi_use": false
}
```
Copy the entire block of the invitation object, from the curly brackets {}, excluding the trailing comma.

To receive the invitation by Alice, go the Alice's API http://localhost:8031 and find the ```/out-of-band/eceive-invitation endpoint.

Replace the pre-populated text with the invitation object from Faber.

Next, we need Alice to accept the invitation.  Looking at the log out for Alice, we can see the ```contection_id``.  

In Alice's API, find the ```/connections/{conn_id}/accept-invitation``` endpoint, and use the connection_id found int Alice's log output.

If you look at the log output for Faber, you should also see the connection state has changed to connected.  Please note that the connection id will be different betwee Alice and Faber, but has the same XXX.




