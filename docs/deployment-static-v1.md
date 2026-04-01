# Deployment Static V1

## Zweck
Aus der ersten HTML-Rohfassung eine direkt deploybare Minimalstruktur ableiten.

## Aktueller Stand
- veröffentlichbare Testseite liegt als `site/index.html` vor
- Quelle für Weiterentwicklung bleibt vorerst `docs/waitlist-web-v1.html`
- `site/index.html` ist die einfache Export-Fassung für schnelles Testen oder späteres Hosting auf einer statischen Plattform

## Einfacher Deployment-Pfad
Geeignet für z. B. GitHub Pages, Netlify, Cloudflare Pages oder einen simplen Static-Host.

1. `site/` als Veröffentlichungsordner verwenden
2. `index.html` dort direkt ausliefern
3. bei späterem Ausbau Formular-Endpoint oder externes Waitlist-Tool ergänzen
4. danach Styling, Meta-Daten und Tracking nur bewusst ergänzen

## Nächste sinnvolle Ausbaustufen
- Mailto-CTA durch echtes Formular oder leichtes Waitlist-Handling ersetzen
- Footer um Impressum / Datenschutz ergänzen, sobald die Seite öffentlich geht
- Open-Graph-Meta-Tags und Social-Preview ergänzen
- bei Bedarf CSS/Assets auslagern, sobald die Seite nicht mehr nur als Single-File getestet wird

## Wichtige Regel
Keine Schlüssel, Zertifikate oder andere geheime Dateien im Repo ablegen. Wenn für Deployment Zertifikate nötig sind, gehören sie in den Hosting- oder Secret-Kontext, nicht in Git.
