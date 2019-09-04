# Account script

An **account script** is a [RIDE script](/ride/script.md) that has the following directives:

``` ride
{-# CONTENT_TYPE EXPRESSION #-}
{-# SCRIPT_TYPE ACCOUNT #-}
```

An account script is attached to the [account](/blockchain/account.md) with a [set script transaction](/blockchain/transaction-type/set-script-transaction.md).

An account with the account script attached to it is called a [smart account](/blockchain/smart-account.md). Only one script can be attached to an account.
