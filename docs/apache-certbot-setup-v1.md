# Apache- und Certbot-Setup für `lisacloud.site` (sicherer V1-Pfad)

## Ziel
Die statische V1-Seite aus `site/index.html` auf einem Ubuntu-/Apache-Server veröffentlichen, ohne Schlüsselmaterial ins Repo zu legen.

## Wichtig vorab
- **Keine privaten Schlüssel aus Git verwenden.**
- Im Repo lag zwischenzeitlich eine Key-Datei. Sie ist damit als **kompromittiert** zu behandeln, selbst wenn sie wieder gelöscht wurde.
- Falls dieser Key irgendwo verwendet wurde oder werden sollte: **nicht weiterverwenden, sondern ersetzen**.
- Für den V1-Setup ist ein eigener, manuell abgelegter Key in der Regel gar nicht nötig, weil **Certbot** Zertifikat und Key sauber selbst verwaltet.

## Voraussetzungen
1. DNS für `lisacloud.site` zeigt auf den Server
2. optional: `www.lisacloud.site` zeigt ebenfalls auf den Server
3. Apache2 läuft bereits
4. Veröffentlichungsordner ist vorbereitet, z. B. `/var/www/lisacloud.site`

## Empfohlener Veröffentlichungsordner
```bash
sudo mkdir -p /var/www/lisacloud.site
sudo chown -R $USER:$USER /var/www/lisacloud.site
rsync -av --delete site/ /var/www/lisacloud.site/
```

## Empfohlene Apache-VHost-Konfiguration vor TLS
Zuerst **nur Port 80** sauber konfigurieren. Zertifikatspfade werden **nicht** manuell gesetzt, solange Certbot das übernehmen soll.

Beispiel für `/etc/apache2/sites-available/lisacloud.site.conf`:

```apache
<VirtualHost *:80>
    ServerName lisacloud.site
    ServerAlias www.lisacloud.site
    DocumentRoot /var/www/lisacloud.site

    <Directory /var/www/lisacloud.site>
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/lisacloud-error.log
    CustomLog ${APACHE_LOG_DIR}/lisacloud-access.log combined
</VirtualHost>
```

Dann aktivieren:

```bash
sudo a2ensite lisacloud.site.conf
sudo a2dissite 000-default.conf
sudo systemctl reload apache2
```

## Certbot installieren und HTTPS aktivieren
```bash
sudo apt update
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache -d lisacloud.site -d www.lisacloud.site
```

Certbot ergänzt danach die TLS-Konfiguration automatisch.

## Deployment-Ablauf für V1
1. lokale Seite in `site/index.html` aktualisieren
2. `site/` auf den Server synchronisieren
3. Apache-Konfiguration prüfen
4. Certbot laufen lassen
5. Seite unter `https://lisacloud.site` testen

## Schnelle Checks
```bash
apache2ctl configtest
systemctl status apache2 --no-pager
sudo certbot certificates
curl -I http://lisacloud.site
curl -I https://lisacloud.site
```

## Offene Punkte vor echtem Go-live
- Impressum / Datenschutz ergänzen
- echtes Formular oder Waitlist-Handling statt `mailto:` einbauen
- später Open-Graph-Meta-Tags und Analytics nur bewusst ergänzen

## Merksatz
**Repo ist für Code und Inhalte da, nicht für Secrets.** Zertifikate, Keys und Zugangsdaten gehören auf den Server oder in einen Secret-Store, nicht in Git.
