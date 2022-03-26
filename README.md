# Solidity-Homework

#### Background

This assignment requires automation of joint saving accounts creation. Create a Solidity smart contract that accepts two user addresses which will be able to control a joint savings account. This smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

#### Required Steps:

- Create a Joint Savings Account Contract in Solidity
- Compile and Deploy Your Contract in the JavaScript VM
- Interact with Your Deployed Smart Contract

#### Create a Joint Savings Account Contract in Solidity

- Defined a new contract named JointSavings.
- Defined the following variables in the new contract:

  - Two variables of type address payable named accountOne and accountTwo
  - A variable of type address public named lastToWithdraw
  - Two variables of type uint public named lastWithdrawAmount and contractBalance
  
- Defined a function named withdraw that accepts two arguments: amount of type uint and recipient of type payable address. In this function, code the following:

  - Defined a require statement that checks if recipient is equal to either accountOne or accountTwo. If it isn’t, the require statement returns the “You don't own this account!” text.
  - Defined a require statement that checks if balance is sufficient for accomplishing the withdrawal operation. If there are insufficient funds, it returns the “Insufficient funds!” text.
  - Added an if statement to check if lastToWithdraw is not equal (!=) to recipient. If it’s not equal, set it to the current value of recipient.
  - Called the transfer function of the recipient, and passed it the amount to transfer as an argument.
  - Set lastWithdrawAmount equal to amount.
  - Set the contractBalance variable equal to the balance of the contract by using address(this).balance to reflect the new balance of the contract.
  
- Defined a public payable function named deposit. In this function:

  - Set the contractBalance variable equal to the balance of the contract by using address(this).balance.
  - Defined a public function named setAccounts that takes two address payable arguments, named account1 and account2. In the body of the function, set the values of accountOne and accountTwo to account1 and account2, respectively.
  - Added a fallback function so that contract can store ether that’s sent from outside the deposit function.

#### Compile and Deploy Your Contract in the JavaScript VM

##### Screenshot of successful compilation
##### Screenshot of successful deployment

#### Interact with Your Deployed Smart Contract

Steps to interact with your deployed smart contract:

1. Used the setAccounts function to define the authorized Ethereum address that will be able to withdraw funds from your contract.
  - Dummy account1 address: 0x0c0669Cd5e60a6F4b8ce437E4a4A007093D368Cb
  - Dummy account2 address: 0x7A1f3dFAa0a4a19844B606CD6e91d693083B12c0

2. Tested the deposit functionality of smart contract by sending the following amounts of ether. After each transaction, used the contractBalance function to verify that the funds were added to your contract:
  - Transaction 1: Send 1 ether as wei.
  
  - Transaction 2: Send 10 ether as wei.
  
  - Transaction 3: Send 5 ether.

3. Tested the contract’s withdrawal functionality by withdrawing 5 ether into accountOne and 10 ether into accountTwo. After each transaction, used the contractBalance function to verify that the funds were withdrawn from your contract. Also, used the lastToWithdraw and lastWithdrawAmount functions to verify that the address and amount were correct.
