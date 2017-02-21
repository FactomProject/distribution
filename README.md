##Factom Binaries

The latest version of Factom is Version 0.4.0.2, released 21 Feb, 2017

Install for:

| OS | Factomd Installer | Enterprise Installer | factomd sha256sum | Enterprise sha256sum |
|----|-----|-----|-----|-----|
| Windows 64bit | [FactomInstall-amd64.msi]() | [enterprise-wallet-setup-amd64.exe]() | xx | xx |
| Windows 32bit | [FactomInstall-i386.msi]() | | xx | |
| Mac | [factom.mpkg.zip]() | [enterprise-wallet-setup.dmg]() | xx | xx |
| Linux (Ubuntu/Debian) 64bit | [factom-amd64.deb]() | [enterprise-wallet-setup-amd64.deb]() | xx | xx |
| Linux (Ubuntu/Debian) 32bit | [factom-i386.deb]() | | xx | |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-linux.zip]() | | xx |


Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

Source code archive: [FactomProject_src_0.4.0.2.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.2/FactomProject_src_0.4.0.2.zip)


##Release notes for 0.4.0.2

- Resolve "too many files" error

On Linux and Mac, factomd would crash due to using too many open files.  This bug has been solved, and factomd no longer needs the adjust the ulimit in order to work.

- Resolve Windows Database Problem

Enterprise Wallet on some Windows systems would fail to start.  This problem has been solved.

- Networking more Resiliant

Timeouts for network connections have been increased.  This gives an incremental improvement for some stalling problems that factomd nodes have been seeing.

- Lower CPU usage

Idle time CPU usage has been decreased for times after factomd boot and syncs.



- Workarounds

One known issue is that factomd does not keep up with new blocks if it needs to download many blocks after starting.  The workaround is to start factomd, allow it to download all the blocks so far created.  Close factomd (ctrl+c) and restart it.  it should keep up with blocks after the second start.


The blockchain is fairly large and the P2P sync code is not fast.  To expedite the startup time, the first 70k blocks can be downloaded via http.
 https://www.factom.com/assets/site/factom_bootstrap.zip
 SHA256: 2d4d256c337cdabc8f75aa71180c72129f807c365c78356471350ac1e0a4faed

Extract the zip file to your home directory. It will create files in the location: ~/.factom/m2/main-database/ldb/MAIN/factoid_level.db/   Compressed the blockchain is currently about 5 GB and uncompressed is over 9 GB.


factomd is much slower to start on a spinning hard drive, compared to a solid state drive.  It is recommended to save the blockchain on a solid state drive.





