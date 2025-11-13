# **UX-Audit-Framework-Optimiert.md**

Dieses Dokument beschreibt ein vollständig operationalisierbares Framework, mit dem ein autonomer Agent einen UX-Audit durchführen kann.  
Es basiert auf den heuristischen Kategorien (**Don’t make me think**, **Guide me** und **Create emotional impact**) und branchenspezifischen Best Practices.  
Das Framework wurde angepasst, um ohne numerisches Scoring auszukommen und stattdessen qualitative Befunde mit **Status**, **Priorität** und **Evidenz** zu erfassen.  
Themen wie **Barrierefreiheit** und **technische Performance** sind ausgelagert und werden als optionale Zusatzmodule geführt.

---

## **0 – Briefing-Intro (vor Auditbeginn)**

Vor Beginn fragt der Agent folgende Informationen ab, um Kontext und Zielrahmen zu definieren:

| Kategorie | Beschreibung / Beispiel |
| :--- | :--- |
| **Branche / Industrie** | Energie, Bank, SaaS, E-Commerce, Bildung, NGO, Medien … |
| **Produkt / Service-Art** | Stromtarif, Versicherung, Subscription, physisches Produkt … |
| **Seitentyp / Kategorie** | Corporate Site / Landing Page / Shop / SaaS-Seite / Kundenportal / Blog / Hilfe / Portfolio / Microsite / Community |
| **Customer Journey Phase / Marketing Funnel** | Awareness / Consideration / Purchase Decision / Retargeting / Retention / Advocay |
| **Primäre Ziele (max 3)** | Lead / Kauf / Kontakt / Termin / Download |
| **Sekundäre Ziele** | … |
| **Zielgruppen / Segmente** | … |
| **Markenwerte / Ton** | optionale Brand-Guide-Angabe |
| **KPIs (falls vorhanden)** | CR, CTR, Sign-ups, Bounce … |

> Wenn kein Seitentyp genannt ist, leitet der Agent ihn aus Struktur und Funktion ab und notiert die Annahme im Report.

---

## **Audit-Philosophie**

* **Don’t make me think** – Inhalte sollen leicht verständlich sein.  
  Nutzer:innen dürfen im Flow nicht ins Stocken geraten, weil Strukturen oder Begriffe ungewohnt sind.  
* **Guide me** – Die Seite muss Zielhandlungen klar kommunizieren, durch Struktur und Navigation leiten und entscheidungsrelevante Informationen priorisieren.  
* **Create emotional impact** – Markenidentität, Vertrauen und Gestaltung erzeugen Emotion und Glaubwürdigkeit.  

---

## **Evidenz- und Befundschema (ohne Scores)**

Jedes Kriterium wird mit folgender Struktur bewertet:

| Feld | Beschreibung |
| :--- | :--- |
| **Status** | ✅ Erfüllt   /  ⚠️ Teilweise   /  ❌ Nicht erfüllt |
| **Priorität** | High / Medium / Low  (Impact × Aufwand) |
| **Evidenz (Code)** | Relevante DOM-Selektoren, Attribute, Texte |
| **Evidenz (Visuell)** | Screenshot-Ausschnitt (+ Viewport-Angabe) |
| **Empfehlung (3-teilig)** | **Was** – Handlung   • **Warum** – Prinzip / Heuristik   • **Wie** – technischer Vorschlag (CSS/HTML/JS) |

---

## **Kategorien & Kriterien**

Die Kategorien folgen den Heuristiken und beinhalten nur UX-relevante Aspekte.  
Barrierefreiheit und technische Leistung sind bewusst nicht enthalten (siehe Module A & B).

---

