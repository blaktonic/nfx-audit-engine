---
title: "NFX UX-Audit Framework"
version: "2.1"
status: "stable"
last_updated: "2025-11-13"
author: "Ben Sikasa (NFX) & Noa"
description: "Ein heuristisches, agentenfähiges Framework zur automatisierten UX-Analyse von Websites."
tags:
  - UX
  - Usability
  - Audit
  - Heuristics
  - NFX
  - Conversion
  - Navigation
  - Information Architecture
  - Emotional Design
repository: "https://github.com/blaktonic/nfx-audit-engine"
framework_type: "operational"
changelog:
  - version: "2.1"
    changes:
      - "Navigation und In-Page Navigation getrennt"
      - "Formularstrecke als eigene Rubrik ergänzt"
      - "Barrierefreiheit und Alt-Texte vollständig entfernt"
      - "Lesbarkeitskriterien erweitert (Satzlänge, Komposita)"
      - "CTA-Ziel-Check & Button-Link-Matching ergänzt"
      - "Doppelte Kriterien entfernt (V2, V5, R2, R3, W5, W6)"
      - "Nur ein Primärziel & max. 2–3 Sekundärziele"
      - "Responsiveness-Bereich gestrafft"
      - "Emotion/Engagement überarbeitet (Medienmix, Sprache)"
---

# **NFX UX-Audit Framework 2.1**
*(Bereinigt, optimiert, agentenfähig)*

Dieses Framework beschreibt ein vollständig operationalisierbares System, mit dem ein autonomer Agent einen hochwertigen, qualitativ fundierten UX-Audit durchführt.  
Es basiert auf den Heuristiken **Don’t Make Me Think**, **Guide Me** und **Create Emotional Impact**.

**Wichtig:** Barrierefreiheit und technische Performance sind *nicht Teil dieses Frameworks* und werden separat betrachtet.

---

# **0 – Briefing-Intro (muss vor Audit ausgefüllt werden)**

Der Agent fragt folgende Angaben ab:

| Kategorie | Beschreibung / Beispiele |
|---|---|
| **Branche / Industrie** | Energie, Bank, SaaS, Handel, NGO … |
| **Produkt / Service-Art** | Versicherung, Tarif, Subscription, physisches Produkt … |
| **Seitentyp / Kategorie** | Landing Page, Produktseite, Microsite, Shop, Blog, Hilfe … |
| **Funnel-Phase** | Awareness, Consideration, Purchase/Conversion, Retention |
| **Primäres Ziel (GENAU 1)** | Lead **oder** Kauf **oder** Termin **oder** Registrierung |
| **Sekundäre Ziele (max. 2–3)** | Newsletter, Social Follow, Vertiefungs-Content |
| **Zielgruppen** | Segmente, Personas, B2B/B2C |
| **Markenwerte / Tone of Voice** | optional |
| **KPIs** | CR, CTR, Bounce Rate, Sign-ups |

> Wenn mehr als 1 Primärziel oder mehr als 3 Sekundärziele angegeben werden,  
> **erzwingt der Agent eine Entscheidung**.

---

# **Audit-Philosophie**

**1. Don’t Make Me Think**  
Einfache, klare, verständliche Inhalte. Keine kognitiven Barrieren.

**2. Guide Me**  
Die Seite leitet sauber durch Navigation, Struktur und Zielführung.

**3. Create Emotional Impact**  
Marke spürbar machen. Vertrauen erzeugen. Medien sinnvoll einsetzen.

---

# **Evidenz- und Befundschema**

Jedes Issue wird so dokumentiert:

| Feld | Beschreibung |
|---|---|
| **Status** | ✅ erfüllt • ⚠️ teilweise • ❌ nicht erfüllt |
| **Priorität** | High / Medium / Low |
| **Evidenz (Code)** | DOM-Selektoren, Attribute, Textstellen |
| **Evidenz (Visuell)** | Screenshots + Viewport |
| **Empfehlung** | Was • Warum • Wie (konkret, technisch realisierbar) |

---

# **Kategorien & Kriterien**

Alle Kategorien wurden auf Redundanzen geprüft und methodisch geschärft.  
Barrierefreiheit und technische Performance sind ausgelagert.

---

# **Kategorie 1 – Einfachheit (Simplicity)**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **E1 – Konsistenz & CTA-Klarheit** | Buttons korrekt semantisch (`button`, `a`), Ziel-URL passt zum Text. | Primär/sekundär-CTAs klar unterscheidbar; States sichtbar. |
| **E2 – Essentielle Inhalte vollständig & ausreichend tief** | Produktdetails, Vorteile, Kontakt etc. | Inhalte nicht nur vorhanden, sondern **ausreichend erklärt**, nicht oberflächlich. |
| **E3 – Verständliche Anweisungen (UX Writing, Formulare)** | klare Labels, Verben, `aria-labels`. | Formulare logisch geführt. |
| **E4 – Lesbarkeit: kurze Sätze & wenig Füllwörter** | Sätze >20 Wörter flaggen; überlange Komposita markieren. | Listen, Fettungen, Absätze statt Textwüsten. |
| **E5 – Aktive / gesprochene Sprache** | direkte Ansprache, 2. Person. | aktivierende Formulierungen sichtbar. |

---

