# DAO-Streaming-Platform

## Inspiration
DAO.tv is inspired by a pressing issue in today's society. Given the last few years, it is evident that platforms such as YouTube bare a great responsibility. This responsibility is to serve the community of content creators and users alike with a fair environment that promotes freedom of speech and expression. The issue lies that YouTube has broken this responsibility countless times in years. Whether it be unfair algorithms, shameless removal of certain fair content, or prioritizing content that produces greater interest of advertisers, it is clear YouTube and other monopolistic tech giants cannot be trusted. To make the situation worse, content creators do not have a better choice than to put up with YouTube. YouTube has 0 competition that offers the attention certain content creators need. This is why they are allowed to essentially bully the entire user base. In fact, recently, YouTube has been strict regarding the removal of false COVID Content. The issue here is that YouTube becomes oppressive, and their rules of what counts as "misinformation" is a grey zone. They have proven to overstep their ability, and in the end it's the content creators that are hurt, without the ability to fight back.

## What it does
DAO.tv is an entirely independent ecosystem, that does not rely on any central servers or databases to stream video files. We also applied the Decentralized Autonomous Organization concept to the moderation and user rule features. Users are anonymously moderating the website's content, as well as being responsibile for democratizing the rules of the platform. The ecosystem we created is completely self sustainable, as the Content Creators store video files across decentralized nodes.

We incentivize users to host these nodes by offering a Crypto Token reward. There are multiple ways on the site to earn the Crypto Token, also known as DTV. DTV is earned by users who anonymously review reported content. Multiple people can review reported content, determine whether the offensives are legitimate, then receive DTV as a reward for their moderation. We implement a Staking system in order to prevent abuse of this system. Users stake an amount of DTV in order to participate. The users who appropriately identified the select verdict receive the reward, meaning that bots and abuse cannot realistically make money through spamming the system- only truthful real humans that review the videos accurately can receive these rewards.

This DTV would be used to purchase ads and premium content on the site. The second function for DTV is donations. Users can donate DTV to other content creators as a form of a tip- similar to a twitch donation. That said, the crypto reward, which has real $ value, is a way that we can make this sustainable system possible. Crypto incentives is what drives the platform to remain anonymous and fair, while giving back good rewards for outstanding content, and fair moderation. With the lack of a central owner and server, DAO.tv fosters the most secure, fair, and prosperous community for it's content creators. We like to say it's for content creators, ran by content creators.

## How I built it
Our tech stack was very, very complex. The blockchain infrastructure and computing systems is the backbone of this project. We used nested IPFS hashes in order to organize video files, video information, and other content into a manner that can be efficiently called by our front end. Our front end is made with react, and we used fetch api, and axios in order to interact with our very extensive back end. Our back end features multiple endpoints, 2 of which are dedicated to database infrastructure One of the contracts handles data related to the moderation system (such as voting), and the other handles data related to video files. The way we planned our "database" though is completely decentralized. We created two smart contracts solely for holding references to IPFS. We can call the methods on the smart contract to constantly update this hash with new content, and call get() methods to receive the hash. We created algorithms to parse and add new information into a json-estique format within ipfs. We had to cleverly organize it in a way that each new hash on the smart contract is a collection of the previous hash data, plus any new data (such as videos). 

Our other main smart contract handles all the crypto token data. We opted for a simpler version of the erc-20 token. We have 2 main end points that handle the interaction with this smart contract. We can essentially take any wallet address, and distribute a small amount of DTV upon call to the api. The call to the api is dependent on other events, such as moderation reward distribution. We can also send DTV tokens from user A to user B (such as a donation). We also use this smart contract to keep track of all owners of DTY, and their account balances. This way we can continue to update the DTV balance on the client side, while preventing over-spending, or similar issues.

We used ganache and truffle framework to deploy and develop our 5 smart contracts. We used the remix ethereum ide to develop our smart contracts, test them, and interact with the contracts during development. We used metamask as our web3 provider and injection. Metamask is a secure way for us to manage log in to the web platform. It is also the way in to which the user can utilize the DTV, and participate in the ecosystem.

## Challenges I ran into
Our group ran into COUNTLESS tedious issues. Most of out issues stem from the fact we are using bleeding edge, not always well documented technology. Our first major problem came in the form of  web3 implementation in the back end. Our server was simply not interacting with the smart contract functions correctly for hours. We could not get web3 to work, so eventually we had to switch to using the ether.js library for the server. The second large issue was planning the infrastructure of this project down the road. It was quite difficult to visualize the methods and the structure/flow of the data. We had to plan out nested ipfs data structures. The collaboration software we used also caused some issues that didn't allow us to properly render images. We had to eventually use firebase to host images in order to render them(lul). The last major problem that we had was structuring the token contract. We had to play a lot with the contract in solidity before we got it working.

## Accomplishments that I'm proud of
We are very proud of the technicality of this project, as this is definitely tech wise the hardest project we had to do. We are also proud to have built something that has real application, and real potential. Lastly, our skill to pick up ideas and problem solving ability effectively along the way is something else we are very proud of.

## What I learned
We learned about structuring data in a decentralized manner was a huge learning curve. We also learned we cannot run ipfs on multiple nodes on the same computer at once. We also learned about retrieving data from IPFS and how to do it effectively. We also learned how to plan out and execute token distribution to users. Security and moderation issues were also very important learning points during this project. Overall, this was a very long process of problem solving, and given the complexity of the project, we all learned a little about patience- through a lot of debugging!

## What's next for DAO.tv
DAO.tv is looking for it's next steps through interacting with a tes tnetwork, instead of local blockchain. Using the test network opens up the possibility of deploying, and expanding the capabilities of the site.

Developed by Aditya Keerthi, Markos Georghiades, Daniel Yu, and Kevin Gao.
