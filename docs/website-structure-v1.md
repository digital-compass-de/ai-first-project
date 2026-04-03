# Website-Struktur für lisacloud.site – Vorschlag

## Aktueller Stand
- One-Page ist deploybereit (`site/index.html`)
- SSL-/Server-Setup dokumentiert (`docs/apache-certbot-setup-v1.md`)
- CTA auf Frühzugang per Mailto-Link

## Ziel
Eine Website, die:
1. Vertrauen aufbaut (authentisch, nicht überverkauft)
2. Klar kommuniziert, für wen das Produkt ist
3. Einfache nächste Schritte bietet (Frühzugang, Leseprobe)
4. Grundlage für spätere Erweiterungen schafft

---

## Empfohlene Struktur V1

### Option A: Erweiterte One-Page (empfohlen für Launch)

**Vorteile:**
- Schneller Deploy
- Einfacher zu warten
- Fokussierte User Journey
- Mobile-optimiert

**Struktur:**

```
/
├── Hero
│   ├── Titel: Tagebuch einer KI-Agentin
│   ├── Unterzeile: Ein pragmisches Playbook...
│   ├── CTA: Frühzugang sichern
│   └── Sekundär-CTA: Leseprobe ansehen
├── Problem ("Alle reden über KI...")
├── Lösung ("Ein Playbook für den ersten echten Workflow")
├── 3 Workflows (Kurzvorstellung)
├── Glaubwürdigkeit ("Warum dieses Projekt überzeugt")
├── Zielgruppe ("Ideal für dich, wenn...")
├── Leseprobe (Anchor-Link oder eingebettet)
├── FAQ (4-6 Fragen)
└── Final CTA (Frühzugang)
```

**Erweiterungen zur aktuellen Version:**
- [ ] Leseprobe als eingebetteter HTML-Ausschnitt (erstes Kapitel)
- [ ] Kleines "Über"-Segment mit Barbara + Lisa Foto/Avataren
- [ ] Newsletter-/Waitlist-Formular (später statt Mailto)

---

### Option B: Mehrseitige Struktur (für spätere Version)

**Wann sinnvoll:**
- Nach erstem Resonanztest
- Wenn mehr Inhalte verfügbar (Testimonials, Case Studies)
- Bei Erweiterung auf Coaching/Workshops

**Struktur:**

```
/
├── / (Landingpage – wie Option A, aber kompakter)
├── /leseprobe
│   ├── Vollständige Leseprobe (Kapitel 1 + Auszüge)
│   └── PDF-Download
├── /workflows
│   ├── Übersicht der 3 Workflows
│   └── Detailseiten pro Workflow
├── /ueber
│   ├── Barbara + Lisa Story
│   ├── Entstehungsgeschichte
│   └── Hinter den Kulissen
├── /blog (später)
│   └── Auszüge aus Erfahrungen/Stolpersteine
└── /kontakt
    └── Formular statt Mailto
```

---

## Technische Empfehlung

### V1 (Jetzt)
- Statische HTML/CSS-Seite
- Deploy auf VPS oder Static Hosting (Netlify, Vercel)
- Domain: lisacloud.site
- SSL: Let's Encrypt via Certbot

### V1.1 (Nach Launch)
- Leseprobe als separate Seite
- Einfaches Formular für Waitlist (z.B. Tally, Typeform, oder n8n + Airtable)

### V2 (Bei Erfolg)
- Mehrseitige Struktur
- Blog für Content-Marketing
- Mitgliederbereich für Käufer

---

## Content-Prioritäten für Website

### Muss (vor Launch)
- [x] Hero mit klarem Value Proposition
- [x] Problem-Abschnitt
- [x] 3 Workflows kurz vorgestellt
- [x] CTA Frühzugang
- [x] FAQ

### Sollte (kurz nach Launch)
- [ ] Leseprobe eingebettet
- [ ] "Über uns"-Segment
- [ ] Professionelles Waitlist-Formular

### Kann (später)
- [ ] Testimonials
- [ ] Case Studies
- [ ] Blog
- [ ] Ressourcen-Seite

---

## Design-Prinzipien

1. **Warm, nicht korporat** – Passt zu "Tagebuch"
2. **Klar, nicht überladen** – Pragmatisch wie das Playbook
3. **Authentisch, nicht gepolished** – Echte Zusammenarbeit zeigen
4. **Mobile-first** – Zielgruppe nutzt viel Mobile

---

## Nächste Schritte

1. **Heute:** Entscheidung zwischen Option A/B treffen
2. **Diese Woche:** Domain deployen (Option A)
3. **Nächste Woche:** Leseprobe als eingebetteten Abschnitt hinzufügen
4. **Nach Launch:** Feedback sammeln, dann V1.1 planen

---
*Website-Struktur-Vorschlag erstellt am 2026-04-03*
