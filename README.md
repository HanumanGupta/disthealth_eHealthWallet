# Universal CCD
### disthealth_eHealthWallet

Our blockchain entry into the DistHealth hackathon

## Technologies used

* HealthLX CCD viewer (Patient Insight)
	* <http://52.20.128.239:3000/>
* DICOM viewer
	* <https://ivmartel.github.io/dwv/demo/stable/viewers/static/index.html>
* Ethereum (blockchain)
* Tierion (non-repudiation system  - uses blockchain)
	* <https://tierion.com/>
	* <https://tierion.com/proof>
* IPFS (distributed storage). Other alternatives
  * [MIT Enigma](http://enigma.media.mit.edu/)
  * [Blockstack](https://blockstack.org/)


# FAQ

## Why use Tierion?

Tierion is based on **Proof of Existence**

Use our service to anonymously and securely store an online distributed proof of existence for any document. Your documents are NOT stored in our database or in the bitcoin blockchain, so you don't have to worry about your data being accessed by others.

All we store is a cryptographic digest of the file, linked to the time in which you submitted the document. In this way, you can later certify that the data existed at that time. This is the first online service allowing you to publicly prove that you have certain information without revealing the data or yourself, with a decentralized certification based on the bitcoin network.

The key advantages are anonymity, privacy, and getting a decentralized proof which can't be erased or modified by anyone (third parties or governments). Your document's existence is permanently validated by the blockchain even if this site is compromised or down, so you don't depend or need to trust any central authority. All previous data timestamping solutions lack this freedom.

# Log

### Generate certs for hospitals

* setup DNS for hospitals (mayoclinic.apifocal.org, nashvillecentral.apifocal.org)
* install certbot
* install & configure apache2 (80/443)
* setup vhost for hospital
  * http to https redirect: http://mayoclinic.apifocal.org -> https://mayoclinic.apifocal.org
  * http to https redirect: http://nashvillegeneral.apifocal.org -> https://nashvillegeneral.apifocal.org
* generate certs using letsencrypt

```ssh
sudo ./certbot-auto certonly --webroot -w /var/www/html -d nashvillegeneral.apifocal.org --email alex@apifocal.com
sudo ./certbot-auto certonly --webroot -w /var/www/html -d mayoclinic.apifocal.org --email alex@apifocal.com
```

### Setup a private Ethereum Blockchain

### Create a Smart Contract

