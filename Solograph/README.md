# Solograph
Solograph is a tool used to visualize the control flow of Solidity smart contracts.It can be useful for analysing the security of smart contracts by providing a visual representation of the control flow within the contract's code. This can assist in identifying potential vulnerabilities and understanding the overall structure of the contract.
# Legend:
-> Red: Send to external address
-> Blue: Constant function
-> Yellow: View 
-> Green: Call
-> Orange: Transfer
-> Lilaac: Payable

# How to install Solograph

Step 1: Mandatory Step
```
sudo su
```
Step 2: Install npm:
```
sudo apt install npm
```
Step 3:Install solograph using:
```
npm install -g solgraph
```
Step 4: Add the unsfe-perm flag:
```
sudo npm install -g solgraph --unsafe-perm=true --allow-root
```
Step 5: Install Graphivz
```
apt install graphviz
```


  # Run Solograph

Step 6: Make a directory named Solograph using:
```
mkdir solgraph
```
```
cd solgraph
```
Step 7: Make a MyContract.sol
```
touch MyContract.sol
```
```
nano MyContract.sol
```
  <b><u> Paste the following </u></b>
  ```
contract MyContract {
  uint balance;

  function MyContract() {
    Mint(1000000);
  }

  function Mint(uint amount) internal {
    balance = amount;
  }

  function Withdraw() {
    msg.sender.send(balance);
  }

  function GetBalance() constant returns(uint) {
    return balance;
  }
}
```

Step 8: Create MyContract.dot
```
touch MyContract.dot
```
```
nano MyContract.dot
```
  <b><u>Paste the following</u></b>
  ```
strict digraph {
  MyContract
  Mint [color=gray]
  Withdraw [color=red]
  UNTRUSTED
  GetBalance [color=blue]
  MyContract -> Mint
  Withdraw -> UNTRUSTED
}
```

Step 9: generate the png of yoor contract
```
dot -Tpng MyContract.dot -o MyContract.png
```
# Output
![]()





