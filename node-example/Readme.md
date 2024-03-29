# Run a XCBC Validator
## Setting up a node
1. Git clone https://github.com/Xcblockchain/XCBCNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/XCBC  /root/
```
3. Create an Account

```
cd /root/XCBC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake XCBC coin, all you should do is sending your XCBC coin to the XCBC Consensus contract address over the XCBC network from the validator address.
    The XCBC Consensus contract address: 0x5f5A17f45f64717300527236eD1B50054eAdB76E
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to XCBC and send the XCBC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /XCBC/nodes/validator/keys/XCBC/UTC--xxxx
    /XCBC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
