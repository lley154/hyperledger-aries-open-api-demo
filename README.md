# Hyperledger Aries OpenAPI Demo
# Setup

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



