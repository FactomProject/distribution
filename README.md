##Factom Binaries

The latest version of Factom is Version 0.4.0.0, released 11 Jan, 2017

Install for:

| OS | Installer | sha256sum |
|----|-----|-----|
| Windows 64bit | [FactomInstall-amd64.msi]() | 8f154dc63532a79f47854760d678ff065a2c2eec1a9c40e0837c836b75d8547b |
| Windows 32bit | [FactomInstall-i386.msi]() | 17204eaf65bb717e1b971618d345b6da4e0fedf880ef5ce7b93d30a82ecea884 |
| Mac | [factom.mpkg.zip]() | 2c061ca8dc60e846476e0011ed8dfaa87ffd379bdd56b5ea6af1bd30fc67894a |
| Linux (Ubuntu/Debian) 64bit | [factom-0.4.0.0-amd64.deb]() | b4e3a351c96b6efc8b2e8d1f3d9566ffa9c1c8fe6be73b1739ca8750b50e92f4 |
| Linux (Ubuntu/Debian) 32bit | [factom-0.4.0.0-i386.deb]() | 52aa0c23c7f898ae2c0803697d43e6d25ae3a1b86222bff9331ee9e341ea31a4 |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/installFromSourceDirections.md).  |  |

note: the 32 bit versions do not include the GUI wallet enterprise-wallet.  This is due to a golang 1.7 [bug](https://github.com/golang/go/issues/13277). 

Install guide located [here](https://docs.factom.com/wallet#install-factom-federation-ff).

Source code archive: [FactomProject_src_0.4.0.0.zip]()


##Release notes for 0.4.0.0

- Complete Redesign

This version of Factom is a complete redesign.  It has a completely revamped blockchain managing software with much better user feedback.  It also has brand new GUI and API wallets.




- Workarounds

One known issue is that factomd does not keep up with new blocks if it needs to download many blocks after starting.  The workaround is to start factomd, allow it to download all the blocks so far created.  Close factomd (ctrl+c) and restart it.  it should keep up with blocks after the second start.


The blockchain is fairly large and the P2P sync code is not fast.  To expedite the startup time, the first 70k blocks can be downloaded via http.
 https://www.factom.com/assets/site/factom_bootstrap.zip
 SHA256: 2d4d256c337cdabc8f75aa71180c72129f807c365c78356471350ac1e0a4faed

Extract the zip file to your home directory. It will create files in the location: ~/.factom/m2/main-database/ldb/MAIN/factoid_level.db/   Compressed the blockchain is currently about 5 GB and uncompressed is over 9 GB.


factomd is much slower to start on a spinning hard drive, compared to a solid state drive.  It is recommended to save the blockchain on a solid state drive.





