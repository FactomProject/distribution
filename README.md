##Factom Binaries

The latest version of Factom is Version 0.3.8.0, released 28 Oct, 2016

Install for:

| OS | Installer | sha256sum |
|----|-----|-----|
| Windows 64bit | [FactomInstall_64_bit.msi](https://github.com/FactomProject/distribution/releases/download/v0.3.8.0/FactomInstall_64_bit.msi) | 4b10944a36d82f22fbee837b238f09a709d6e6b13f4d9281922d1d16a8401b1b |
| Windows 32bit | [FactomInstall_32_bit.msi](https://github.com/FactomProject/distribution/releases/download/v0.3.8.0/FactomInstall_32_bit.msi) | 391e518c6c566445058e6ce97c0efc9266e49a883823bfe4a42d09c1c7a64b75 |
| Mac | [factom.mpkg.zip](https://github.com/FactomProject/distribution/releases/download/v0.3.8.0/factom.mpkg.zip) | a74a63e124268d9a31a77866a3042f0243ff0844fb6e830cb6db663ddfd8ebc9 |
| Linux (Ubuntu/Debian) | [factom-0.3.8.0-i386.deb](https://github.com/FactomProject/distribution/releases/download/v0.3.8.0/factom-0.3.8.0-i386.deb) | 1678c91cb2593db22c9ff8e3ee223a1c60991569698b01454387941247d3b3c5 |
| Linux (Redhat/Centos) | Please install from [source](https://github.com/FactomProject/FactomDocs/blob/master/communityTesterDirections.md).  |  |

Install guide located [here](https://factom.com/devs/docs/howto/binaries-install-guide).

Source code archive: [FactomProject_src_0.3.8.0.zip](https://github.com/FactomProject/distribution/releases/download/v0.3.8.0/FactomProject_src_0.3.8.0.zip)


##Release notes for 0.3.8.0

- Improvements

Factomd was recompiled using the latest golang 1.7.3 compiler. Using the new compiler fixes the crash when starting factomd with an already downloaded blockchain. A 64 bit windows binary is also included which may have more reliability on some systems.

