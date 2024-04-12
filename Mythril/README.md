# Mythril
Mythril is a security analysis tool for EVM bytecode. It detects security vulnerabilities in smart contracts built for Ethereum, Hedera, Quorum, Vechain, Roostock, Tron and other EVM-compatible blockchains. It uses symbolic execution, SMT solving and taint analysis to detect a variety of security vulnerabilities.

# How to install Mythril
Step-1: Check if Python and pip are installed
```
python --version
```
  If Python is not installed use:
```
sudo apt update
```
```
sudo apt install python3
```
  Install pip:
```
sudo apt install python3-pip
```
Step-2: Install Mythril using 
```
pip3 install mythril
```
Step-4: Verify Installation:
```
mythril --version
```
# How to run Mythril
 Step-5:Create a 'my_contract.sol' file in any local directory. You may paste the following in a Text Editor and save the file as my_contract.sol .<br>
You may use the following smart contract for testing Slither:
```
pragma solidity ^0.4.15;

contract Missing{
    address private owner;

    modifier onlyowner {
        require(msg.sender==owner);
        _;
    }

    // The name of the constructor should be Missing
    // Anyone can call the IamMissing once the contract is deployed
    function IamMissing()
        public 
    {
        owner = msg.sender;
    }

    function withdraw() 
        public 
        onlyowner
    {
       owner.transfer(this.balance);
    }
}
```
Step-6: Go to the dirctory in you terminal and add:
```
myth analyze my_contract.sol
