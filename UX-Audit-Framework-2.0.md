**Ziel:** Ein autonomer Agent führt einen UX-Audit durch – ohne Scoring. Stattdessen Status + Priorität + Evidenz + konkrete Empfehlung.  
**Hinweis:** Themen der **Barrierefreiheit** und **technischen Performance** (z. B. Pagespeed) sind **nicht** Teil des Kern-Audits und als **Zusatz-Module** separat anbaubar (siehe „Module (optional)“).

---

## 0) Briefing-Intro (vor dem Audit abfragen)
**Kurzabfrage (Pflicht):**
- **Branche/Industrie:** (z. B. Energie, Bank, SaaS, E-Commerce, Bildung, NGO, Medien)
- **Produkt/Service-Art:** (Sparprodukt, Tarif, Versicherung, Subscription, physisches Produkt …)
- **Seitentyp/Kategorie:** (eine oder mehrere)
  - Corporate / Unternehmensseite
  - **Landing Page** (Kampagne/Lead-Gen)
  - **Online-Shop / E-Commerce**
  - **Produkt-/SaaS-Seite**
  - **Service-/Kundenportal**
  - **Blog / Magazin / News**
  - **Wissensbasis / Doku / Hilfe**
  - **Portfolio / Case-Studies**
  - **One-Pager / Microsite**
  - **Community / Forum / Events**
- **Primäre Ziele (max. 3):** (Lead, Kauf, Termin, Kontakt, Download …)
- **Sekundäre Ziele:** …
- **Zielgruppen/Segmente:** …
- **Markenwerte/Brand-Ton:** (optional Brand-Guide)
- **KPIs (falls vorhanden):** (CR, CTR Hero-CTA, Sign-ups, Bounce …)

> Wenn kein Seitentyp angegeben ist, aus Struktur + Features ableiten und dokumentieren („Annahme: …“).

---

## Audit-Philosophie
- **Don’t make me think:** Inhalte einfach, klar, ohne Hürden.
- **Guide me:** Sichtbare Zielhandlung, klare Struktur & Navigation.
- **Create emotional impact:** Stimmige Marke, glaubwürdige Signale, aktivierende Gestaltung.

---

## Evidenz- und Befundformat (ohne Scores)
Jedes Kriterium wird so dokumentiert:

- **Status:** ✅ Erfüllt / ⚠️ Teilweise / ❌ Nicht erfüllt  
- **Priorität:** High / Medium / Low *(Impact × Aufwand, pragmatisch)*
- **Evidenz (Code):** Relevante DOM-Selektoren, Attribute, Textstellen
- **Evidenz (Visuell):** Screenshot-Ausschnitt (+ Viewport/Koordinaten)
- **Empfehlung (3-teilig, verpflichtend):**
  - **Handlung (Was)** – kurze Direktive
  - **Begründung (Warum)** – Heuristik/UX-Law/Prinzip
  - **Technische Anweisung (Wie)** – selektorbasierter Vorschlag (CSS/HTML/JS)

---

## Kategorien & Kriterien (Kern-Audit)

### 1) Einfachheit (Simplicity)
**E1 – Konsistenz der Interaktionselemente (Jakob’s Law)**  
- **Code:** Buttons sind `<button>` oder `<a>` (kein `div[onclick]`), konsistente Komponentenklassen  
- **Visuell:** einheitliche Button-Gestalt (Farbe, Größe, Radius, States)

**E2 – Essentielle Inhalte & Funktionen vorhanden (seitentypabhängig)**  
- **Code:** erwartete Schlüsselelemente vorhanden (z. B. Produktinfo, Kontakt, Pricing; Formulare mit `required` wo nötig)  
- **Visuell:** erwartete Bereiche sichtbar & zugänglich

**E3 – Eindeutige Zielhandlungsanweisung (CTA-Klarheit)**  
- **Code:** CTA-Texte mit Handlungsverb, keine mehrdeutigen Labels  
- **Visuell:** CTA prominent, klar abgegrenzt, ausreichend Abstand

**E4 – Redundanzen & Füllwörter vermeiden**  
- **Code:** Textanalyse auf sehr lange Sätze (> 20 Wörter) & Füllwörter  
- **Visuell:** sinnvolles Chunking, Weißraum, Scanbarkeit

