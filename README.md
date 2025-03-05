
# monero_crack
Script to use a password list to attack a monero wallet (sequentially) using the Monero Wallet CLI. This function can be used in ```bash```, ```zsh``` etc or you can make it more usable by creating an alias and putting it in your profile.

### Prerequisites
1) You must install ```monero-wallet-cli``` from [getmonero.org](https://www.getmonero.org/resources/user-guides/monero-wallet-cli.html). Version 18.3.2 and above should work.
2) Set up an environment variable ```$MONERO_DIR``` to point to the location you have placed ```monero-wallet-cli```.

### Password lists
Please use one password per line, and keep the lists short as this process is very slow compared to other password cracking! Also passwords with strange characters *may not work*.

### Installation (as an alias)
1) Open your user profile (eg ```.bash_profile```, ```.zprofile```)
2) Add an alias to your monero-wallet-cli (change the path appropriately): 
```bash
export MONERO_DIR='./monero-aarch64-apple-darwin11-v0.18.3.3'
```
3) Copy the function ```monero_crack``` to the end of the profile

### Running
You will need the monero wallet (either the file without extension or the ```.keys``` file) and a list of passwords:
```bash
monero_crack wallet passwords.txt
```
The script will try each password in turn and stop when either the correct password has been found or the password list is exhausted
