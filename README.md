### Lottery Smart Contract  

This Solidity smart contract implements a simple lottery system where participants can enter the lottery by sending 1 Ether to the contract. Once enough participants have entered, the manager can select a random winner to receive the accumulated Ether.  

#### Features  
1. **Manager Role**: The contract deployer becomes the manager and has exclusive control over certain functions like checking the balance and selecting the winner.  
2. **Entry Fee**: Participants must send exactly 1 Ether to join the lottery.  
3. **Random Winner Selection**: A pseudo-random mechanism selects the winner from the participants.  
4. **Payout**: The winner receives all Ether accumulated in the contract.  
5. **Reset Mechanism**: After selecting a winner, the participants list is reset for a new round.  

#### Functions  
- **constructor()**: Sets the deployer of the contract as the manager.  
- **receive() external payable**: Enables the contract to receive Ether and adds the sender to the participants list if 1 Ether is sent.  
- **getBalance()**: Allows the manager to view the contract's balance.  
- **random()**: Generates a pseudo-random number using block properties and participant count.  
- **selectWinner()**: Requires at least 3 participants and manager privileges to select a random winner, transfer the prize, and reset the lottery.  

#### How to Use  
1. Deploy the contract on a compatible Ethereum network.  
2. Participants can enter the lottery by sending exactly 1 Ether to the contract's address.  
3. Once there are at least 3 participants, the manager can call `selectWinner()` to choose a winner and reset the lottery for the next round.  

#### Disclaimer  
This contract uses a pseudo-random number generator, which is not secure for production-grade lotteries. For secure randomness, consider integrating Chainlink VRF or similar services.  

