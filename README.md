##Factom Binaries

The latest version of Factom is Version 0.4.0.1, released 29 Jan, 2017

Install for:

| OS | Factomd Installer | Enterprise Installer | factomd sha256sum | Enterprise sha256sum |
|----|-----|-----|-----|-----|
| Windows 64bit | [FactomInstall-amd64.msi](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/FactomInstall-amd64.msi) | [enterprise-wallet-setup-amd64.exe](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/enterprise-wallet-setup-amd64.exe) | 9aa9d5006c2a56d18f7c513f7dd324c9d355ca5a7770c34044a032d955866594 | 1d89ae97de6b53a189a9b7b4950f1696cef810ccb87f292323a4a5430691c225 |
| Windows 32bit | [FactomInstall-i386.msi](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/FactomInstall-i386.msi) | | 9db590c6f58cef8a466a0148610882a848749471dfa78d5aad47415427aeee3f | |
| Mac | [factom.mpkg.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/factom.mpkg.zip) | [enterprise-wallet-setup.dmg](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/enterprise-wallet-setup.dmg) | 4a42076b66995eb313a5208f9f524bcf245e1803ad1c9ea8e4ad41ad63cb5db1 | 28198046cc9bf4d35bb3a9658cd6a28dcfb21f5831dcfc43ba9ea17e62bd44a2 |
| Linux (Ubuntu/Debian) 64bit | [factom-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/factom-amd64.deb) | [enterprise-wallet-setup-amd64.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/enterprise-wallet-setup-amd64.deb) | 7b95ccc996307c066222a1cb6e444a9d70959b96061902acf91b2edaf376a47b | dfdda21db76da3035361b2aa7094b979d2245747db4932f89a4ad1b0ce4becc1 |
| Linux (Ubuntu/Debian) 32bit | [factom-i386.deb](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/factom-i386.deb) | | 74a16ee5f377811e73e20ca57e0d8cb909454728537fa30c9cb95c46fc90c45f | |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md). | [enterprise-wallet-linux.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/enterprise-wallet-linux.zip) | | 28dcd18ad499b204fb87f6dbeeb23c6266654d9b33143074163ad37a10c6098c |


Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

Source code archive: [FactomProject_src_0.4.0.1.zip](https://github.com/FactomProject/distribution/releases/download/v0.4.0.1/FactomProject_src_0.4.0.1.zip)


##Release notes for 0.4.0.1

- Updated Wallet

Enterprise Wallet now launches as a standalone program.  It no longer needs to be started from the command line.  (Factomd, however still does though.)

- Faster Download

This version of Factomd downloads the blockchain faster.

- Faster Startup

This version also boots much faster than v0.4.0.1. 


- Workarounds

One known issue is that factomd does not keep up with new blocks if it needs to download many blocks after starting.  The workaround is to start factomd, allow it to download all the blocks so far created.  Close factomd (ctrl+c) and restart it.  it should keep up with blocks after the second start.


The blockchain is fairly large and the P2P sync code is not fast.  To expedite the startup time, the first 70k blocks can be downloaded via http.
 https://www.factom.com/assets/site/factom_bootstrap.zip
 SHA256: 2d4d256c337cdabc8f75aa71180c72129f807c365c78356471350ac1e0a4faed

Extract the zip file to your home directory. It will create files in the location: ~/.factom/m2/main-database/ldb/MAIN/factoid_level.db/   Compressed the blockchain is currently about 5 GB and uncompressed is over 9 GB.


factomd is much slower to start on a spinning hard drive, compared to a solid state drive.  It is recommended to save the blockchain on a solid state drive.





