# Storage Power Actor

The ActorCode for storage power built-in actor is *hex*"0004" which will be used to call methods in storage power actor.

### CreateMiner

```
createMiner(params: CreateMinerParams) -> Result<CreateMinerReturn, ActorError>
```

Create a new miner for the owner address and worker address.

**Params**:

+ `uint` CreateMinerMethodNum = 1173380165;
+ CreateMinerParams
  + `bytes` Owner: the address of the owner
  + `bytes` Worker: the address of the workder
  + `RegisteredPoStProof` WindowPoStProofType: the type of RegisteredPoStProof
  + `bytes` Peer: peerID
  + `bytes[]` Multiaddrs: the multi-address which is used to control new created miner

**Results**:

+ CreateMinerReturn

  + `bytes` The canonical ID-based address for the actor.

  + `byte`: A more expensive but re-org-safe address for the newly created actor.




### NetworkRawPower

Returns the total raw power of the network.

**Params**:

+ `uint`  NetworkRawPowerMethodNum = 931722534;
+ null

**Results**:

+ `int256` : the raw storage power of the whole network.

**Examples**:

```
Actor.call(PowerTypes.NetworkRawPowerMethodNum, PowerTypes.ActorCode, raw_request);
```

### MinerRawPower

Returns the raw power claimed by the specified miner, and whether the miner has more than the consensus minimum amount of storage active.

**Params**:

+ `uint` MinerRawPowerMethodNum = 3753401894;
+ MinerRawPowerParams
  + `uint64` Miner : Miner ID


**Results**:

+ `int256`: the row power of the miner
+ `bool`: if the miner power meets the minimum for consensus

**Examples**:

```
Actor.call(PowerTypes.MinerRawPowerMethodNum, PowerTypes.ActorCode, raw_request);
```

### MinerCount

Returns the total number of miners created, regardless of whether or not they have any pledged storage.

**Params**:

+ `uint` MinerRawPowerMethodNum = 3753401894;
+ null

**Results**:

+ `uint64`: the count of the miners that the caller address has

**Examples**:

```
Actor.call(PowerTypes.MinerCountMethodNum, PowerTypes.ActorCode, raw_request);
```

### MinerConsensusCount

Returns the total number of miners that have more than the consensus minimum amount of storage active.

**Params**:

+ `uint`  MinerConsensusCountMethodNum = 196739875;
+ null

**Results**:

+ `uint64`: the count of the miners meet the consensus minimum that the caller address has.

**Examples**:

```
delegate(PowerTypes.MinerConsensusCountMethodNum, PowerTypes.ActorCode, raw_request);
```

