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
