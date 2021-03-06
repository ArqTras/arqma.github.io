<p>Copyright 2019 The ArQmA Project</p>
<h1 id="arqma-22-multisig-wallet-transfers"><font color="ffd008">ArQmA 2/2 Multisig Wallet Transfers</font></h1>
<p>Purpose: Enable a balance on a joint account that requires 2 or more signatures from separate accounts and their respective digital signatures. A spend transaction that is one way only forward can then be created and enabled from both parties. Refunds and recourses have to be dealt with the seller directly.</p>
<p>Also, a third party signer could also be enabled as an escrow agent could also enable pend forward only transactions or with both buyer and seller agreeing to cancel a purchase the escrow agent can send funds to one party, both or the seller with signoff signatures.</p>
<p>First, the buyers wallet to be converted to multisig must be empty. It is best to use a brand-new, separate walllet for the purpose, although not required. It is strongly advised to make a copy of the wallet files first, just in case something goes wrong. Also the buyer needs to transfer funds from their normal spending wallet to this multisig wallet for personal security and anonymitiy reasons. ### Set-up</p>
<h4 id="step-1-initiate-creation-of-multisig-wallet-and-exchange-data"><font color="ffd008">Step 1 Initiate Creation of Multisig Wallet and Exchange Data</font></h4>
<p>Person A commands:</p>
<p><font color="ffd008">[wallet 47HSuD]: prepare_multisig</font></p>
<p>The output will be something like:</p>
<p>MultisigV1WHyBiEPV5rv3jgU59QUv2ZYTvmN3pwzCL8mp5jTDxkkhRzDjL1T8A2dHTYLmprbUsiLzvPLqRc1GkFHp3mq7dFq6BiE98Ur5cD6P46YYLd5QwD4diqe4VRSiS7GYHATbL4cLGidyNUbWha4EU7ET2jfJ7UKUVZRhNb5prZxfsJddbzaw Send this multisig info to all other participants, then use make_multisig &lt;info1&gt; [&lt;info2&gt;...] with others' multisig info</p>
<p>This includes the PRIVATE view key, so needs to be disclosed only to that multisig wallet's participants</p>
<p>Copy the entire line</p>
<p>Multisig...bzaw be sure to capture the whole thing when copying. Send this line to person B.</p>
<p>Person B does the same and sends his output to person A. Person B commands:</p>
<p><font color="ffd008">[wallet 48e86K]: prepare_multisig</font></p>
<p>Person B gets the output</p>
<p>MultisigV1ZST26VmNuozbbHL9PeDuqiLDuMLCmaCRxBBLoK7yuxsHXyUiMr2SjxXgnsWrbmVRpghFTtcHEDLDnbPcqdoSuum1bLCFvmoFGrK7z3AtizKPTG96ukb4mzzqPcCD55ZCb1Y8cUL4RipVtcB4YbzZyK5eZdRLxAKi8TvyTD9h3QjVraXs Send this multisig info to all other participants, then use make_multisig &lt;info1&gt; [&lt;info2&gt;...] with others' multisig info This includes the PRIVATE view key, so needs to be disclosed only to that multisig wallet's participants and sends it to person A.</p>
<h4 id="step-2-create-multisig-wallets"><font color="ffd008">Step 2 Create Multisig Wallets</font></h4>
<p>Both person A and person B now have the</p>
<p>Multisig... text from the other one. With that, each of them can create their part of the multisig wallet. Before you proceed, note that the wallet will lose access to the underlying account when converted to multisig. This is not really a problem, since we started with an empty one, and if all goes ok with this step, you won't ever need it unless you want to go through the process again for whatever reason (like HDD died, but you have the seed mnemonic of the underlying account and want to reconstruct the multisig wallet).</p>
<p>Person A commands:</p>
<p><font color="ffd008">[wallet 47HSuD]: make_multisig 2 MultisigV1ZST26VmNuozbbHL9PeDuqiLDuMLCmaCRxBBLoK7yuxsHXyUiMr2SjxXgnsWrbmVRpghFTtcHEDLDnbPcqdoSuum1bLCFvmoFGrK7z3AtizKPTG96ukb4mzzqPcCD55ZCb1Y8cUL4RipVtcB4YbzZyK5eZdRLxAKi8TvyTD9h3QjVraXs</font></p>
<p>and the output will be something like:</p>
<p>2/2 multisig address: 47RGRFeLPT51qvDWuw7SGf57JK7AziAVqYucct8z5yEDQ1XqU8zKEjidWjqPXk7PuHP3MJDN2AJATKy9PH7zaGV7MB8X6CH</p>
<p>Person B commands:</p>
<p><font color="ffd008">[wallet 48e86K]: make_multisig 2 MultisigV1WHyBiEPV5rv3jgU59QUv2ZYTvmN3pwzCL8mp5jTDxkkhRzDjL1T8A2dHTYLmprbUsiLzvPLqRc1GkFHp3mq7dFq6BiE98Ur5cD6P46YYLd5QwD4diqe4VRSiS7GYHATbL4cLGidyNUbWha4EU7ET2jfJ7UKUVZRhNb5prZxfsJddbzaw</font></p>
<p>and the output should be something like:</p>
<p>2/2 multisig address: 47RGRFeLPT51qvDWuw7SGf57JK7AziAVqYucct8z5yEDQ1XqU8zKEjidWjqPXk7PuHP3MJDN2AJATKy9PH7zaGV7MB8X6CH</p>
<p>Now exchange addresses and compare, they must be the same.</p>
<h3 id="receiving"><font color="ffd008">Receiving</font></h3>
<h4 id="step-1-fund-the-multisig-account"><font color="ffd008">Step 1 Fund The Multisig Account</font></h4>
<p>This is simple. Just send to the shared address. You can send multiple times, same like normal wallet. You can use payment ID as well, or generate an integrated address to receive funds.</p>
<p>Best part, whomever is sending the funds won't be able to tell that the address belongs to a multisig wallet since it looks as any other.</p>
<h4 id="step-2-check-multisig-account-balance"><font color="ffd008">Step 2 Check Multisig Account Balance</font></h4>
<p>Just open the wallet and command refresh. Once completed, both persons can verrify that the funds arrived.</p>
<p>Person A commands:</p>
<p><font color="ffd008">[wallet 47HSuD]: show_transfers and can see all incoming transfers.</font></p>
<p>1357156 in 07:50:35 PM 0.100000000000 88ba687dc79a0b39e6de6d0763eda8363d33d9f58ec9a096171bd9a7f1dae873 0000000000000000 - 1357161 in 08:00:18 PM 0.100000000000 d6ac845b9400759525519cdc5d514eb8f5b1d265b24d1c016e75b20ed3b4b7da 0000000000000000 -</p>
<p>Person B can do the same:</p>
<p><font color="ffd008">[wallet 48e86K]: show_transfers and will see the same:</font></p>
<p>1357156 in 07:50:35 PM 0.100000000000 88ba687dc79a0b39e6de6d0763eda8363d33d9f58ec9a096171bd9a7f1dae873 0000000000000000 - 1357161 in 08:00:18 PM 0.100000000000 d6ac845b9400759525519cdc5d514eb8f5b1d265b24d1c016e75b20ed3b4b7da 0000000000000000 -</p>
<h3 id="spending"><font color="ffd008">Spending</font></h3>
<h4 id="step-1-syncronizing-key-images"><font color="ffd008">Step 1 Syncronizing Key Images</font></h4>
<p>Without this step, it will not be possible to create a spending transaction.</p>
<p>Person A commands:</p>
<p><font color="ffd008">[wallet 47HSuD]: export_multisig_info testmp1 where</font></p>
<p>testmp1 can be any filename. The output will be:</p>
<p>Multisig info exported to testmp1</p>
<p>The file</p>
<p>testmp1 will be located in the shell working folder*</p>
<p>Person A sends that file to Person B.</p>
<p>Person B does the same and commands:</p>
<p><font color="ffd008">[wallet 48e86K]: export_multisig_info testmp2 and the output will be:</font></p>
<p>Multisig info exported to testmp2</p>
<p>The file testmp2 will be located in the shell working folder*</p>
<p>Person B sends that file to person A.</p>
<p>Now, they must both import each other's file.</p>
<p>Person A commands:</p>
<p><font color="ffd008">[wallet 47HSuD]: import_multisig_info testmp2 (the wallet will look for it in the shell working folder*) and the output will look like:</font></p>
<p>2 outputs found in testmp2 Height 1357156, transaction &lt;88ba687dc79a0b39e6de6d0763eda8363d33d9f58ec9a096171bd9a7f1dae873&gt;, received 0.100000000000 Height 1357161, transaction &lt;d6ac845b9400759525519cdc5d514eb8f5b1d265b24d1c016e75b20ed3b4b7da&gt;, received 0.100000000000</p>
<p>Person B commands:</p>
<p><font color="ffd008">[wallet 48e86K]: import_multisig_info testmp1 (the wallet will look for it in the shell working folder*) and the output will look like:</font></p>
<p>2 outputs found in testmp1 Height 1357156, transaction &lt;88ba687dc79a0b39e6de6d0763eda8363d33d9f58ec9a096171bd9a7f1dae873&gt;, received 0.100000000000 Height 1357161, transaction &lt;d6ac845b9400759525519cdc5d514eb8f5b1d265b24d1c016e75b20ed3b4b7da&gt;, received 0.100000000000 Multisig info imported</p>
<h4 id="step-2-preparing-spending-transaction"><font color="ffd008">Step 2 Preparing Spending Transaction</font></h4>
<p>Either person A or person B can do this, it doesn't matter. To avoid weird things from happening only do it for 1 transaction at a time.</p>
<p>Person A performs the usual</p>
<p>transfer command:</p>
<p><font color="ffd008">[wallet 47HSuD]: transfer 47wbKEXBGnyHohezMGpD6y2SFNczrSpeSfQgFW5cMxMziFuHpBWM9yjBLJ1iTv31AwN6daPg1QXfRKBJGq2XZDekNqv8gsP 0.15</font></p>
<p>The output will look like:</p>
<p>Unsigned transaction(s) successfully written to file: multisig_arqma_tx*</p>
<p>Check in the folder where you started</p>
<p>arqma-wallet-cli from*. There should be a file named</p>
<p>multisig_arqma_tx.</p>
<p>Send the file multisig_arqma_tx to the person B.</p>
<p>Person B must finish the signature. Person B copies the file to the same folder from where he started (or will start)</p>
<p>arqma-wallet-cli*.</p>
<p>Then, Person B commands:</p>
<p><font color="ffd008">[wallet 48e86K]: sign_multisig multisig_arqma_tx and a prompt will be displayed to allow person B to check the transaction before signing:</font></p>
<p>Loaded 1 transactions, for 0.200000000000, fee 0.015570240000, sending 0.150000000000 to 47wbKEXBGnyHohezMGpD6y2SFNczrSpeSfQgFW5cMxMziFuHpBWM9yjBLJ1iTv31AwN6daPg1QXfRKBJGq2XZDekNqv8gsP, 0.034429760000 change to 47RGRFeLPT51qvDWuw7SGf57JK7AziAVqYucct8z5yEDQ1XqU8zKEjidWjqPXk7PuHP3MJDN2AJATKy9PH7zaGV7MB8X6CH, with min mixin 4. Is this okay? (Y/Yes/N/No):</p>
<p>If ok, answer</p>
<p>Y, and the output will look like:</p>
<p>Transaction successfully signed to file multisig_arqma_tx, txid bb998b00dad0c245b45b975277d9b685592b412fd5fb58b2c1805091418c8b49.</p>
<p>Finally, person B submits the transaction to the network by commanding:</p>
<p><font color="ffd008">[wallet 48e86K]: submit_multisig multisig_arqma_tx and there will be a confirmation prompt:</font></p>
<p>Loaded 1 transactions, for 0.200000000000, fee 0.015570240000, sending 0.150000000000 to 47wbKEXBGnyHohezMGpD6y2SFNczrSpeSfQgFW5cMxMziFuHpBWM9yjBLJ1iTv31AwN6daPg1QXfRKBJGq2XZDekNqv8gsP, 0.034429760000 change to 47RGRFeLPT51qvDWuw7SGf57JK7AziAVqYucct8z5yEDQ1XqU8zKEjidWjqPXk7PuHP3MJDN2AJATKy9PH7zaGV7MB8X6CH, with min mixin 4. Is this okay? (Y/Yes/N/No):</p>
<p>If ok, answer</p>
<p>Y, and the transaction will be sent. The output will look like:</p>
<p>Money successfully sent, transaction: &lt;bb998b00dad0c245b45b975277d9b685592b412fd5fb58b2c1805091418c8b49&gt;</p>
<p>The person B could also send the signed TX to person A, who could then submit it to the network himself.</p>
<p>If you want to make another one, you have to go back to step 1 of spending (sync the key images again).</p>
<p>Note on folders and file locations, as it could create some confusions. The wallet will look for the files and export them to the folder from where it was started, ie where your command prompt / shell was when you called arqma-wallet-cli. It may or may not be the same folder as your actual wallet files or arqma-wallet-cli, depending on how you go about it.</p>
<p>For example, your wallet could be on some USB drive like</p>
<p>f:, and your wallet software on</p>
<p>c:Â and your shell working folder could be</p>
<p>c:.</p>
<p>If you remain in</p>
<p>c:Â with the shell, you could start the wallet by its full path and specify the wallet file location:</p>
<p>c:-wallet-cli.exe --wallet-file f:. In this case, all the import/export stuff would be read/written to</p>
<p>c:Â because that's still your shell's working folder.</p>
<p>It would be probably feel more natural to</p>
<p>cd into the wallet folder. Do</p>
<p>f: to change drive and then</p>
<p>cd f:. Then, simply start the wallet from that location by its full path again:</p>
<p>c:-wallet-cli.exe --wallet-file mywallet. Notice how you don't have to write the full wallet path now as you're already there with your shell. In this case, all the files mentioned above would be written or read from the same folder as the wallet files. -------------------- Typical usage scenarios:</p>
<p>The above are instructions on how to operate the cli wallet with two parties having control of a joint account. Once configured, each party can deposit coins, but both have to exchange signed files to spend from that joint account. So for example, you have a contract with someone, you can put the coins in this joint account for goods and services like an escrow. Both parties have to sign it before there is a transfer complete to the destination account. Which would becoins sent to the seller from the escrow from the buyer. Both parties can see that there are funds from buyer to escrow, and then to the seller. Still, it can be completely private to the outside world unless they are giving up the necessary information to the puiblic. When you send a cryptonote transaction, its a one way, no return trip thing. So, when the money is in escrow joint multisig account, then it's already commited by the buyer to escrow.</p>
<p>It would take both parties to cancel and return the funds to the buyer, or complete the transaction and send the coins to the seller.</p>
<p>The escrow account can also be held by a third party with their own signature also.</p>
<p>That is why you set up a multisig account separate from your main spending wallet. You put funds in there that you know you are going to spend, but can possibly not get back depending on how you word the external contract or make and agreement with a third party or escrow.</p>
<p>----About this docuement. Based on stackexchange.com originally for Monero multisig transfers. Account number references in this example are for monero addresses and not ArQmA addresses, but the commands and syntax format is correct. Tested and verfied that this works exactly as described with ArQmA CLI wallet 0.2.2 Devil's Gate. 01/25/2019. Standard Disclaimer: The ArQmA Project is not responsible for users misunderstanding the nature of user's transactions and their intended use. This tutorial is not inclusive of every combination to the real world. Seek advice with your administrator or escrow agent for exact contract wording outside of ArQmA's financial private cryptocurrency technology.</p>
<p>-eof</p>