**E5 – Gesprochene Sprache & aktivierende Fragen**  
- **Code:** 2. Person, Fragen vorhanden, wenig Passiv/Nominalstil  
- **Visuell:** kurze, direkte Botschaften sichtbar hervorgehoben

---

### 2) Verständlichkeit (Clarity)
**V1 – Einfache Sprache, Jargon erklärt**  
- **Code:** Fachbegriffe/Abkürzungen erkenntlich; Erklärflächen/Glossar vorhanden  
- **Visuell:** kontextsensitive Erklärungen/Infoboxen

**V2 – Vollständigkeit der Informationen**  
- **Code:** Pflichtangaben vorhanden (z. B. Preis, Konditionen), Formulare liefern Fehlermeldungen  
- **Visuell:** keine Informationslücken in Kernbereichen

**V3 – Klare Informationshierarchie**  
- **Code:** sinnvolle `<h1…h6>`-Abfolge, semantische Gruppierung  
- **Visuell:** typografische Hierarchie, Abstände, Raster

**V4 – Konsistente Benennungen**  
- **Code:** gleiche Funktionen gleich benannt („Login“ vs. „Anmeldung“ vermeiden)  
- **Visuell:** Labels, Menüs, Buttons konsistent

**V5 – Aussagekräftige Headlines**  
- **Code:** H1–H3 enthalten Schlüsselbegriffe (keine Placeholder)  
- **Visuell:** Headlines visuell dominant und inhaltlich klar

---

### 3) Responsiveness (Responsivität)
**R1 – Angepasste Informationstiefe**  
- **Code:** Textlänge pro Viewport; Absätze > 3 Bildschirmhöhen flaggen  
- **Visuell:** Scrolltiefe vs. Informationsdichte im ersten Screen

**R2 – Nutzung nativer Gerätefunktionen**  
- **Code:** Standard-Elemente (z. B. `<select>`) oder sauber implementierte Custom-UIs  
- **Visuell:** erwartetes Verhalten/Look für Standard-Controls

**R3 – Lesbarkeit auf kleinen Geräten**  
- **Code:** Media-Queries, fluid Layouts, mobile Fonts ≥ 16px  
- **Visuell:** Zeilenlänge ~45–70 Zeichen, ausreichender Kontrast

> **Hinweis:** Ladezeit/Pagespeed ist **nicht** Teil des Kern-Audits; siehe Modul „Technische Performance“.

---

### 4) Navigation
**N1 – Einfache Antrag/Checkout-Strecke**  
- **Code:** logische Gruppierung, Schrittindikatoren, Interaktions-Feedback  
- **Visuell:** Feldanzahl/-länge angemessen, Progress erkennbar

**N2 – Auffindbarkeit wichtiger Inhalte**  
- **Code:** `<nav>`, interne Verlinkungen, Breadcrumbs  
- **Visuell:** Suche, Menü, Filter klar sichtbar

**N3 – Klare Heading-Struktur**  
- **Code:** keine Heading-Sprünge  
- **Visuell:** visuelle Hierarchie spiegelt Semantik

**N4 – Navigation & Seitenstruktur (Hick’s/Miller’s Law)**  
- **Code:** Hauptnavigation ≈ ≤ 7 ± 2 Punkte  
- **Visuell:** Orientierungspunkte (Header, Footer, Breadcrumbs) eindeutig

**N5 – Visuelle Strukturierung**  
- **Code:** definierte Heading-Styles in CSS  
- **Visuell:** Abstände, Alignment, konsistentes Grid

---

### 5) Zielfokus (Goal Focus)
**Z1 – Primäres Ziel klar abgrenzbar (Isolation Effect)**  
- **Code:** genau ein primärer CTA (keine Konkurrenz durch gleichgewichtete Sekundär-CTAs)  
- **Visuell:** klare farbliche/größenmäßige Abhebung

**Z2 – Call-to-Action-Texte (Handlungsverben)**  
- **Code:** prägnante Verben, klare Semantik  
- **Visuell:** kurz (< 4 Wörter), kontextstark

**Z3 – Platzierung wichtiger Inhalte (Above-the-Fold)**  
- **Code:** Kernbotschaft + CTA im ersten Screen (~600–700 px)  
- **Visuell:** USP + Haupt-CTA sofort sichtbar

