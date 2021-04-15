---
description: Geen commando is er voor niets
---

# Uitleg van Commando's

Om te weten wat je allemaal aan het copie-pasten bent, moet je wel weten wat het betekent toch? Tenminste als je the full road to node experience wilt ervaren.

* **Dependencies installeren**, er is wat software nodig om Bitcoin Core samen te stellen.
* **Broncode ophalen**, door middel van Git kunnen we de nieuwste broncode ophalen.
* **Database installeren**
* **Bitcoin Core samenstellen**

## Dependencies

Voer het volgende uit om de dependencies te installeren. Dependencies zijn precies wat het zegt; afhankelijkheden. Het zelf samenstellen van Bitcoin Core is afhankelijk van andere software.

```bash
sudo apt install git automake autoconf autotools-dev build-essential make pkg-config protobuf-compiler libminiupnpc-dev libprotobuf-dev libdb++-dev libzmq3-dev libsqlite3-dev libboost-thread-dev libboost-test-dev libboost-all-dev libevent-dev libtool libssl-dev libboost-system-dev libboost-filesystem-dev -y
```

## Broncode

Zorg allereerst dat je in de "home directory" zit. Om er zeker van te zijn voer je `cd ~` uit. De tilde \(`~`\) is een afkorting voor `/home/pi` in dit geval. Voer daarna het volgende uit om de broncode binnen te halen en in je home directory neer te zetten. Automatisch zal hier een map aangemaakt worden genaamd bitcoin met daarin de broncode.

```bash
git clone https://github.com/bitcoin/bitcoin
```
