# Updaten

## Backups maken

Backup eerst voor de zekerheid je channels via Ride The Lightning, Thunderhub of LNCLI. Dit is sowieso een goede gewoonte om regelmatig te doen en niet alleen bij updates.

### RTL

* Ga naar je RTL dashboard op bijvoorbeeld `192.168.1.6:3000`. 
* Kies voor "Backups" onder "Lightning"
* Klik op "Backup All"

Nu staat er in `/home/pi/RTL/backup/node-1/` een bestand dat `channel-all.bak` heet.

## Stop services

Stop nu de services die afhankelijk zijn van LND zoals Ride The Lightning of Thunderhub en LND zelf.

```bash
sudo systemctl stop lnd
```

## Source code ophalen en compileren

Update de repository met de laatste wijzigingen via Git.

```bash
cd ~/lnd
git pull
```

Toon de laatste versie / tag.

```text
git describe --tags `git rev-list --tags --max-count=1`
```

Haal de wijzigingen op van de laatste versie.

```bash
git checkout <OUTPUT VAN DE VORIGE STAP> #voorbeeld: v0.12.0-beta
```

Installeer nu de software.

```bash
make install tags="signrpc walletrpc chainrpc invoicesrpc"
```

## Start de services

Start de service `lnd` en monitor de voortgang van het opstarten. Wees geduldig dit kan even duren.

```bash
sudo systemctl start lnd
sudo journalctl -f -u lnd
```

Zodra je in de output voorbij ziet komen dat je de wallet kunt unlocken, start je een tweede putty venster.

```bash
lncli unlock
```

Vul nu je passphrase in van je wallet. Nu zie je in het andere venster de GossipSyncer wat betekent dat LND weer in de lucht is.

Check de huidige versie van LND.

```bash
lncli --version
```

De output zal lijken op `lncli version 0.12.1-beta commit=v0.12.1-beta`

LND is nu bijgewerkt! Start nu de andere services die afhankelijk zijn van LND zoals RTL of Thunderhub.

