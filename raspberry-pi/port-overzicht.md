# Port overzicht

{% hint style="info" %}
Dit dient als een naslagwerk mocht je het overzicht een beetje kwijt raken. Begrijpelijk, want je node heeft geen fancy, makkelijk te gebruiken voorkant.
{% endhint %}

Het volgende is een overzicht van alle ports die benaderbaar zijn op je Raspberry Pi. Je kunt bij bepaalde tools door in je browser het IP-adres van je Pi gevolgd door het portnummer in te voeren. Bijvoorbeeld `192.168.1.6:3002` om BTC RPC Explorer in te zien. Wil je de tools benaderen over tor, zul je per tool het `torrc` bestand moeten aanpassen. Je kunt dan bepaalde porten benaderbaar maken voor buitenaf en doorsturen naar een lokale port op je Pi. Hoe dit werkt staat binnen The Road to Node meestal uitgelegd in de tool naar keuze.

We gaan uit van de default waardes voor alle tools, met uitzondering van Thunderhub. Dit heeft te maken met het feit dat Ride the Lightning op dezelfde port draait.

### Bitcoin Core

| Port | Functionaliteit |
| :--- | :--- |
| **8332** | De JSON-RPC port. Met de juiste username/password combinatie kun je hier tegenaan praten. Standaard accepteert Bitcoin Core alleen connecties vanaf de Pi zelf. Een tool die op de Pi draait zal daarom mogen praten met de RPC port, maar een willekeurige aanvaller van buitenaf niet.  |
| **8333** | Deze port is verantwoordelijk voor de communicatie met andere clients op het Bitcoin netwerk. |
| **28332** | De Bitcoin Daemon kan middels het ZeroMQ protocol block informatie versturen naar clients. Zo hoeven de clients niet iedere keer een request te doen via de JSON-RPC, maar gaat het op subscription basis. |
| **28333** | Hetzelfde als port 28332, maar dan voor transacties in plaats van blocks. |

### Tor

| Port | Functionaliteit |
| :--- | :--- |
| **9050** | Als je wil dat een bepaalde applicatie communiceert over het tor netwerk, moet je de applicatie vertellen gebruik te maken van port 9050. |

### BTC RPC Explorer

| Port | Functionaliteit |
| :--- | :--- |
| **3002** | De BTC RPC Explorer is benaderbaar via deze port. |

### Electrum \(zowel X als Personal Server\)

| Port | Functionaliteit |
| :--- | :--- |
| **8000** | Standaard RPC port van het Electrum protocol. |
| **50001** | Standaard port voor TCP verbindingen. |
| **50002** | Standaard port voor SSL verbindingen. |
| **50004** | Standaard port voor secure websocket verbindingen. |

### Specter

| Port | Functionaliteit |
| :--- | :--- |
| **25441** | Voer je deze port in dan zie je het Specter overzicht. |

### Lightning Network Daemon

| Port | Functionaliteit |
| :--- | :--- |
| **8080** | De port waarmee de REST API van LND zich benaderbaar maakt. Beveiligd met een zogenaamde macaroon. |
| **9735** | De port die connect met andere nodes. Een beetje zoals 8333 voor Bitcoin Core. |
| **10009** | De port waarmee de RPC API van LND zich benaderbaar maakt. Beveiligd met een zogenaamde macaroon. |

### Loop

| Port | Functionaliteit |
| :--- | :--- |
| **8081** | REST port voor loopd. |
| **11010** | RPC port voor loopd. |

### Faraday

| Port | Functionaliteit |
| :--- | :--- |
| **8465** | RPC port voor faraday. |

### Pool

| Port | Functionaliteit |
| :--- | :--- |
| **8281** | REST port voor poold. |
| **12010** | RPC port voor poold. |

### Lightning Terminal

| Port | Functionaliteit |
| :--- | :--- |
| **8443** | De port waarop LiT draait. |

### Ride the Lightning

| Port | Functionaliteit |
| :--- | :--- |
| **3000** | De Ride the Lightning interface kun je gebruiken als je naar deze port gaat. |

### Thunderhub

| Port | Functionaliteit |
| :--- | :--- |
| **4000** | Standaard staat deze tool ingesteld op port 3000. Maar aangezien Ride The Lightning daar al gebruik van maakt, kiezen we in deze guide voor port 4000. |

