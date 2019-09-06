# Proof-of-Play consensus the gaming chains

- a new block is generated when a game event occurs
- data is serialized into a well-known array instead of objects to reduce the amount of traffic transmitted to other nodes
- game nodes interact with each other using sockets
- at the socket level we use additional compression of serialized data
- separate protocol for receiving static information and query execution on JSON/RPC
- storage LevelDB keys/values
- real-time gaming events are broadcast via sockets in DAPPs
- optional: to develop a load balancer, sharding
- solve the problem of nat using udp through the stun


blockData: 0xblockHeight

- prevBlockHash
- blockHash
- blockTime
- generatorId: address
- payload: [txsData]

txsData:[]

- txtype: bet/play (0/1)
- txIdSTH: hash
- gameId: hash-md5
- amount: sth
- timestamp: unixtime
- senderId: address
- recipientId: address
- gameValue: 0/1 hash
- senderSig: from sth
- affiliateID: address
--------------------------------
- txType: result (2)
- txIdSTH: hash
- gameId: hash-md5
- amountWin: sth
- timestamp: unixTime
- senderId: address
- winnerId: address
- affiliate: {
    - accountId: address
    - amount: sth
}
- playerBet: {
    - accountId: address
    - blockId
    - txIndex
    - value
    - amount
}
- playerPlay: {
    - accountId: address
    - blockId
    - txIndex
    - value
    - amount
}
- gameResult: 0/1

