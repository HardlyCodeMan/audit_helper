# audit_helper
## Description

audit_helper is a Python3 helper script for Linux to automate some Foundry boilerplate set up in audit repositories.

Too many times have I found myself initialising Hardhat framework based audit repositories with my preferred audit framework Foundry.

## Requirements

Python3
```bash
user@machine:~/ sudo apt install python3
```

Foundry
```bash
user@machine:~/ curl -L https://foundry.paradigm.xyz | bash
```

## Installation

```bash
mkdir ~/audit_helper
wget https://raw.githubusercontent.com/HardlyCodeMan/audit_helper/main/audit_helper -o ~/audit_helper/audit_helper
chmod u+x ~/audit_helper/audit_helper
echo "export PATH=$PATH;~/audit_helper/audit_helper" >> ~/.bashrc
source ~/.bashrc
```

## Usage Example

```bash
user@machine:~/audit_repo$ audit_helper -c src/ -o test/ -p myTest_ -s -oz
```

The above bash command will:
- initialise Foundry into the repository root (with ``-s``) 
- remove the initial Counter.* files created automatically by ``foundry init``
- install the openzeppelin/openzeppelin-contracts (with ``-oz``)
- set the contract source in foundry.toml to src/ (with ``-c``)
- set the test source in foundry.toml to test/ (with ``-o``)
- create boilerplate test files
- prefix the boilerplate test filenames with myTest_ (with ``-p``)

## Flags

| --flag | -flag | Description |
|---|---|---| 
| --help | -h | Display this menu |
| --version | -v | Print the version number |
|||| 
| --contracts | -c | Location of contracts |
| --output | -o | Test output folder. (Default: test/) |
| --prefix | -p | Test file prefix (Default: "") |
| --setup | -s | Initialise Foundry project and edit foundry.toml accordingly |
| --openzeppelin | -oz | Requires -s flag. Initialize with OpenZeppelin-Contracts repository |
| --solmate | -sm | Requires -s flag. Initialize with Solate repository |

## Links
- [Changes](./CHANGELOG.md)
- [License](./LICENSE)

- [Foundry](https://github.com/foundry-rs/foundry)
- [OpenZeppelin](https://github.com/openzeppelin/openzeppelin-contracts/)
- [Solmate](https://github.com/transmissions11/solmate)

## Issues and Improvements

Feel free to create issues to raise awareness of problems or feature implementation requests.

By all means please contribute fixes and features through pull requests.