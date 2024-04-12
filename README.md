# Slither
Slither is a Solidity static analysis framework based on Python 3 and has a wide range of vulnerability detectors, printers for visualization of the contract details, and API for custom analyses.



# How To Install Slither

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
Step-2: Install Solidity Compiler.
```
sudo apt install software-properties-common
```
```
sudo add-apt-repository ppa:ethereum/etherum
```
```
sudo apt install solc
```
```
pip3 install solc-select
```

Step-3: Installing slither using pip:
```
pip3 install slither-analyzer
```
Step-4:Verify if Slither is Installed:
```
slither --version
```
# How to run Slither

Step-5:Create a <my_contract.sol> file in any local directory<br>
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
slither my_contract.sol
```
# Output
![output](https://github.com/uv-goswami/Solidity_Samart_Contract_Tools/blob/main/output.png)
