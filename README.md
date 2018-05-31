## Factom Binaries

The latest version of Factom is version **5.0.0**, released **1 May, 2018**

The latest version of Enterprise Wallet is Version **0.2.1**, released **16 October, 2017**

Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

![Enterprise Wallet](img/enterprise.png)

### Factom Enterprise Wallet

| OS | Enterprise Installer | sha256sum |
|----|-----|-----|
| Windows 64bit | [enterprise-wallet-setup-amd64.exe](https://github.com/FactomProject/distribution/releases/download/v0.4.2.11/enterprise-wallet-setup-amd64.exe) | 6b6248da07a3a3d7a60480f99013b0e35f09a3ace484569bb24f44730d61ff70 |
| Mac |  [enterprise-wallet-setup.dmg](https://github.com/FactomProject/distribution/releases/download/v0.4.2.11/enterprise-wallet-setup.dmg) | 4af4a6ded4a74e8e38e194d9648248314d8671ed381e35f0e969b87625f1d601 |
| Linux (Ubuntu/Debian) 64bit | [enterprise-wallet-setup-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.2.11/enterprise-wallet-setup-amd64.deb) | 22c7bce469e5f2d1051a4d9c6ad5d94cf2b79ce3f7cf6073f7e971fb692b44e5 |
| Linux (Redhat/Centos) | [enterprise-wallet-linux.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.2.11/enterprise-wallet-linux.zip) | ce0ab4bf4d446bf5a3c5b0b25d68719d6dffa1005ad31781a0da3719c088111f |


#### Release notes for v0.2.1
- [new] added splash screen displaying license

Known issue:
If the zip based linux wallet is run as a fresh install, a blank white screen is shown on startup.

#### Release notes for v0.2.0.0
- [new] added a password protected, encrypted wallet option
- [new] revamped the seed backup and restore processes, no longer exposing their 12 words on the user's hard drive
- [new] a fresh coat of paint! Cleaned up portions of the UI

See our [blog post](https://www.factom.com/blog/encrypted-enterprise-wallet) for details.

#### Release notes for v0.1.3.1
- [fix] Now able to enter a "." character to increase precision of a factoid sending transaction.

#### Release notes for v0.1.3
- [fix] An error regarding the wallet's sync status was showing despite the wallet saying 100% synced. This message would only go away when factomd's second pass hit 100%. This has been rectified.
- [fix] The screen appearing blank/freezing when editing an address has been fixed. All addresses will have special characters in their names replaced with '_'
- [new] The courtesy remote node has a new domain, all users using factomd-live.cloudapp.net will automatically be updated to courtesy-node.factom.com.
- [new] The courtesy remote node will now be the default blockchain target.  This will help new users with getting started.

#### Release notes for v0.1.2
- GUI now remains responsive with slow API responses




### Factom Command Line Interface Programs

![Factom CLI apps](img/factomd.png)

| OS | Factomd Installer | sha256sum |
|----|-----|-----|
| Windows 64bit | [FactomInstall-amd64.msi](https://github.com/FactomProject/distribution/releases/download/v5.1.0/FactomInstall-amd64.msi) | 39cf99ca095d382060130c9c6bcd1d4e1ff0fb12214db3a76f1ed32e9722e244 |
| Windows 32bit | [FactomInstall-i386.msi](https://github.com/FactomProject/distribution/releases/download/v5.1.0/FactomInstall-i386.msi) | 7ad164f25f58c6e04fe0b691631ef64861ba16c8a4f4e0b3400edf7b13ca5d32 |
| Mac | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md) |  |
| Linux (Ubuntu/Debian) 64bit | [factom-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v5.1.0/factom-amd64.deb) | 6598a6ac28cb88f08dd17d6ac414f5ee56198e99d42323d8a85084ebeb455c0e |
| Linux (Ubuntu/Debian) 32bit | [factom-i386.deb](https://github.com/FactomProject/distribution/releases/download/v5.1.0/factom-i386.deb) | 13377bf40468d409c87bdb1865d38734ce7f130759f26a30d8c6ee62f3a3295d |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md) | |


Source code archive: [factom_source_v5.1.0.zip](https://github.com/FactomProject/distribution/releases/download/v5.1.0/factom_source_v5.1.0.zip)

## Release notes for 5.1.0

- [new] Added broadcast to all peers for election messages to make them more reliable
- [new] Added ability for the Authority Set Majority to correct coinbase errors during settling period
- [new] Lowered boot time CPU by not calculating the balancehash while loading from disk (Thank you AlexanderSupersloth)

- [fix] Fixed a bug where an malicious p2p message could cause an Authority Server to panic
- [fix] Set default fault timeout to 120 seconds
- [fix] Tagged incoming p2p messages to prevent automatic rebroadcast
- [fix] Suppressed duplicate sending of commit from a leader, correctly send out a reveal instead
- [fix] Updated control panel and API to show 100% sync when block is saved
- [fix] Removed trimming of the process list during faulting to reduce errors during faults
- [fix] Fixed an elections out of bound panic
- [fix] Suppressed error with nil messages panicking factomd nodes (Pokemon bug)

## Release notes for 5.0.0
**This is a required upgrade.**  Older versions of software will not download new blocks from the network.

- [new] Added new more reliable faulting algorithm
- [new] Added coinbase output to Authority Servers
- [new] Added command line option for config file location
- [new] Added `exclusive_in` flag to limit incoming p2p connections
- [new] Updated Identity and Authority structures, needing a full chain rescan for updated savestate.
- [fix] Fixed potential race condition in filter
- [fix] Improved peer error handling
- [fix] Included many other stability updates

## Release notes for 0.4.2.22
- [fix] Fixed potential deadlock in validation loop
- [fix] corrected bug where commits were not following efficient control flow

## Release notes for 0.4.2.21
- [new] Networking package is now compatible with Logstash / Elastic Search 
- [new] Reduced overhead when loading large Entry Blocks
- [new] Reduced overhead when using Control Panel with large Directory Blocks

## Release notes for 0.4.2.20
- [new] Ensured compatability with Golang 1.10
- [new] Stopped processing messages before loaded from database finished
- [fix] Reduced the number of missing message requests sent to peers
- [fix] Fixed race condition with API

## Release notes for 0.4.2.19
- [new] Sped up loading EC Block with many (thousands) of Commits per block
- [new] Refactored to use less CPU when downloading blockchain
- [fix] Hold Entries which cannot yet be added to blockchain

## Release notes for 0.4.2.18
- [new] Updated console to output to file
- [new] Added DNS resolution to seed and peers file lookups
- [fix] Resolved rare panic during network restart
- [fix] Fixed condition where valid acknowledgements were discarded unnecessarily
- [fix] Reduced the number of times missing messages are asked for

## Release notes for 0.4.2.17
- [new] Add AdminID type to Admin Block API response

## Release notes for 0.4.2.16
- [new] Save progress between boots for the 2nd pass (Entry verification)
- [fix] Check the Entry's content exists in the database not just the key.

## Release notes for 0.4.2.15
- [new] Cached the marshaled objects to save CPU/RAM
- [fix] Corrected bug where under heavy traffic, Entries were prevented from being matched with a Commit

## Release notes for 0.4.2.14
- [fix] Prevented duplicate Entries in edge cases
- [fix] Prevented Entries from flooding over the network without Commits

## Release notes for 0.4.2.13
- [new] Added generic key-value store accessors to database
- [new] Added ability to set which blockheight to begin verifying Entries from on the command line for the 2nd pass
- [fix] Removed spurious errors complaining about process list duplicates

## Release notes for 0.4.2.12
- [new] Switched to a logging package compatible with Logstash / Elastic Search
- [fix] Fixed case where control panel was not displaying the ChainID
- [fix] Added extra check for replayed messages on startup
- [fix] Remove unhelpful data from heights API response
- [fix] Eliminated edge case where Chain could be created with incorrect external ID's (ExtIDs)
- [fix] Changed capitalization of Transaction, EC block, and Pending Entry API responses
- [fix] Updated dependencies of various included projects

## Release notes for v0.4.2.11
- [fix] Status call returned error messages when factomd was booting.
- [fix] Refactor unreachable code paths for messages during node startup.

## Release notes for v0.4.2.10
- [fix] Reconfigured internal handling of API processing JSON fields to ensure consistency
- [fix] Internal state hash now reports accurately when used with savestate
- [fix] Improved efficiency by recalculating block state only once per block
- [new] Expanded automated test coverage over more error conditions

## Release notes for v0.4.2.9
- [new] we are now fully golang 1.9 compatible!
- [new] added -l flag on factom-walletd to enable use of level db - this is suggested for wallets with hundreds or more addresses
- [fix] fixed bug in compose-chain API call of factom-walletd to now give accurate feedback
- [fix] fixed bug handling stdin inputs seen when run in docker
- [fix] updated the GetPendingEntries, GetPendingTransactions to return standardized outputs

## Release notes for v0.4.2.8
- [new] Added ability to suppress raw data when printing blocks with -r flag
- [new] Shifted to CircleCI for automated testing.
- [fix] Updated Pending Entries duplicate checking

## Release notes for v0.4.2.7
- [new] added FACTOM_HOME environment variable or -factomhome flag for .factom directory
- [fix] reduced load on api of factom-walletd under heavy traffic
- [fix] updated savestate to correct potential balance corruption
- [new] improved authority management code in factomd
- [new] added config option -exp for enabling profiling from non-localhost
- [new] update Entry Credit Block API response
- [fix] correct a printout for negative numbers in factom-cli

## Release notes for v0.4.2.6
- [fix] better handling of Chain Heads between creation and when an Entry Block is made
- [fix] ignore duplicate commits which pay for a disallowed duplicate reveal
- [fix] resolved a bug where more commits could be acknowledged than the net Entry Credits should have allowed
- [fix] remove CPU overload when factomd is run in container with "-nosim=true" flag
- [new] framework for supporting additional plugins
- [new] add support for logrus for better log handling
- [new] add additional Prometheus instrumentation across various functions
- [new] add new API calls "admin-block", "factoid-block", "entrycredit-block" which output unmarshaled versions of those blocks
- [new] add "ack" api call which takes a ChainID, setting the stage to accommodate nodes that only download some chains

## Release notes for v0.4.2.5
- [new] Added 'current-minute' API to check status of factomd node, enabling faster detection of stalls
- [new] Added addresses of inputs and outputs of factoid transactions to 'pendingtransactions' API and factom-cli call
- [new] Better logging infrastructure for debugging at scale
- [fix] Stop leaders from stalling when restarting after a fault

## Release notes for v0.4.2.4
- [fix] Don't save unverified ancillary data received from a misbehaving peer
- [new] Create utility to fix corrupted database chain heads
- [fix] Immediately flush DBstates that will never become valid
- [fix] Improve order of operations when saving DBstates with an incomplete process list

## Release notes for v0.4.2.3
- [Fix] Fixed a bug which prevented nodes from processing messages following initial blockchain download.
- [Fix] Speedup boot while synching by ignoring messages which won't affect the state.
- [Fix] Now discard dbsig messages which will never become valid, and handle potential collisions better.
- [Fix] Handle EOM messages better with an invalid signature.
- [New] Chain creation in wallet API now no longer forces user calculation of the ChainID.
- [New] Add more historical checkpoints.
- [New] Protect users from paying too many entry credits for an entry.

## Release notes for v0.4.2.2
- Fast bootup mode is now enabled by default.  Factomd will complete the startup process faster after booting with a previously downloaded blockchain.  (To disable this feature, start factomd with -fast=false)
- The P2P connection is now less likely to be dropped with low numbers of peers.
- Entry acknowledgement feedback is now more likely to succeed between minute 0 and 1 of block creation.
- Chain creation acknowledgement feedback is now more likely to give timely results
- More instrumentation of the API accessors
- more fidelity of loading metrics from the database

## Release notes for v0.4.2.1
- This is a feature preview of the fast bootup mode.
- Upgrade is only needed to try the new mode.
- With this version, when booting after downloading the blockchain, factomd will save most of the work it does when starting.  When starting again, it will fully startup much faster.
- To try, start with this command `factomd -fast=true`
- This release does not include any bugfixes beyond what 0.4.2.0 fixed.

## Release notes for v0.4.2.0
- Better discovery of the highest block.
- Catches up to highest block more quickly from 1-2 blocks behind.
- Fix some bugs in process list handling.
- Allow to download past block 87623.  Older versions will likely get stuck. 


## Release notes for v0.4.1.3
- Fix bug where block height stays 1-3 block behind servers for an extended period of time.
- Fix bug where client can lose synchronization with the servers.
- Fixed bug where data was downloaded then ignored/deleted.


## Release notes for v0.4.1.2
- This improves some network message management.
- Improve handling of entries over the p2p network
- Added some instrumentation


## Release notes for v0.4.1.1
- This fixes a problem which causes network disconnections when many peers are connecting to a node.
- Increase the broadcast rate of p2p messages


## Release notes for v0.4.1.0

**This is a required upgrade.**  Older versions of software will not download new blocks from the network.

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


## General Notes

factomd is much slower to start on a spinning hard drive, compared to a solid state drive.  It is recommended to save the blockchain on a solid state drive.


