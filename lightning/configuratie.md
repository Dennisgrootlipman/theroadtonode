# Configuratie

{% hint style="info" %}
Tijd: 5 minuten
{% endhint %}

De map waar LND gebruik van wil maken, bestaat nog niet. Maak hem dus eerst aan. Let op: deze configuratie map verschilt van de map waar je LND zojuist in hebt [geïnstalleerd](https://docs.theroadtonode.com/lightning/installatie), dat was namelijk `/home/pi/lnd`.

```bash
mkdir ~/.lnd
```

Het configuratie bestand maak je aan met:

```bash
nano ~/.lnd/lnd.conf
```

En plak er de instellingen in.

```bash
[Application Options]
tlsautorefresh=true
restlisten=0.0.0.0:8080
rpclisten=0.0.0.0:10009
listen=127.0.0.1:9735
maxpendingchannels=5
color=ZELF_VERZINNEN_A
alias=ZELF_VERZINNEN_B

[Tor]
tor.active=true
tor.v3=true
tor.streamisolation=true

[Bitcoin]
bitcoin.active=true
bitcoin.mainnet=true
bitcoin.node=bitcoind

[bitcoind]
bitcoind.dir=/home/pi/.bitcoin
bitcoind.rpcuser=DIT_WEET_JE_A
bitcoind.rpcpass=DIT_WEET_JE_B
bitcoind.zmqpubrawblock=tcp://127.0.0.1:28332
bitcoind.zmqpubrawtx=tcp://127.0.0.1:28333
```

In de tekst hierboven staan vier dingen die je zelf moet regelen.

-   **color**, verander ZELF_VERZINNEN_A naar een kleur naar keuze. Het is een hexadecimale waarde. Bijvoorbeeld `color=#123ABC` voor de kleur blauw.
-   **alias**, verander ZELF_VERZINNEN_B naar een naam naar keuze. Je krijgt dan `alias=nickname`.
-   **bitcoind.rpcuser**, verander DIT_WEET_JE_A naar [de juiste user](https://docs.theroadtonode.com/bitcoin-core/configuratie-en-starten#authenticatie).
-   **bitcoind.rpcuser**, verander DIT_WEET_JE_B naar [het juiste wachtwoord](https://docs.theroadtonode.com/bitcoin-core/configuratie-en-starten#authenticatie). Dit wachtwoord heb je dus toebedeeld gekregen.

Sla het bestand op met `Ctrl + X` en `Y`.
