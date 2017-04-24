## Factom Binaries

**Note: Deployment of v0.4.1.0 is taking longer than expected.  Until further notice, use v0.4.0.3 which can be installed with these commands after installing from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md).**
```
cd $GOPATH/src/github.com/FactomProject/factomd
git checkout v0.4.0.3
glide install
go install -v -ldflags "-X github.com/FactomProject/factomd/engine.Build=`git rev-parse HEAD`"
```


Install for:

| OS | Factomd Installer | Enterprise Installer | factomd sha256sum | Enterprise sha256sum |
|----|-----|-----|-----|-----|
| Windows 64bit | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-setup-amd64.exe](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup-amd64.exe) | 459b5efd2b531b5190b92527a504a8439576c3ced1754f35e8f2fd73b138a1f2 | 1e11d103da7e7b2d93c5b65c2bca9eababd08975b349b633d49681e701b18c5d |
| Windows 32bit | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | | 08eba516046d6c5fa174080e28a6a61816962fe08fb32343a222d4a3e0aa05ab | |
| Mac | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-setup.dmg](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup.dmg) | 3dea2d3c1b7e91e19acc11e5535806af2a2ea1bd1fcc409c07deced60e6e148a | 6ad2c06b05656b0fcfae75a8b4919ed3921d073d06c58698475de2a85f4d55f5 |
| Linux (Ubuntu/Debian) 64bit | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-setup-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup-amd64.deb) | | 29babb2a4cfb8f0f250a25bfd21ecfe34c5866d53a91a17c8a101570033252a1 |
| Linux (Ubuntu/Debian) 32bit | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | | | |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-linux.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-linux.zip) | | ba0ce2307ecaf83001ddff4b92036882e9af8036b3ee755159a2f664b3a15dfb |


Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

Source code archive: pending

## Release notes for v0.4.1.0

This is a required upgrade.  Older versions of software will not download new blocks from the network.

- Large fix for network connection problems
- Prioritized Directory Block and Factoid Block downloading over Entry downloading.  This is apparent when viewing the control panel 1st and 2nd pass.
- Limitations on outgoing peers
- reduce outgoing message traffic
- add computed balance messaging to prevent out-of sync balances (thanks to [34ro](https://github.com/34ro) for reporting the error)
- add prometheus logging for nice graphana performance graphs
- expose API for checking leader status
- add API call to get network transaction rate
- Database consistency fixes
- updated leveldb to include upstream fixes


Known issues:
- If an earlier version of factomd was run, it may have corrupted your local database.  If you are seeing panics as you are booting the latest factomd, the safest fix is to delete (or rename) your ~/.factom/m2/main-database folder
- On machines with 4GB or less of RAM, memory spikes have been observed which cause the OS to stop factomd while downloading the blockchain.


## Release notes for v0.4.0.3

- This latest update fixes some consistency bugs.  It is more aggressive in filling in gaps introduced when synching the blockchain with marginal network connections.  This fixes some problems people were seeing with missing entries. (factoid transactions did not fall under this bug)
- This updates to Golang 1.8, which gives better garbage collection.
- Added some stabilization of the network connectivity.


## Release notes for 0.4.0.2

- Resolve "too many files" error

On Linux and Mac, factomd would crash due to using too many open files.  This bug has been solved, and factomd no longer needs the adjust the ulimit in order to work.

- Resolve Windows Database Problem

Enterprise Wallet and factom-walletd on some Windows systems would not cache factoid transactions.  This solves the User Map Restriction bug.

- Networking more Resiliant

Timeouts for network connections have been increased.  This gives an incremental improvement for some stalling problems that factomd nodes have been seeing.

- Lower CPU usage

Idle time CPU usage has been decreased for times after factomd boot and syncs.

- Right Click in Wallet

Now the Enterprise Wallet supports right clicking for copy/pasting etc.



- Workarounds

One known issue is that factomd does not keep up with new blocks if it needs to download many blocks after starting.  The workaround is to start factomd, allow it to download all the blocks so far created.  Close factomd (ctrl+c) and restart it.  it should keep up with blocks after the second start.


The blockchain is fairly large and the P2P sync code is not fast.  To expedite the startup time, the first 70k blocks can be downloaded via http.
 https://www.factom.com/assets/site/factom_bootstrap.zip
 SHA256: 2d4d256c337cdabc8f75aa71180c72129f807c365c78356471350ac1e0a4faed

Extract the zip file to your home directory. It will create files in the location: ~/.factom/m2/main-database/ldb/MAIN/factoid_level.db/   Compressed the blockchain is currently about 5 GB and uncompressed is over 9 GB.


factomd is much slower to start on a spinning hard drive, compared to a solid state drive.  It is recommended to save the blockchain on a solid state drive.