**Z4 – Biases & UX-Laws (Framing, Social Proof, Trust)**  
- **Code:** Preisanker, Testimonials, Trust-Signale, Verknappungs-Hinweise  
- **Visuell:** Hervorhebung ohne Ablenkung

---

### 6) Wiedererkennung (Recognition)
**W1 – Klarer Absender/Branding**  
- **Code:** Logo im Header, sinnvoller `<title>` und `meta description`  
- **Visuell:** Markenlogo/Name prominent ohne Konkurrenz

**W2 – Konsistente Gestaltung**  
- **Code:** wiederkehrende Variablen/Klassen für Farben, Spacing, Komponenten  
- **Visuell:** kohärente Bildwelt, Icons, Farbpalette

**W3 – Markenidentität spürbar**  
- **Code:** Mission/Values/Proof-Points im DOM  
- **Visuell:** Bildsprache & Ton treffen Marke und Branche

**W4 – Glaubwürdigkeit & Versprechen**  
- **Code:** Buzzword-Dichte niedrig, Abgleich mit Impressum/AGB  
- **Visuell:** plausible Testimonials/Zertifikate

**W5 – Abgrenzung zur Konkurrenz**  
- **Code:** (optional) Text-Ähnlichkeitscheck  
- **Visuell:** eigenständige Motive statt generischer Stock

**W6 – Brand-Guide-Konformität**  
- **Code:** Terminologie-Abgleich ggü. bereitgestelltem Guide  
- **Visuell:** orthografische Konsistenz, Schreibweisen

---

### 7) Relevanz
**Rlv1 – Essenzielle Inhalte & Features**  
- **Code:** USPs/Features/Kontakt vorhanden  
- **Visuell:** USP, Preis, Vorteile sichtbar priorisiert

**Rlv2 – Zielgruppen-spezifischer Content**  
- **Code:** Segmentierung/Personalisierung (falls vorgesehen)  
- **Visuell:** Bildwelt & Beispiele passen zur Zielgruppe

**Rlv3 – Präsentation der USPs**  
- **Code:** Abschnitte „Vorteile/Warum wir“ strukturiert  
- **Visuell:** Icons/Listen/Hervorhebungen

**Rlv4 – Aktualität der Inhalte**  
- **Code:** Datumsangaben/Versionen vorhanden  
- **Visuell:** zeitgemäße Referenzen & Assets

**Rlv5 – Relevante Suchbegriffe (leichtgewichtig, on-page)**  
- **Code:** `<title>`, `meta description`, `<h1>` keyword-stimmig  
- **Visuell:** zentrale Begriffe im sichtbaren Text

**Rlv6 – Nutzerprobleme antizipieren**  
- **Code:** FAQs/Help/Erklärflächen vorhanden  
- **Visuell:** heikle Themen (Lieferzeit, Kosten) proaktiv adressiert

---

## Ablauf (Agenten-Operative)
1. **Framework laden** → Briefing-Intro abfragen/validieren  
2. **URL öffnen** → Viewports: Mobile (360×640), Tablet (768×1024), Desktop (1440×900)  
3. **Screenshots** je Viewport: Above-the-Fold + Full-page (scrollend), Pfade speichern  
4. **DOM-Dump**: HTML + verbundene CSS/JS (für Evidenz, keine Performance-Bewertung)  
5. **Kriterienprüfung** Kategorie → Kriterium:  
   - Status, Priorität, Evidenz (Code/Visuell)  
   - Empfehlung (Was/Warum/Wie) – **immer selektorbasiert**  
6. **Quick Wins** identifizieren (hoher Impact, niedriger Aufwand)  
7. **Bericht erzeugen** (Template unten) + optional JSON-Artefakt (Issues)

---

## Bericht-Template (ohne Scores)
# UX-Audit für `<Hostname>` (`<Datum>`)

## Executive Summary
- **Primäres Ziel:** `<…>`  
- **Hauptbefunde (3–5):** `<…>`  
- **Top-3 Quick Wins:** `<…>`  
- **Risiken/Trade-offs:** `<…>`  
- **Nächste Schritte:** `<…>`

