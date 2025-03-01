# RegenPass: A POAP Platform for Dynamic AR Event Engagement

## Short Description
RegenPass is a next-generation POAP (Proof of Attendance Protocol) platform that transforms event participation into a dynamic, interactive digital experience. By combining geo-location, augmented reality (AR), AI-powered booth recognition, and cross-chain minting via CCIP/Chainlink, RegenPass enables attendees to collect unique, branded POAPs that serve as verifiable proof of their participation—minted on the ideal blockchain network based on the event booth detected.

![image](https://github.com/user-attachments/assets/ce6c871a-468a-4a0c-8c76-9db9b790acb7)

## Contract Details
- **Chainlink VRF Random Generator Contract**: [0x9870b407fD14351818cE1424063724E4a5C0FFC2](https://base-sepolia.blockscout.com/address/0x9870b407fD14351818cE1424063724E4a5C0FFC2)
- **Base Sepolia Cross Chain POAP**: [0x2D2B9Bf62b0143a8D68eD4A7063E5F50244dFC81](https://sepolia.basescan.org/address/0x2D2B9Bf62b0143a8D68eD4A7063E5F50244dFC81)
- **Ethereum Sepolia Cross Chain POAP**: [0xefA8f407FC504A45ca2079bD5C1B087a81C38F2a](https://sepolia.etherscan.io/address/0xefA8f407FC504A45ca2079bD5C1B087a81C38F2a)

- **Deployment**:
  - **Base Sepolia**: The primary contract is deployed here. An agent initiates cross-chain mint requests from this chain using Image Processing.
  - **Ethereum Sepolia & Arbitrum Sepolia**: Destination contracts are deployed on these chains to receive and process cross-chain minting requests.
  
- **Direct Minting**:  
  The direct mint function no longer has the restriction that previously limited it to Arbitrum Sepolia. This change enables direct minting on any chain, including Base Sepolia.
  
- **Cross-Chain Minting**:  
  The `crossChainMint` function is now called on Base Sepolia. Once invoked, the Chainlink CCIP router (simulated via the CCIPLocalSimulatorFork) routes the mint request to the destination chain where the NFT is minted.

## Transaction Link

Cross Chain Mint transaction can be viewed here:  
[View Transaction on Chainlink CCIP](https://ccip.chain.link/tx/0x67089e7792bc83b4139052d377f4dccf37e59c7f3c786fc7db2c9eef427aae41)

![image](https://github.com/user-attachments/assets/d6d2d469-4357-4284-a10a-443c7d8da919)

VRF Chainlink Generator  
[View Transaction on Blockscout](https://base-sepolia.blockscout.com/tx/0x6c726768a5ebadb11fdf152dd445d6872ff2457d16dae2ae4dc6cf06b15709a6)

![image](https://github.com/user-attachments/assets/6dea79d9-759d-4833-9217-e07631a4fbc8)

## Key Features
- **Seamless Onboarding & Geo-Verification**  
  Quickly register and verify attendance using geo-location to ensure participants are within designated event zones.

- **Immersive AR Experience**  
  Engage with dynamic AR assets as soon as the camera opens, enhancing the in-person experience with interactive digital overlays.

- **AI-Powered Booth Recognition & Agent Flow**  
  As soon as the camera activates, the integrated AI agent begins scanning the image. This real-time analysis not only recognizes booth banners and identifies the associated chain (e.g., Chainlink or Base) but also dynamically provides the client with a tailored transaction builder. This ensures that the correct minting process is initiated based on the detected chain booth.

- **Cross-Chain POAP Minting via CCIP/Chainlink**  
  Initiate a mint function on Sepolia that leverages CCIP to direct the actual minting on the target blockchain as determined by the recognized booth, ensuring optimal cross-chain interoperability.

- **Secure, Real-Time Transaction & Wallet Updates**  
  Conduct secure on-chain transactions with immediate updates to the user’s digital wallet, providing verifiable proof of attendance in real time.

- **Robust Error Handling & User Feedback**  
  Offer clear prompts for re-scanning or retrying in cases of unrecognized inputs or transaction failures, ensuring a smooth user experience.

## Relevant Use-Cases
- **Event Attendance Verification**  
  Provide a reliable and engaging method for participants to prove their attendance at events, conferences, and expos.

- **Brand Activation & Engagement**  
  Allow brands to create custom POAP experiences (e.g., Chainlink or Base-themed) that boost interaction and leave lasting digital impressions.

- **Community Building & Gamification**  
  Foster community spirit and friendly competition by enabling users to collect, display, and share their unique POAPs across social channels.

- **Marketing & Promotional Campaigns**  
  Enhance event marketing by offering exclusive, collectible digital rewards that can double as discount coupons or access passes for future events.

## User Interaction and Data Flow
1. **Geo-Verification**:  
   The user arrives at the event and is geo-verified to ensure they are within the designated event zone.
2. **Booth Scanning**:  
   The user scans a booth using their mobile camera.
3. **AI Analysis**:  
   The AI agent analyzes booth banners to determine the corresponding blockchain.
4. **AR Engagement**:  
   Augmented reality overlays provide interactive digital assets related to the event, enhancing the overall experience.
5. **Transaction Building**:  
   A tailored transaction builder is provided based on the detected blockchain.
6. **Minting Confirmation**:  
   Upon user confirmation, the transaction is executed on the correct chain via CCIP.
7. **POAP Issuance**:  
   The POAP is minted and immediately displayed in the user’s wallet.
8. **Leaderboard & Random Winner Selection**:  
   The user is added to a leaderboard, where lucky winners are selected using Chainlink VRF for fair and transparent random selection, granting exclusive event-specific perks.

## Project Architecture and Development Process
- **Frontend**:  
  A mobile-first web interface with integrated camera functionality for real-time scanning.
- **Backend**:  
  Incorporates AI-powered booth recognition, geo-fencing for event verification, and AR enhancements.
- **Smart Contracts**:  
  Deployed on Base Sepolia & Ethereum Sepolia, supporting both direct and cross-chain minting.
- **Cross-Chain Execution**:  
  Leverages Chainlink CCIP for seamless cross-chain POAP minting.
- **Random Winner Selection**:  
  Utilizes Chainlink VRF to fairly select lucky winners among event attendees for exclusive rewards.

