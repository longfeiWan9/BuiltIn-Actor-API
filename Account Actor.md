## Account Actor

The account actor is responsible for user account. If you want to call methods in account actor in your smart  contract, you need to specify method number of the method you want to invoke.

#### **AuthenticateMessage**

```
func AuthenticateMessage(params AuthenticateMessage) EmptyValue()
```

Authenticates whether the provided signature is valid for the provided message. 

`uint` AuthenticateMessageMethodNum = 2643134072;

**Params**:

+  `struct` AuthenticateMessageParams

  + `bytes` AuthenticateMessageParamsSignature: should be a raw byte of signature, NOT a serialized signature object with a signatureType.

  + ` bytes` Message:  The message which is signed by the corresponding account.


**Results**:

+  `EmptyValue`

#### **UniversalReceiverHook** 

```
func AuthenticateMessage() EmptyValue()
```

Whenever the account receives transfers, this method will be invoked.

`uint`  UniversalReceiverHookMethodNum = 3726118371;

**Params**:

+ null

**Results**:

+ `EmptyValue`: always succes
