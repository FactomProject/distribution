##Factom Binaries

The latest version of Factom is Version 0.4.0.2, released 21 Feb, 2017

Install for:

| OS | Factomd Installer | Enterprise Installer | factomd sha256sum | Enterprise sha256sum |
|----|-----|-----|-----|-----|
| Windows 64bit | [FactomInstall-amd64.msi] | [enterprise-wallet-setup-amd64.exe](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup-amd64.exe) | xx | 1e11d103da7e7b2d93c5b65c2bca9eababd08975b349b633d49681e701b18c5d |
| Windows 32bit | [FactomInstall-i386.msi] | | xx | |
| Mac | [factom.mpkg.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/factom.mpkg.zip) | [enterprise-wallet-setup.dmg](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup.dmg) | 3dea2d3c1b7e91e19acc11e5535806af2a2ea1bd1fcc409c07deced60e6e148a | 6ad2c06b05656b0fcfae75a8b4919ed3921d073d06c58698475de2a85f4d55f5 |
| Linux (Ubuntu/Debian) 64bit | [factom-amd64.deb] | [enterprise-wallet-setup-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-setup-amd64.deb) | xx | 29babb2a4cfb8f0f250a25bfd21ecfe34c5866d53a91a17c8a101570033252a1 |
| Linux (Ubuntu/Debian) 32bit | [factom-i386.deb] | | xx | |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-linux.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/enterprise-wallet-linux.zip) | | ba0ce2307ecaf83001ddff4b92036882e9af8036b3ee755159a2f664b3a15dfb |


Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

Source code archive: [factom_source_v0.4.0.2.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/factom_source_v0.4.0.2.zip)


##Release notes for 0.4.0.2

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





