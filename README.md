# About

`tss-server` is an implementation of [tss-lib](https://github.com/bnb-chain/tss-lib) and it handles `keygen`, `reshare` and `sign` operations.

# Usage

## Keygen

Use below command to start keygen server.

```sh
cd cmd/mpc_keygen
go run main.go -server :8080 -meID A -partyIDs "A B C" -threshold 2 -shareDir /tmp/mpc
```

Use below command to start keygen client.

```sh
cd cmd/mpc_keygen
go run main.go -url ws://localhost:8080 -meID B -partyIDs "A B C" -threshold 2 -shareDir /tmp/mpc
```

## Reshare

Use below command to start reshare server.

```sh
cd cmd/mpc_keygen
go run main.go -reshare -server :8080 -url ws://localhost:8080 -meID A -partyIDs "A B C" -threshold 2 -meIdNew A2 -partyIDsNew "A2 B2 C2 D2" -thresholdNew 3 -shareDir /tmp/mpc
```

Use below command to start reshare client.

```sh
cd cmd/mpc_keygen
go run main.go -reshare -url ws://localhost:8080 -meID B -partyIDs "A B C" -threshold 2 -meIdNew B2 -partyIDsNew "A2 B2 C2 D2" -thresholdNew 3 -shareDir /tmp/mpc
```
