Transaction is not supported with NoSQLs.
To achieve this:

2 phase approach:
- Prepare
- Commit

instead of 
```
ACCOUNT
{id: 0, balance: 100}
```

```
ACCOUNT
{id: 0, balance: 100, transactions:[]}

TRANSACTION
{
	id:
	state: // NEW, COMMITED, ROLLBACK
	timestamp:
	amount:
	src:
	dst:
}
```

state will be 'ROLLBACK' if its not 
// WHERE TO CHECK FUNDS?
```
transfer(){
	prepareTransfer()
	commitTransfer()
}

prepareTransaction(){
	createTransactionObject()
	makeBalanceChangesAndAddTransactionToTransactions()
}

commitTransfer(){
	setTransactionStateToCommit()
	deleteSuccessTransaction()
}


// this function is idempotent.
// if it fails on removeTransactionFromAccount phase,
// deleteSuccessTransaction(txnId) will work eventually
// with cleanupTransactions()

// lets say removeTransactionFromAccount succeed for 
// only one account, when this function recalled,
// only the second account will be effected.
deleteSuccessTransaction(txnId){
	removeTransactionFromAccounts(txnId)
	removeTransaction(txnId)
}

rollbackTransaction(txnId){
	removeTransactionFromAccountsAndGiveMoneyBack(txnId)
	revomeTransaction(txnId)
}


// maybe you think that deleteSuccessTransaction()
// is redundant,
// however in commitTransfer()
// setTransactionStateToCommit() can fail.
// which will lead to deleteSuccessTransactions() to not
// be executed.
cleanupTransactions(){
	deleteSuccessTransactions() //where status=Committed
	setExpiredsToRollbackStatus()
	rollbackTransfer() //where status=Rollback 
}




```

