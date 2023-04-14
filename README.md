# Activate the environment

```bash
python3.9 -m venv venv
source venv/bin/activate
```

Ensure having these env varaibles:
```bash
export STARKNET_NETWORK=alpha-goerli
export STARKNET_WALLET=starkware.starknet.wallets.open_zeppelin.OpenZeppelinAccount
```

## Create an account 

```bash
starknet new_account --account v0.11.0.2
```

Fill up the account with ~0.005 ETH

```bash
 starknet deploy_account --account v0.11.0.2
```

## Deploy a contract

Compile it:
```bash
starknet-compile src/first.cairo sierra/first.json
```

Declare it:
```bash
starknet declare --contract sierra/first.json --account v0.11.0.2
```

⚠️ **CLASS_ALREADY_DECLARED**

So we don't need to declare it, just deploy an instance of the class hash:

```bash
starknet deploy --class_hash 0x9b09ce076e1789d2901b83b27f88b9dfdc5d8952ee694f0ad6416640839af7 --account v0.11.0.2
```

