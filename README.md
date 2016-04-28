##Factom Binaries

The latest version of Factom is Version 0.3.7.0, released 27 April 2016

Install for:

| OS | Installer | sha256sum |
|----|-----|-----|
| Windows | [FactomInstall.msi](https://github.com/FactomProject/distribution/releases/download/v0.3.7.0/FactomInstall.msi) | 743e5b0cc65a79afe5eac8c75f4141b4edad946da67d7080aed6f3b53dbab796 |
| Mac | [factom.mpkg.zip](https://github.com/FactomProject/distribution/releases/download/v0.3.7.0/factom.mpkg.zip) | 1d3d69d5f841e515128121e53018031ac1fb84f1ee8ab0e24af4b5e2a637c80b |
| Linux (Ubuntu/Debian) | [factom.deb](https://github.com/FactomProject/distribution/releases/download/v0.3.7.0/factom.deb) | 6a7e66b8b00958cc3a1328c20a7e760d787e7addc82e617fce339d833729b983 |
| Linux (Redhat/Centos) | Pending. See [last release](https://github.com/FactomProject/distribution/blob/9a745d8962462912ffc9b0c2b2a2fa3a231dab7b/README.md). |  |



Source code archive: [FactomProject_source.zip](https://github.com/FactomProject/distribution/releases/download/v0.3.7.0/FactomProject_source.zip)


##Release notes for 0.3.7.0

- Network Improvements

Factomd was having trouble with the Great Firewall of China. We were finally able to track down what was causing factomd to fall behind from synchronization. Version 0.3.7.0 no longer falls behind when the GFW resets connections.
