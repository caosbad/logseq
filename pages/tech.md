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
router offor send transactions with different trx types
![send](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/595x698/5366dc505b026b98a24eff6e4ddf47c5/image.png)
####### sendTransaction
####### sendGetTransactionStatus
###### @onflow/sdk-resolve 
:PROPERTIES:
:id: 5fe0532c-59fd-4df6-a11e-b7baaadc3447
:END:
resolve args by pipe and return ix before send 
![reslove args](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/453x178/ced5a8e22da1b51779d6f00b9e6b8e56/image.png)
####### resolveCadence 
handle cadence with string or function `ix.message.cadence`
####### resolveArguments
check args with `cast`  and update `ix.arguments` 
``` javascript
 for (let [id, arg] of Object.entries(ix.arguments)) {
    ix.arguments[id].asArgument = cast(arg)
  }
```
####### resolveAccounts
packages/sdk-resolve-accounts/src/index.js
######## accountCanFulfillRoles
check account's role with three types `proposer` `payer` `authorizer`
######## invariant
asserter for accounts check and role check
######## enforceResolvedAccounts
iterator reslove accounts with their reslover fumction
######## dedupeResolvedAccounts
 iterator calc `cid` for accounts and merge the same cid account, instead `cid` of `tempId` and update `ix.authorizations`
#########
```
`const cid = `${account.addr}|${account.keyId}`
```
#########
```
ix.authorizations = ix.authorizations.map(d =>
      d === account.tempId ? cid : d
    )
```
####### resolveRefBlockId(opts)
check ref block id or get getLatestBlock and return
packages/sdk-resolve-ref-block-id/src/index.js
######## getRefId
set the latestBlock  value to `ix.message.refBlock`
####### resolveSignatures
######## collateSigners
 split signers with two type and return two array
######### insideSigners
######### outsideSigners
######## mutateAccountsWithSignatures
####### resolveValidators
###### sdk-send
####### sendFunction  —— use flow.json config send function or ((5fe052d2-d798-4209-b4e3-7f1e969d72a1))
####### resolveFunction —— use flow.json config resolve function or ((5fe0532c-59fd-4df6-a11e-b7baaadc3447))
####### pipe(interaction(), args)
:PROPERTIES:
:id: 5fe0523b-1f2a-4442-9982-67a43d70187c
:END:
###### protobuf
###### decode
###### encode
###### interaction
packages/interaction/src/interaction.js
####### constants
######## IX tag 
![interaction constants](https://trello-attachments.s3.amazonaws.com/5fccc55f9c47787592af6b96/518x340/6b86c4bfb3e65f2e000c2c649a31dd9f/image.png)

```typescript
const makeIx = (wat) => (ix) => {
  ix.tag = wat
  return Ok(ix)
}
```
######## IX status
######## IX kind
######### ACCOUNT
######### PARAM
######### ARGUMENT
####### struct of IX
####### validate funcs
####### pipe && recPipe
######## handler IX as funcs input and exec by step
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
### Balancer
#### balancer-exchange
##### batchSwapExactIn
src/stores/Proxy.ts
