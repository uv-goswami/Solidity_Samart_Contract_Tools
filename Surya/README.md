# Surya
Surya is a tool for smart contract visualization and analysis for Ethereum. It provides insights into the structure of Solidity smart contracts by generating interactive diagrams and graphs, allowing developers and auditors to better understand the relationships between different parts of the contract code.

# How to Install Surya
Step-1: Install Node.js and npm if not installed.
```
sudo apt update
sudo apt install nodejs npm
```
Step-2:Install graphivz, in order to view graph output.
```
sudo apt install graphviz
```
To verify if graphivz is installed use:
```
dot -V
```
Step-3: install Surya:
```
sudo npm install -g surya
```
Step-4: To verify if Surya is installed or not use:
```
surya --version
```
# How to Run Surya
Step-5: Step-5:Create a <temp.sol> file in any local directory. You may paste the following in a Text Editor and save the file as my_contract.sol .<br>
You may use the following smart contract for testing Slither:
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Temp {
    uint256 public data;

    event DataUpdated(uint256 newValue);

    constructor(uint256 initialValue) {
        data = initialValue;
    }

    function setData(uint256 newValue) external {
        data = newValue;
        emit DataUpdated(newValue);
    }

    function getData() external view returns (uint256) {
        return data;
    }
}
```
Step-6:To generate a DOT file for the inheretence graph use:
```
surya inheritance temp.sol
```
Step-7: To generate a DOT file for the control flow graph of the contract:
```
surya graph temp.sol
```
Step-8: To generate a structured output of its syntax tree:
```
surya parse temp.sol
```

# Output
For Step-6 and Step-7:
![](https://github.com/uv-goswami/Solidity_Smart_Contract_Tools/blob/main/Surya/01_Output.png)

For Step-8:
![](https://github.com/uv-goswami/Solidity_Smart_Contract_Tools/blob/main/Surya/02_Output.png)
![](https://github.com/uv-goswami/Solidity_Smart_Contract_Tools/blob/main/Surya/03_Output.png)
![](https://github.com/uv-goswami/Solidity_Smart_Contract_Tools/blob/main/Surya/04Output.png)
![](https://github.com/uv-goswami/Solidity_Smart_Contract_Tools/blob/main/Surya/05_Output.png)
