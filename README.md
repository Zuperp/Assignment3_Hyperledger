# Assignment3_Hyperledger
 
<h1>Assignment 3 Hyperledger fabric</h1>
 
  


<h2> Implementation info </h2>

The implementaiton was not completed, all the tutorials were completed, but the implementation of the voting applicaiton was not completed.
<br>
<br>
<br>

<h1> Analysis and Design </h1> 

<h2>Formulate Hyperledger Fabric use case
Voting application</h2>

*Transparency* is an important part of the voting application use case. Both voters and auditors need to have an idea of what's happening. 
*Secure*. It must be secure to avoid any misconduct from happening.  
*Avoid double spending.* Voters should not be allowed to vote more than once.
*Performance and scalability*. It has to be scalable to the required capacity, and perform at an acceptable level, to be a suitable solution.  
*Simplistic*. It has to be simple enough so that ordinary users can participate.  
*Eligibility*. It has to ensure that the ones casting the votes, are actually eligible to vote.  
*Confidentiality, Integrity, Availability (CIA).*   
*Confidentiality*: Anonymity in votes, but not the voters. Information regarding what was voted can not be shared, but who has voted must be available.  
*Integrity:* It’s important that the integrity is intact, because without integrity, the results are meaningless.  
*Availability*: It has to have high availability, so that the users can cast their votes without problem.  
 
  
<h3>Evaluation analysis table</h3> 

![image](https://user-images.githubusercontent.com/43138778/205723459-ea193584-e076-41ad-8af4-78ccffca9799.png)
  
<br>   
<br> 
<h2> Criteria Analysis </h2>
- Will this project require updates, mutability or deletion of records?

  - Most likely not. The voting system follows a simple transactional model without double spending. A change in law could potentially require an update to the architecture, but we find it very unlikely. 
- Is there agreement that all blockchain participants should be able to view and validate transaction details?
  - Yes, however, transaction details are obfuscated and unreadable. This means that there is no way to figure out what people have voted for.
- Does this architecture fit well in an ecosystem of diverse participants?
  - Yes. Each participant should be able to vote by mail, so there is no difference between the participants. 
- Are there adequate incentives for participants to continue to support the chain indefinitely?
  - Yes. Whenever there is a vote, each individual would like to use their vote just like they would in a traditional system. Voting by mail would also be a quicker option for the voter.
- From an efficiency perspective, are there enough participants and sufficient complexity to buoy the consensus model, validate all transactions, and approve the authentication and authorization processes?
  - A voting system could have as many participants as the entire country's eligible voter population. It would also be hosted by the state, and funded through tax money, ensuring enough resources to process everything.
<br>
<br>
<h2> Suitability analysis </h2>

![image](https://user-images.githubusercontent.com/43138778/205725280-e7951c35-7144-4891-a9af-9c8d6cde55ae.png)

Multi-party is a requirement since the political system requires political parties across the political spectrum to run for elections. There is no trusted authority required, as long as storage and computation is handled on-chain, where it is immutable which is definitely a requirement in order to run a fair vote. High performance is believed to be necessary since a lot of votes are expected at a very fast pace, depending on the voting environment (district, country etc.). High performance is usually not guaranteed in blockchain technology, however, with frameworks such as Hyperledger Fabric we can deploy permissioned high-performance blockchains. This is among more because we can choose consensus mechanisms depending on specific use-cases. Transparency is a requirement for voters to get insight in the voting process. Voters should be identifiable, but actual votes should not. Without transparency a blockchain implementation is no better than a traditional voting system from an end-user point of view. Finally we land on a blockchain implementation, and we can now suggest an architecture based on our use-case.

<br>
<br>
<h2> Designing the Hyperledger Fabric Blockchain </h2>

![image](https://user-images.githubusercontent.com/43138778/205725501-9114f877-2076-4ded-8eab-3d25914d7cbc.png)

Now that we have somewhat argued for the suitability of blockchain, we can use the above design framework to figure out the architecture of the solution. With an e-voting system there is no need for a trusted authority, as long as all computation and storage is on-chain. On-chain is advantageous over off-chain both for storage and computation in high-risk voting systems, because then all votes and counts are immutable and transparent. Off-chain computation is faster than off-chain, however, we find the security aspect very essential. All participants are supposed to be identifiable while their votes should be unidentifiable. This speaks for a private/permissioned blockchain implementation. The block configuration would depend on the environment the blockchain is implemented in. The batch-size and batch-time should be configured so that the transactions per second (TPS) are high enough to finish the voting count within 24 hours of the individual votes.

<br>
<br>

<h2> Design diagram of the hyperledger fabric voting system architecture </h2>

![image](https://user-images.githubusercontent.com/43138778/205725987-8a4804eb-3458-4b18-acd4-8d0283466ee3.png)

The diagram shows a consortium of organizations. The organizations have nodes. <br> The peers uphold a ledger.  And there is a smart contract that can be used. <br>
C1 is channel one, the voting channel in which votes are cast. <br> C2 is the token distribution channel, this channel distributes the tokens used to vote.
Each organization has a certificate which is used to authorize them. <br>
The external applications are connected to the channels so smart chaincode can be evoked.
<br>
<br>

<h3> Collaboration </h3>

**The process of analyzing and designing was done in collaboration with Mads Møller Hansen.**

