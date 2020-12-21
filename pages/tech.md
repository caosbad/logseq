---
title: Tech
---

## web3
### Flow
#### Js-sdk
##### Package analisis
###### fcl main file  
packages/fcl/src/fcl.js
####### auth
![auth](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/505x222/cf6ad803cccfd69501cd183bac6c4753/image.png)
####### modules import
 ![modules](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/577x461/98faad85fa771dfeea66278ea651a319/image.png)
###### transaction
@onflow/sdk-build-transaction
###### config
recursive load `flow.json` in folder
###### onflow/send
:PROPERTIES:
:id: 5fe052d2-d798-4209-b4e3-7f1e969d72a1
:END:
router of send transactions with different trx types
![send](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/595x698/5366dc505b026b98a24eff6e4ddf47c5/image.png)
###### @onflow/sdk-resolve
:PROPERTIES:
:id: 5fe0532c-59fd-4df6-a11e-b7baaadc3447
:END:
#######
###### sdk-send
####### sendFunction  —— use flow.json config send function or ((5fe052d2-d798-4209-b4e3-7f1e969d72a1))
####### resolveFunction —— use flow.json config resolve function or ((5fe0532c-59fd-4df6-a11e-b7baaadc3447))
####### pipe
####### interaction
###### decode
###### interaction
packages/interaction/src/interaction.js
#######
###### utll-address
###### util-template
#######
###### account
###### latestBlock
###### script
###### ping
###### getAccount
##### How [FCL](https://github.com/onflow/flow-js-sdk) interact with Flow
###### fcl.getAccount()
###### fcl.currentUser()
####### subscribe()
###### fcl.authenticate()
###### fcl.unauthenticate()
#### wallet-provider-spec
