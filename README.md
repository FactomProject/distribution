##Factom Binaries

The latest version of Factom is Version 0.3.6.0, released 25 March 2016

Install for:

| OS | Installer | sha256sum |
|----|-----|-----|
| Windows | FactomInstall.msi | 97359317b8fc9971432bd6e8847585b3e3c6ca2898a5cef32a5e77e4d2354143 |
| Mac | factom.mpkg.zip | 6c60f2f3d11959936a89f124904d101e8e7a447f93376e171b7c49a9b46ad8a5 |
| Linux (Ubuntu/Debian) | factom-i386.deb | a6d5178ab21d2274c751ca0b280d4ba5be20d1df93132fadfd2e45c36a215cf3 |


Source code archive: FactomProject_source.zip


##Resease notes for 0.3.6.0

- Syncup Acceleration

Lately we had been seeing a bug where syncing the blockchain stalled out or would be very slow, especially in China.  It might require a restart of factomd to restart the chain download.  The bug has been fixed in this release.



- Point to trusted remote factomd

Some applications would benefit from having a trusted factomd node to hold the blockchain.  Multiple clients would share a single blockchain instance.  This would allow users to trade off convience for trustlessness.  Using a trusted factomd node does not require sharing private keys, so attacks are limited with this arrangement.

This arrangement would allow cloud service providers to host a local blockchain node which served an API to its clients.



- Easier to setup inter-company sandbox.

 When a developer wants to do some local testing, they can setup a local federated server.  If they wanted a more realalistic setup, they could setup a sandbox federated server on the LAN.  To get local clients to download the blockchain from the LAN server, they would need to recompile factomd to respect the new signature.  This release gives the option in the config file to specify the local server.  See how to setup a sandbox [here](https://github.com/FactomProject/FactomDocs/blob/master/developerSandboxSetup.md).




- Experimental partial Netki support

Last year Factom [announced](https://www.factom.com/netki-factom-announce-partnership/) it would integrate [Netki](https://www.netki.com/) wallet name resolution into the wallet.  We have added preliminary read support for the command line wallet with this release.  Use the -r command flag to lookup a factom address to send factoids or entry credits.



- Golang 1.6 support

Factom now can be compiled using the latest version of golang.  Earlier releases would break with golang 1.6.



- Vendorized all dependency packages

Now users who install from source do not have to worry about 3rd party packages introducing malicious or latent bugs.  All 3rd party packages are pulled from a FactomProject repository, so only golang and google 3rd party repositories are pulled when compiling factom.



- API changes for fctwallet

Factoid block search ranges can be specified in the API.  This allows faster automated searching for new transactions.

The compose-chain-submit and compose-entry-submit calls have been updated to take hex data instead of ascii data in the extID fields.  This allows for arbitrary data to be used as an extID instead of just text.

Added the factoid-sub-fee API call.  This is the opposite of the addfee call.  Subfee allows users to deduct an output by the correct fee amount.  It will help when emptying an address.



- Updates to factom-cli 

All entries can be requested, as well as the first entry in the chain.
Updated command "get chain" to "get chainhead"
Also exposed the subfee command in the cli wallet.



- Updates to walletapp

Doubleclicking on walletapp in the mac environment now uses the correct path for the HTML files.  you now no longer need to navigate to the terminal window to launch walletapp on the mac.



- Config file error tolerance

Earlier versions of factom handled changes to the factom.conf file poorly.  It now doesn't give incorrect results when lines are missing from the config file.
