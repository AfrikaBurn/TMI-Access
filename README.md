# TMI Access

> Represent, authenticate and collect participants.


## Services

* [OpenLDAP](openldap.org)      - main user directory and group store.
* [phpLDAPadmin](keycloak.org)  - authentication adapter.
* [Keycloak](keycloak.org)      - authentication adapter.


## Installation

### Prerequisites:

* [Docker](https://docker.io)

Clone this repository including the openLDAP submodule:
```bash
git clone --recurse-submodules https://github.com/AfrikaBurn/TMI-Access-Token.git
```
* Copy default.env to .env:
```bash
cd TMI-Access-Token
cp default.env .env
```


## Service

| Container                     | Protocol  | External Port | Internal port | URL
| ----------------------------- | --------- | ------------- | ------------- | ---
| [OpenLDAP](openldap.org)      | LDAP      | 11010         | 389           | ?
|                               | LDAPS     | 11015         | 363           | ?
| [phpLDAPadmin](keycloak.org)  | HTTP      | 11020         | 80            | http://localhost:11020
|                               | HTTPS     | 11025         | 443           | https://localhost:11025
| [Keycloak](keycloak.org)      | HTTP      | 11030         | 8080          | http://localhost:11030
|                               | HTTPS     | 11035         | 363           | https://localhost:11035


## Service control

```bash
# Build service:
./scripts/build

# Build and start service:
./scripts/start

# Stop service
CTRL+C

# SSH into images
./scripts ssh [ openLDAP | phpLDAPadmin | Keycloak ]
```