### **Kategorie 1 – Einfachheit (Simplicity)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| E1 | Konsistenz der Interaktionselemente (**Jakob’s Law**) | Buttons sind `<button>` oder `<a role="button">`; keine `<div onclick>`; einheitliche Komponentenklassen | Buttons sehen überall gleich aus (Farbe, Radius, States) |
| E2 | Essentielle Inhalte & Funktionen vorhanden | Schlüsselelemente im DOM (z. B. Produktinfo, Kontakt, Pricing); Formularfelder mit `required` | Erwartete Bereiche sichtbar und leicht zugänglich |
| E3 | Eindeutige Zielhandlungsanweisung | CTA-Texte mit Verben und sinnvollen `aria-labels` | CTA prominent, kontrastreich, gut abgesetzt |
| E4 | Redundanzen & Füllwörter vermeiden | Textanalyse auf > 20 Wörter und Füllwörter | Kurze Absätze, Weißraum, guter Lesefluss |
| E5 | Gesprochene Sprache / aktivierende Fragen | 2. Person, Frageformen, wenig Passiv | Kurze direkte Texte sichtbar hervorgehoben |

---

### **Kategorie 2 – Verständlichkeit (Clarity)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| V1 | Einfache Sprache, Jargon erklärt | Fachbegriffe markiert (`abbr` oder Glossar) | Erklärungen neben Text oder via Tooltip |
| V2 | Vollständigkeit der Informationen | Pflichtfelder, Fehlermeldungen, FAQ-Bereiche | Preise, Leistungen, Beschreibungen vorhanden |
| V3 | Klare Informationshierarchie | Korrekte `<h1>`–`<h6>` Reihenfolge | Abstände, Typografie, Raster klar erkennbar |
| V4 | Konsistente Benennungen | gleiche Funktion = gleicher Begriff | Labels / Menüs / Buttons einheitlich |
| V5 | Aussagekräftige Headlines | H1–H3 mit Schlüsselbegriffen | Headlines optisch dominant, prägnant |

---

### **Kategorie 3 – Responsiveness (Responsivität)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| R1 | Angepasste Informationstiefe | Absätze > 3 Screens flaggen | Scrolltiefe vs. Informationsdichte |
| R2 | Nutzung nativer Gerätefunktionen | Standard-Inputs (`select`, `date`) oder saubere ARIA-Customs | Erwartetes Look & Feel des Systems |
| R3 | Lesbarkeit auf kleinen Geräten | Media-Queries, Fonts ≥ 16 px | Zeilenlänge 45–70 Zeichen, Kontrast OK |

> *Performance-Metriken (LCP u. a.) sind nicht Teil dieser Kategorie – siehe Modul B.*

---

### **Kategorie 4 – Navigation**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| N1 | Einfache Antrags- / Checkout-Strecke | Formulare logisch gruppiert, Feedback vorhanden | Feldanzahl / Progress angemessen |
| N2 | Auffindbarkeit wichtiger Inhalte | `<nav>`, interne Links, Breadcrumbs | Suche, Menü, Filter klar sichtbar |
| N3 | Klare Heading-Struktur | keine Heading-Sprünge | Visuelle Hierarchie entspricht Semantik |
| N4 | Navigation & Seitenstruktur (**Miller’s Law**) | ≤ 7 ± 2 Hauptpunkte | Header, Footer, Breadcrumbs eindeutig |
| N5 | Visuelle Strukturierung | Heading-Styles in CSS definiert | Abstände, Alignment, 8-px-Grid konsistent |
| N6 | Fehlervermeidung & Hilfe (**Heuristik 5 & 9**) | `input:invalid`, `required`, Inline-Hilfen | Fehlertexte direkt am Feld, Pflichtmarkierung |

---

### **Kategorie 5 – Zielfokus (Goal Focus)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| Z1 | Primäres Ziel klar abgrenzbar (**Isolation Effect**) | ein primärer CTA, keine gleichwertigen Sekundär-CTAs | Farb-/Größenabhebung klar erkennbar |
| Z2 | Call-to-Action-Texte | Handlungsverben, prägnant | kurz (< 4 Wörter), kontextstark |
| Z3 | Platzierung wichtiger Inhalte (**Above-the-Fold**) | Kernbotschaft + CTA im ersten Screen | USP + CTA sofort sichtbar |
| Z4 | Biases & UX-Laws (Framing, Social Proof, Trust) | Preissignale, Testimonials, Badges | prominent, nicht aufdringlich |

