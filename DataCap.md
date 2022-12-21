# DataCap Actor

DataCap Actor is responsible for DataCap token management.  The ActorCode for DataCap actor is *hex*"0007" which will be used to call DataCap actor APIs.

### Name

```
func Name() String {}
```

Return the name of DataCap token which is 'DataCap'.

`Unit ` NameMethodNum : 48890204

**Params**:

+ null

**Results**:

+ `String` : DataCap

### Symbol

```
func Symbol() String {}
```

Return the symbol of DataCap token which is 'DCAP'.

`unit` SymbolMethodNum: 2061153854

**Params**:

+ null

**Results**:

+ `String` : DCAP

### TotalSupply

```
func TotalSupply() TokenAmount {}
```

Return the total supply of DataCap token.

`uint` TotalSupplyMethodNum: 114981429.

**Params**:

+ null

**Results**:

+ `int256` TokenAmount - Total DataCap token supply.

### Balance

```
func TotalSupply(params Address) TokenAmount {}
```

Return the DataCap token balance for the wallet address.

`unit` BalanceOfMethodNum: 3261979605.

**Params**:

+ `bytes` Address: the wallet address.

**Results**:

+ `int256` TokenAmount - the DataCap token balance for the specified address.

### Transfer

```
func Transfer(params TransferParams) TransferParams {}
```

Transfers DataCap tokens from caller address to an address.

`uint`  TransferMethodNum = 80475954;

**Params**:

+ `struct` TransferParams
  + `bytes` to: the address to receive DataCap.
  + `int256` amount: A non-negative amount to transfer.
  + `bytes` operator_data: Arbitrary data to pass on via the receiver hook.


**Results**:

+ `struct` TransferParams
  + `int256` from_balance: the balance of from_address.
  + `int256` to_balance:  the balance of to_address.
  + `bytes` recipient_data: data returned from receive hook.


### TransferFrom

Transfers DataCap tokens between from from_address to to_address.

**Params**:

+ `uint`  TransferFromMethodNum = 3621052141.
+ `bytes` TransferFromParams : raw_request
  + `bytes` from: the address to send DataCap.
  + `bytes` to: the address to receive DataCap.
  + `int256` amount: A non-negative amount to transfer.
  + `bytes` operator_data: Arbitrary data to pass on via the receiver hook.


**Results**:

+ `int256` FromBalance: the balance of from_address.
+ `int256` ToBalance:  the balance of to_address.
+ `int256` Allowance: the remaining allowance of owner address.
+ `bytes` RecipientData: data returned from receive hook.

**Examples**:

```
Actor.call(DataCapTypes.TransferFromMethodNum, DataCapTypes.ActorCode, raw_request);
```

### IncreaseAllowance

Increase the DataCap token allowance that an operator can control of an owner's balance by the requested amount.

**Params**:

+ `uint`  IncreaseAllowanceMethodNum = 1777121560;
+ `IncreaseAllowanceParams`
  +  `bytes` operator : the  wallet address of the operator.
  +  `int256` increaseAmount: increase DataCap token allowance amount.


**Results**:

+ `int256` the total Allowance amount of the operator address.

**Examples**:

```
Actor.call(DataCapTypes.IncreaseAllowanceMethodNum, DataCapTypes.ActorCode, raw_request);
```

### DecreaseAllowance

Decrease the DataCap token allowance that an operator controls of the owner's balance by the requested amount.

**Params**:

+  `uint` DecreaseAllowanceMethodNum = 1529376545;
+ `DecreaseAllowanceParams`
  +  `bytes` operator : the  wallet address of the operator.
  +  `int256` increaseAmount: the decreased DataCap token allowance amount.

**Results**:

+ `int256` the total Allowance amount of the operator address.

**Examples**:

```
Actor.call(DataCapTypes.DecreaseAllowanceMethodNum, DataCapTypes.ActorCode, raw_request);
```

### RevokeAllowance

Revoke the DataCap Token allowance from the operator and set the operator's allowance in behave of owner address to 0.

**Params**:

+ `uint` RevokeAllowanceMethodNum = 2765635761;
+ `RevokeAllowanceParams` 
  +  `bytes` operator : the  wallet address of the operator.


**Results**:

+ `int256`: the old Allowance amount of the operator address.

**Examples**:

```
Actor.call(DataCapTypes.RevokeAllowanceMethodNum, DataCapTypes.ActorCode, raw_request);
```

### Burn

Burns an amount of token from the owner/caller address, decreasing total token supply.

**Params**:

+ `uint` BurnMethodNum = 1434719642;
+ BurnParams
  + `int256` Amount: the amount the DataCap token to be burned


**Results**:

+ `int256` : the updated DataCap token balance of the caller address

**Examples**:

```
Actor.call(DataCapTypes.BurnMethodNum, DataCapTypes.ActorCode, raw_request);
```

### BurnFrom

 Burns an amount of token from the specified address (owner address), decrease the allowance of operator/caller, and decrease total token supply.

**Params**:

+ `uint` BurnFromMethodNum = 2979674018;
+ BurnFromParams
  + `bytes` Owner : the  wallet address of the owner.
  + `int256` Amount: the amount of DataCap token to be burned.


**Results**:

+ `bytes` : the  wallet address of the owner.
+ `int256` : the new balance of owner wallet.

**Examples**:

```
Actor.call(DataCapTypes.BurnFromMethodNum, DataCapTypes.ActorCode, raw_request);
```

### Allowance

Return the allowance between owner and operator address.

**Params**:

+ `uint` AllowanceMethodNum = 4205072950;
+ AllowanceParams
  + `bytes` Owner : the  wallet address of the owner.
  + `bytes` Operator : the  wallet address of the owner.


**Results**:

+ `int256` : the  allowance that an operator can control of an owner's balance.

**Examples**:

```
Actor.call(DataCapTypes.AllowanceMethodNum, DataCapTypes.ActorCode, raw_request);
```