## Befundübersicht
| Kategorie | Kriterium | Status | Priorität | Kurzbefund |
|---|---|---:|---:|---|
| Einfachheit | E1 – Konsistenz der Interaktionselemente | ⚠️ | High | `<1-Satz-Befund>` |
| … | … | … | … | … |

## Detailanalyse
### `<Kategorie>`
#### `<Kriterium-ID – Kurzbeschreibung>`
- **Status:** ✅ / ⚠️ / ❌  
- **Priorität:** High / Medium / Low  
- **Evidenz (Code):** ```html
<relevanter DOM-Ausschnitt oder Selektor>
Evidenz (Visuell): screens/desktop_hero.png#bbox(120,320,540,420)

Empfehlung (3-teilig):

Was: <Direktive>

Warum: <Heuristik/UX-Law>

Wie: ```css
.hero-cta { background: var(--brand-primary); }
.btn.secondary { opacity: .75; }

python
Code kopieren

## Quick Wins
- `[High/Low Aufwand] <Maßnahme>` – **Nutzen:** `<Impact>` – **Wie:** `<Selektor/Change>`

## Anhang
- **Screenshots:** je Viewport (nummeriert)  
- **DOM-Artefakte:** Exportpfade/Hashes  
- **(Optional) Brand-Guide-Abgleich:** Stichpunkte

---

## JSON-Artefakt (optional)
Jedes Issue als Objekt mit:  
`id, category, criterion, status, priority, evidence.code[], evidence.visual, recommendation.{what,why,how}`

**Beispiel:**
```json
{
  "id": "Z1-001",
  "category": "Goal Focus",
  "criterion": "Z1 – Primäres Ziel klar abgrenzbar",
  "status": "partial",
  "priority": "high",
  "evidence": {
    "code": [".btn.primary", ".btn.secondary.is-equal-weight"]
  },
  "evidence_visual": {
    "screenshot": "screens/desktop_hero.png",
    "bbox": [120, 320, 540, 420]
  },
  "recommendation": {
    "what": "Sekundär-CTA deeskalieren, Primär-CTA isolieren",
    "why": "Isolation Effect, Hick’s Law",
    "how": ".btn.secondary{opacity:.7;border-color:var(--neutral-300)}; .btn.primary{background:var(--brand-primary)}"
  }
}
Mini-Checklisten nach Seitentyp (Erwartungswerte)
Landing Page (Lead/Kampagne)

Hero: klarer USP + ein primärer CTA Above-the-Fold

Social Proof im 1. Screen; Formular schlank, nur notwendige Felder

Friktion gering (kein unnötiger Ablenkungskram)

E-Commerce / PDP

Preis, Variante, Verfügbarkeit sichtbar

Primär-CTA „In den Warenkorb“ isoliert

Versand/Retouren vor dem CTA klar

SaaS / Produktseite

Klarer Value Prop + „Free Trial/Demo“

Pricing-Vergleich verständlich, FAQ zu Risiken (Kündigung, Sicherheit)

Onboarding kurz erklärt, Trust-Signale sichtbar

Service-/Kundenportal

Login/Registrierung einfach, Aufgaben-Hub (Top-3 Tasks)

Klarer Status (z. B. Tickets/Rechnungen) – ohne technische Detailmetriken

Module (optional, separat ausführbar – nicht Kern-Audit)
Modul A – Barrierefreiheit (A11y) – separat dokumentieren
Ziel: Konformität ggü. WCAG 2.1 AA prüfen (Kontraste, Tastatur-Fokus, Alternativtexte, Rollen, Skip-Links, Fokus-Reihenfolge, Fehlertexte etc.).

Output: eigener A11y-Report mit Checkliste, Beispielen, Code-Patches (keine Vermischung mit UX-Kernbefunden).

Modul B – Technische Performance (Pagespeed)
Ziel: Messung & Analyse (LCP, CLS, INP, TTFB, TTI, Ressourcen-Budget, Bild-Optimierung, kritisches CSS, Caching, 3rd-Party-Kosten).

Tools: Lighthouse/Performance-API, WebPageTest o. ä.

Output: eigener Performance-Report mit Messpunkten, Bottlenecks, Priorisierung & Tech-Fixes.

Beide Module können bei Bedarf parallel beauftragt werden und in der Executive Summary lediglich verlinkt/kurz erwähnt werden.
