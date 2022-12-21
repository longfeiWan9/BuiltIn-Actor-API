# Storage Power Actor

The ActorCode for storage power built-in actor is *hex*"0004" which will be used to call methods in storage power actor.

### CreateMiner

```go
func CreateMiner(params CreateMinerParams) CreateMinerReturn {}
```

Create a new miner for the owner address and worker address.

`uint` CreateMinerMethodNum = 1173380165;

**Params**:

+ `struct` CreateMinerParams
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

```go
func NetworkRawPower() NetworkRawPowerReturn {}
```

Returns the total raw power of the network.

`uint`  NetworkRawPowerMethodNum = 931722534;

**Params**:

+ null

**Results**:

+ `struct` NetworkRawPowerReturn
  + `int256` : the raw storage power of the whole network.


### MinerRawPower

```
func MinerRawPower(params MinerRawPowerParams) MinerRawPowerParams {}
```

Returns the raw power claimed by the specified miner, and whether the miner has more than the consensus minimum amount of storage active.

`uint` MinerRawPowerMethodNum = 3753401894;

**Params**:

+ MinerRawPowerParams
  + `uint64` Miner : Miner ID

**Results**:

+ `struct` MinerRawPowerParams

  + `int256`: the row power of the miner

  + `bool`: if the miner power meets the minimum for consensus


### MinerCount

```
func MinerCount() MinerCountReturn {}
```

Returns the total number of miners created, regardless of whether or not they have any pledged storage.

`uint` MinerRawPowerMethodNum = 3753401894;

**Params**:

+ null

**Results**:

+ `struct	` MinerCountReturn
  + `uint64`: the count of the miners that the caller address has


### MinerConsensusCount

```
func MinerConsensusCount() MinerConsensusCountReturn {}
```

Returns the total number of miners that have more than the consensus minimum amount of storage active.

**Params**:

+ `uint`  MinerConsensusCountMethodNum = 196739875;
+ null

**Results**:

+ `struct` MinerConsensusCountReturn
  + `uint64`: the count of the miners meet the consensus minimum that the caller address has.


