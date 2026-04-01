# READER.md — /erfahrungen/

## Zweck

Dieser Ordner ist das lebende Erfahrungsarchiv von OpenClaw und ihrer Agentin LISA CLOUD.
Er sammelt reale Praxiserfahrungen aus dem Betrieb von KI-Agenten,
dokumentiert Stolpersteine, Erkenntnisse und Lösungen —
und dient gleichzeitig als Rohmaterial für Content auf LinkedIn und X.

---

## Struktur
```
/erfahrungen/
  READER.md          ← diese Datei
  /stolpersteine/    ← Erfahrungsberichte aus der Praxis
  /linkedin/         ← fertige Posts für LinkedIn
  /x/                ← fertige Posts für X / Twitter
```

Weitere Unterordner können jederzeit nach demselben Prinzip ergänzt werden.

---

## Dateiformat

**Dateiname:** `YYYY-MM-DD_stichwort.md`  
Beispiel: `2026-04-01_webhook-timeout.md`

**Inhalt:** Freitext — kein starres Schema.  

Optionaler Hinweis in der ersten Zeile:
```
Typ: Schmerz | Tipp | Aha-Moment | Allgemein
```

---

## Wie LISA damit arbeitet

1. LISA liest alle Dateien in `/stolpersteine/`
2. nach Zeitplan, generiert daraus Posts
3. Fertige Posts landen in `/linkedin/` und `/x/` —
   gleicher Dateiname wie die Quelldatei
4. Barbara gibt frei — dann wird gepostet

### Beispiel
Der 5-Minuten-Mythos von OpenClaw. 🦞
1. Die Software von OpenClaw zu installieren dauert zwar weniger als 5 Minuten, aber damit ist OpenClaw noch gar nicht einsatzbereit.
2. Die erste Hürde sind die ganzen Fragen, die beantwortet werden müssen, um OpenClaw einzurichten.
   - Beispiel: die Auswahl der LLM
     - welche der LLM passt am Besten zu den Aufgaben, Recherche ist hier sinnvoll und kann mehrere Tage dauern
   - Beispiel: Skills
     - welche der 50 Skills die angeboten werden soll ich einrichten?
   - Beispiel: Channel
     - Wie soll ich mit der KI Agentin kommunizieren, Telegram, Discord, Slack, WhatsApp?
   - Wo sollen Dokumente abgelegt werden?
     - Auf Google Drive, Notion, Github, Discord         
   - Was braucht die KI Agentin um mit der Arbeit loszulegen?
     - Email Konto, Google Account, Github API etc.
    
All das muss entweder vor der Einrichtung oder während der Einrichtung geklärt werden und kann schnell ein paar Tage dauen. 
##### gepostet: DRAFT/ JA/ NEIN
gepostet steht zunächst auf DRAFT, nach dem Barbara den Post genehmigt hat, steht er auf NEIN, nachdem LISA in gepostet hat steht er auf JA.

---

## Für Menschen

- Einträge werden einfach als `.md` Datei ablegt
- Datum im Dateinamen reicht als Zeitstempel
- Fehlende Posts = noch nicht verarbeitet

---

## Blueprint-Hinweis

Diese Struktur ist ein reproduzierbares Muster für
agentenbasiertes Content-Management. Dokumentation
für Menschen und Maschinen in einer Datei.
Geeignet als Kursbeispiel für Digital Compas Bootcamp. (https://digital-compass-de.github.io/)
