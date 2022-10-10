# Web3 Development training - Python
 
- Create a new folder for your project and open VC code on that folder.

## Install Brownie

- Install Python3:

```
$ brew install python3
```

- Install Ganache:

```
$ npm install ganache --global
$ ganache
```

- Install pipx and Brownie:

```
$ python3 -m pip install --user pipx
$ python3 -m pipx ensurepath 
$ pipx install eth-brownie
```

- Alternately, you could install via pip:

```
pip install eth-brownie
```

- Initiate your Brownie environment:

```
$ brownie -- version
$ brownie init
$ ls
```

- Explore folders that Brownie prepare for us: build, contracts, interfaces, scripts, tests, etc.

## Compile a contract

- Copy the file [StoreValue.sol](https://github.com/gonzaloronvera/web3_development_training_python/blob/main/contracts/StoreValue.sol) to the new created contract folder and compile it:

```
brownie compile
```

- Explore the json generated in the build folder.
- Add your Goerli account to Brownie. Get your private key from Metamask:

```
brownie accounts new my-goerli-account
```

- List your available accounts:

```
brownie accounts list
```

## Deploy a contract in your local

- Copy the file [scripts/deploy.py](https://github.com/gonzaloronvera/web3_development_training_python/blob/main/scripts/deploy.py) file into your scripts folder and run it:

```
brownie run scripts/deploy.py
```

## Test your contract

- Copy the file [test/test_store_value.py](https://github.com/gonzaloronvera/web3_development_training_python/blob/main/tests/test_store_value.py) and run:

```
brownie test -s
```

## Deploy to the testnet

- Create a project at [Infura](https://blog.infura.io/). Then, go to settings and find your project ID from the networks endpoints.

```
https://mainnet.infura.io/v3/<PROJECT ID>
```

- Add an environment variable for this project ID. For this, copy and update the [.env](https://github.com/gonzaloronvera/web3_development_training_python/blob/main/.env) and [brownie-config.yaml](https://github.com/gonzaloronvera/web3_development_training_python/blob/main/brownie-config.yaml) files.

- Deploy the contract in Goerli:

```
brownie run scripts/deploy.py —network goerli
```

- Observe the changes in your wallet every time you execute it.
