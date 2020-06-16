# TMI Access

> Represent, authenticate and collect participants.


## Services

* [OpenLDAP](openldap.org) - main user directory and group store.
* [Keycloak](https://www.keycloak.org/) - authentication adapter.


## Requirements

* [Docker](https://docker.io)


## Installation

* Clone this repository including the openLDAP submodule:
```bash
git clone --recurse-submodules https://github.com/AfrikaBurn/TMI-Access-Token.git
```
* Copy default.env to .env:
```bash
cd TMI-Access-Token
cp default.env .env
```
* Change the make passwords in .env more secure .


### Optional:

* Docker Volumes:
    * ldap_config
    * ldap_data


## Services

| Service | Protocol | Port |
| --- | --- | --- |
| OpenLDAP | LDAP | 389 |
| | LDAPS | 363 |
| Keycloak | HTTP | 11080 |
| | HTTPS | 363 |


## Service control

```bash
# Build services:
./scripts/build

# Build and start services:
./scripts/start

# Stop services
./scripts/start

# SSH into either service
./scripts ssh [ keycloak | ldap ]
```