# **Kategorie 2 – Verständlichkeit (Clarity)**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **V1 – Einfache Sprache / verständliche Begriffe** | Jargon markiert, Glossar möglich. | Tooltips, Erklärtexte. |
| **V3 – Informationshierarchie** | saubere `<h1>`–`<h6>` Struktur. | klare typografische Hierarchie. |
| **V4 – Konsistente Begriffe & Labels** | Einheitliche Terminologie. | Navigation & Buttons konsistent. |
| **V6 – Lesbarkeit durch Struktur** | logische DOM-Reihenfolge. | Listen, Fettungen, klare Gliederung. |

---

# **Kategorie 3 – Navigation (Seite)**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **N1 – Hauptnavigation logisch & klar** | `<nav>` vorhanden, sinnvolle Menülogik. | max. 7±2 Hauptpunkte. |
| **N2 – Auffindbarkeit zentraler Inhalte** | Breadcrumbs, interne Links. | Suchfeld sichtbar, klare Menüs. |
| **N3 – Navigation *innerhalb* der Seite** | funktionierende Anker, IDs korrekt. | Inhaltsverzeichnis/Sprungmarken. |
| **N4 – Mobile Header fokussiert** | vereinfachte Struktur im Code. | wichtigste Infos im ersten Mobile-Viewport. |

---

# **Kategorie 4 – Formular- & Antragsstrecken**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **F1 – Logische Gruppierung** | Feldsets, saubere Validierung. | klarer Flow, nicht überfrachtet. |
| **F2 – Goal Gradient Effekt** | Fortschritt via `step=x of y`. | Progressbar sichtbar. |
| **F3 – Fehlermeldungen & Hilfen** | Inline-Errors, `required`. | Fehler direkt am Feld. |
| **F4 – Erwartbare CTA-Zielseiten** | Primäre CTAs führen zur *richtigen* nächsten Funnel-Seite. | logischer Schritt-Flow. |
| **F5 – UX Writing auf Abschluss-/Formularseiten** | klare Labels, spezifische Fehlermeldungen, Microcopy („Warum wir das fragen“), Nutzen-CTA. | klare Erwartungsrahmen („Dauert 2 Min.“), hilfreiche Hinweise und Handlungsanweisungen, vertrauensbildende Texte. |


---

# **Kategorie 5 – Zielfokus (Goal Focus)**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **Z1 – Nur EIN primäres Ziel** | genau *ein* `.primary-cta`. | ein dominanter CTA über dem Fold. |
| **Z1.1 – Sekundärziele klar nachgeordnet** | max. 2–3 `.secondary-cta`. | sichtbar kleiner / dezenter. |
| **Z2 – CTA-Texte prägnant** | Verb + Nutzen. | max. 4 Wörter. |
| **Z3 – Abschlussrelevante Inhalte früh platziert** | DOM-Reihenfolge korrekt. | USP + CTA im 1.–3. Viewport. |
| **Z4 – Trust & Biases** | valide Elemente. | angemessene Präsenz. |

---

# **Kategorie 6 – Wiedererkennung (Recognition)**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **W1 – Klarer Absender** | Logo, Title, Meta korrekt. | Marke sofort erkennbar. |
| **W2 – Konsistentes Designsystem** | CSS-Variablen, Layout-Patterns. | wiederkehrende Bild-/Farblogik. |
| **W3 – Markenidentität** | Mission/Values sichtbar. | Ton, Farbwelt, Bildsprache passend. |
| **W4 – Glaubwürdigkeit** | keine Überversprechen. | Testimonials realistisch. |

---

# **Kategorie 7 – Relevanz**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **R1 – Nutzerrelevante Inhalte** | USPs/Features konsistent. | keine Textwüsten. |
| **R2 – Headlines als Nutzen** | „Was bekomme ich?“ klar beantwortet. | Nutzen statt Funktionslabel. |
| **R3 – Aktualität** | Content frisch. | zeitgemäße Bildwelt. |
| **R4 – Nutzerprobleme antizipieren** | FAQs, Hilfen. | Antworten sichtbar. |

---

# **Kategorie 8 – Emotion & Engagement**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **EM1 – Medienmix** | `<img>`, `<video>`, `<audio>`. | Hero-Visual vorhanden. |
| **EM2 – Aktive, gesprochene Sprache** | direkt, 2. Person. | aktivierende Headlines. |
| **EM3 – Emotionale Relevanz** | emotionale Wortfelder. | Stimmung passend zur Marke. |
| **EM4 – Microinteractions** | kleine Effekte. | Hover/Motion sichtbar. |

---

# **Kategorie 9 – Responsiveness**

| ID | Kriterium | Code-Regeln | Visuelle Regeln |
|---|---|---|---|
| **RS1 – Mobile Lesbarkeit** | Media Queries, responsive Units. | Abstände & Typografie sauber. |
| **RS2 – Sections nicht zu lang** | lange DOM-Blöcke flaggen. | ≤1–1,5 Viewports pro Abschnitt. |
| **RS3 – Struktur bleibt erhalten** | logische Reihenfolge. | kein Chaos durch Stacking. |

---

# **Aus dem Framework entfernt / ausgelagert**

❌ Alt-Texte / Barrierefreiheit  
❌ PageSpeed / technische Performance  
❌ Redundante Kriterien (V2, V5, R2, R3, W5, W6, U5)  
❌ Gamification (nur Progressbar bleibt)

---

# **Ablaufplan für den Agenten**

1. Briefing ausfüllen (inkl. Ziel-Check)  
2. Seite öffnen (Desktop/Tablet/Mobile)  
3. Screenshots erzeugen  
4. DOM extrahieren  
5. Kriterien prüfen  
6. Quick-Wins identifizieren  
7. Report generieren (+ optional JSON)