---

### **Kategorie 6 – Wiedererkennung (Recognition)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| W1 | Klarer Absender / Branding | Logo im `<header>`, `<title>`, `meta description` | Marke sofort erkennbar |
| W2 | Konsistente Gestaltung | CSS-Variablen / Klassen wiederkehrend | Bild- und Farbwelt kohärent |
| W3 | Markenidentität spürbar | Mission / Values im DOM | Bildsprache & Ton entsprechen Marke |
| W4 | Glaubwürdigkeit & Versprechen | Buzzwords vermeiden, Abgleich AGB | Testimonials / Zertifikate plausibel |
| W5 | Abgrenzung zur Konkurrenz | optional Text-Similarity-Check | eigene Bilder statt Stock |
| W6 | Brand-Guide-Konformität | Terminologie-Abgleich mit Guide | Orthografie, Schreibweisen einheitlich |

---

### **Kategorie 7 – Relevanz**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| Rlv1 | Essenzielle Inhalte & Features | USPs / Kontakt vorhanden | USP, Preis, Vorteile sichtbar |
| Rlv2 | Zielgruppen-spezifischer Content | Segmentierung / Personalisierung | Bildwelt & Beispiele passen |
| Rlv3 | Präsentation der USPs | Abschnitt „Warum wir“ o. Ä. | Icons / Listen / Hervorhebung |
| Rlv4 | Aktualität der Inhalte | Datumsangaben / Versionen | Texte / Bilder zeitgemäß |
| Rlv5 | Relevante Suchbegriffe (SEO light) | `<title>`, `meta description>`, `<h1>` | Keywords sichtbar im Text |
| Rlv6 | Nutzerprobleme antizipieren | FAQ / Help / Live-Chat vorhanden | kritische Fragen vorweggenommen |

---

### **Kategorie 8 – Unterhaltungswert (Engagement)**

| ID | Kriterium | Codebasierte Prüfregeln | Visuelle Prüfregeln |
| :--- | :--- | :--- | :--- |
| U1 | Emotionale Gestaltung | emotionale Wortfelder, `alt`-Texte | Farb- / Bildwirkung stimmig |
| U2 | Medienmix | `<video>`, `<audio>`, `<svg>` vorhanden, zugänglich | Medien sinnvoll eingesetzt |
| U3 | Aktive Sprache | wenig Passiv, Verben prägnant | CTAs / Headlines aktiv |
| U4 | Emotionale Ansprache | Begriffe wie „Sicherheit“, „Freude“ | Testimonials / Story-Elemente |
| U5 | Gamification & Feedback | Fortschritt, Punkte, Micro-Interactions | Animationen / Belohnungen vorhanden |

---

## **Ablaufplan für den Agenten (ohne Scores)**

1. **Vorbereitung / Infos holen**  
   * Framework laden (diese Datei)  
   * Briefing-Intro ausfüllen (Branche, Ziele usw.)  
   * Optional: Brand-Guide verknüpfen  
2. **Seite analysieren**  
   * URL öffnen (Desktop 1440×900, Tablet 768×1024, Mobile 360×640)  
   * Screenshots (Above-the-Fold + Full-Page) erstellen  
   * DOM extrahieren (HTML + CSS + JS)  
   * Kriterien prüfen – je Kategorie / Kriterium Status + Priorität + Evidenz + Empfehlung  
3. **Quick Wins identifizieren** – hoher Impact, geringer Aufwand  
4. **Audit-Bericht erzeugen** (siehe Template) + optional JSON-Export aller Issues  

---

## **Audit-Output-Template**

```markdown
# UX-Audit für <Hostname> 
<Datum>
<Framework Version>
