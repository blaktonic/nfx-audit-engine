# **NFX Audit Engine 1.1 – UX & Content Evaluation Framework**  
##   
## **Mission**  
Ein reproduzierbares, KI‑kompatibles Framework für UX‑Audits, das Findings **identifiziert**, **bewertet** und in **priorisierte, messbare Handlungsempfehlungen** überführt.  
  
## **1 · Philosophie**  
UX‑Audits werden **ergebnisoffen** durchgeführt. Es werden nur belegbare Beobachtungen dokumentiert – kein Bauchgefühl, keine Pflicht‑Findings. Kommentare bleiben kurz, präzise und neutral. Unsichere Einschätzungen werden als Frage formuliert und farblich markiert (z. B. gelb).  
  
## **2 · Bewertungssystem**  
## **2.1 Scoring‑Skala**  

| Score | Bedeutung          |
| ----- | ------------------ |
| 0     | Nicht erfüllt      |
| 1     | Teilweise erfüllt  |
| 2     | Weitgehend erfüllt |
| 3     | Voll erfüllt       |
  
**Maximalwert pro Kriterium:** 3   **Gesamtscore:** gewichteter Mittelwert über alle Kategorien (Ausgabe 0–100)  
## **2.2 Kategorie‑Gewichtungen**  

| Kategorie         | Gewicht |
| ----------------- | ------- |
| Verständlichkeit  | 1.5     |
| Einfachheit       | 1.5     |
| Zielfokus         | 1.5     |
| Navigation        | 1.5     |
| Responsiveness    | 1.0     |
| Wiedererkennung   | 1.0     |
| Relevanz          | 1.0     |
| Unterhaltungswert | 0.5     |
  
## **3 · Audit‑Regeln**  
1. Pro Screenshot oder Seite maximal 3–5 Findings.2. Keine Kommentare ohne Evidenz.3. Kommentare: 1–2 Sätze, sachlich.4. Unsichere Beobachtungen als Frage formulieren und markieren.  
  
## **4 · Finding‑Schema**  

| Feld             | Beschreibung                                  |
| ---------------- | --------------------------------------------- |
| Kategorie        | Prüfkategorie (z. B. „Verständlichkeit“)      |
| Kriterium        | Konkreter Prüfaspekt innerhalb der Kategorie  |
| Evidence         | Konkrete Beobachtung oder Beispiel            |
| Location         | Abschnitt / Viewport / Koordinaten (optional) |
| Severity         | low / medium / high                           |
| Comment          | Kurzkommentar (1–2 Sätze)                     |
| Suggestion Style | optional / evidence_based / question          |
  
## **5 · Kategorien & Kriterien**  
## 🟩** Verständlichkeit (1.5)**  
1. **Einfache, klare Sprache** – Vermeide Fachjargon und doppeldeutige Formulierungen.  2. **Vollständigkeit & Informationshierarchie** – Alle relevanten Informationen sind vorhanden und logisch strukturiert.  3. **Konsistente Begriffe / Fachbegriffe erklärt** – Einheitliche Terminologie; Abkürzungen sind erläutert.  
4. **Headlines fassen Inhalte zusammen** – Überschriften sind aussagekräftig und informieren über den Inhalt.  
## 🟦** Einfachheit (1.5)**  
1. **Interaktionselemente wie gewohnt nutzbar** – Buttons, Links und Formulare funktionieren erwartungsgemäß.  
2. **Essentielle Inhalte & Features vorhanden** – Wichtige Funktionen sind sichtbar; First‑Screen enthält die Primärfunktion. 3. **Klare Handlungsanweisungen** – CTAs sind verständlich formuliert; Hilfstexte unterstützen die Nutzer.  
4. **Kurze Sätze / keine Füllwörter** – Informationen sind auf das Wesentliche reduziert.  
## 🟧** Navigation (1.5)**  
1. **Wichtige Inhalte schnell auffindbar** – Wenige Klicks; Filter / Suche bei Bedarf.  
2. **Klare Headline‑Struktur** – Logische H‑Hierarchie.  
3. **Eindeutige Navigation** – Menüs sind konsistent und verständlich.  
4. **Zielerreichung mit minimalen Schritten** – Keine unnötigen Pflichtfelder.  
5. **Visuelle Struktur mit Abständen & Absätzen** – Keine „Textwände“; ausreichend Weißraum.  
## 🟥** Zielfokus (1.5)**  
1. **Primäres Ziel klar sichtbar** – CTA above‑the‑fold; keine ablenkenden Nebenaktionen.  
2. **Call‑to‑Actions deutlich formuliert** – Eindeutige Labels, kein Wettbewerb zwischen CTAs.  
3. **Wichtige Inhalte am Anfang** – Nutzenargumente früh platzieren.  
4. **UX Laws nutzen** (Framing, Isolation, Trust) – Vertrauenssignale integrieren.  
5. **Ladezeiten beachten** – Vermeide große Assets; gestalte den First Fold performant.  
## 🟨** Responsiveness (1.0)**  
1. **Textlänge dem Device anpassen** – Kurze Absätze; optimale Zeilenlänge.  
2. **Native Device‑Features nutzen** – Autofill, native Input‑Picker.  
3. **Darstellung mobil klar erkennbar** – Keine Überlappungen; kein horizontales Scrollen.  
## 🟪** Wiedererkennung (1.0)**  
1. **Klarer Absender sichtbar** – Absender sofort erkennbar.  
2. **Konsistenter Look & Bildwelt** – Einheitliche Gestaltung.  
3. **Markenidentität spürbar** – Purpose & Werte erkennbar.  
4. **Glaubwürdige Infos, keine Übertreibungen** – Authentizität.  
5. **Differenzierung zum Wettbewerb** – Unique Selling Points.  
## 🟫** Relevanz (1.0)**  
1. **Zielgruppen‑spezifischer Content** – Inhalte passen zur Zielgruppe.  
2. **USPs klar kommuniziert** – Mehrwert wird deutlich.  
3. **Essenzielle Features integriert** – Funktionen entsprechen den Erwartungen.  
## 🟧** Unterhaltungswert (0.5)**  
1. **Emotionales Design & Bildwelt** – Ansprechende Visuals.  
2. **Interaktive Elemente / Videos / Grafiken** – Interaktionen lockern den Content auf.  
3. **Keine langen Textblöcke** – Inhalte sind angenehm lesbar.  
4. **Direkte Ansprache, aktive Sprache** – Nutzende werden persönlich adressiert.  
5. **Bezug zu Gefühlen der User** – Inhalte sprechen Emotionen an.  
  
## **6 · Praktischer Ablauf im Audit**  
1. Screenshots oder Live‑Seiten werden viewport‑basiert analysiert.  

2. Für jede relevante Kategorie werden Beobachtungen eingetragen.  

3. Zu jeder Evidence wird ein kurzes Kommentar‑Template verwendet.  

4. Scores werden je Kriterium gesetzt (0–3).  

5. Die Engine berechnet den gewichteten Gesamtscore und eine Top‑3‑Liste kritischer Findings.  

6. Nach Abschluss der Bewertung erzeugt die Engine **automatisch Handlungsempfehlungen** (Abschnitt 6a).  
  
## **6a · Handlungsempfehlungen & Ticketing (Action Synthesis)**  
## **Ziel**  
Aus Findings werden klare, umsetzbare Tasks mit Priorität, Akzeptanzkriterien und Owner abgeleitet. Ergebnisse können automatisiert in Tools wie Jira, Asana, Figma‑Kommentare oder Slack‑Feeds übertragen werden.  
## **Priorisierungsformel**  
```

priority_score = severity_weight × category_weight × impact_estimate × confidence

```

| Parameter       | Bedeutung                       |
| --------------- | ------------------------------- |
| severity_weight | low = 1 · medium = 2 · high = 3 |
| category_weight | entspricht Tabelle oben         |
| impact_estimate | 0.5 – 1.5 (je nach Auswirkung)  |
| confidence      | 0.6 – 1.0 (Evidenzklarheit)     |
  
**SLA‑Richtwerte:**  
* high (≥ 4.5) → innerhalb 3–5 Tagen  
* medium (3.0 – 4.49) → 10–14 Tage  
* low (< 3.0) → einplanen im nächsten Sprint  
## **Action‑Typen (Heuristik)**  

| Typ             | Beschreibung                                    |
| --------------- | ----------------------------------------------- |
| Copy/Content    | Microcopy, Headlines, Struktur                  |
| UX‑Flow/IA      | Klickpfade, Navigation, Reduktion von Schritten |
| UI/Visual       | Abstände, Bildwelt, Typografie, Design Tokens   |
| CTA/Conversion  | Labeling, Platzierung, Framing, Trust           |
| Responsive/Tech | Breakpoints, Inputs, Performance                |
  
****Ableit‑Regeln (Mapping)****  

| Kriterium | Abgeleitete Action |
| ---------------------------------------- | ------------------------------------------------------------- |
| Einfache, klare Sprache | Copy‑Rewrite mit Plain‑Language‑Guideline |
| Vollständigkeit & Informationshierarchie | Struktur‑Refactor (H‑Level, Reihenfolge, Inhaltsverzeichnis) |
| Primäres Ziel sichtbar / CTA | CTA‑Optimierung: above‑the‑fold, eindeutiges Label, Isolation |
| Textlänge dem Device anpassen | Responsive Text‑Splits, kürzere Absätze |
| Wichtige Inhalte auffindbar | IA‑Kürzung: Klickpfade, prominente Suche/Filter |
| Konsistenter Look & Bildwelt | Design‑Konsolidierung: Tokens synchronisieren |
| Ladezeiten beachten | Asset‑Optimierung: Bildgrößen reduzieren, Lazy‑Loading |
  
****Output‑Schema (Beispiel)****  
```

{
  "recommendation_id": "REC-001",
  "from_finding_id": "FND-123",
  "title": "CTA im Hero klar und sichtbar machen",
  "action_type": "CTA/Conversion",
  "owner_role": "UX Writer / Designer",
  "priority_score": 5.4,
  "severity": "high",
  "effort_tshirt": "S",
  "dependencies": ["Design Tokens", "Tracking Spec"],
  "steps": [
    "CTA‑Label von 'Start Onboarding' zu 'Jetzt Konto eröffnen' ändern",
    "CTA above‑the‑fold positionieren und visuelle Isolation schaffen",
    "Trust‑Signale direkt in CTA‑Nähe ergänzen"
  ],
  "acceptance_criteria": [
    "CTA ist auf 1366×768 und 390×844 sofort sichtbar",
    "Label beschreibt die Aktion explizit (Verb + Ziel)",
    "Mindestens ein Trust‑Signal im direkten Umfeld (<120px)"
  ],
  "metrics": [
    "CTR des Hero‑CTA steigt um 15 % gegenüber Baseline",
    "Time‑to‑CTA‑Click sinkt um 10 %"
  ],
  "notes": "Framing muss mit der Brand Voice konsistent sein."
}

```
## **Ticket‑Template (Jira / Asana)**  
**[TITLE]** {action_type}: {kurze Maßnahme} – {Seite/Abschnitt}  
**[BESCHREIBUNG]**Aus Finding {FND-ID}: {evidence}Problem: {kriterium} in {location} | Severity: {severity}  
**[ZIEL]**{user_outcome} (z. B. schnellere Zielerreichung, klarere Entscheidung)  
**[SCHRITTE]**  
* …  
* …  
**[AKZEPTANZKRITERIEN]**  
* …  
* …  
**[IMPACT & PRIORITÄT]**priority_score: {score} | Effort: {T‑Shirt} | SLA: {high/medium/low}  
**[ABHÄNGIGKEITEN]**Design Tokens / Tracking / Backend  
**[METRIKEN]**CTR, Conversion Step‑Through, Dwell Time …  
## **Figma‑Kommentar‑Snippet (Kurzform)**  
**Finding FND‑123 → REC‑001:**CTA zu vage & zu spät sichtbar. Maßnahme: Label präzisieren, above‑the‑fold platzieren, Trust‑Signale hinzufügen.**Akzeptanz:** CTA sichtbar bei 1366×768 und 390×844, Label enthält Verb + Ziel, mindestens ein Trust‑Signal.  
## **n8n‑Flow (Beispiel‑Orchestrierung)**  
Webhook/Ingest → Findings JSON→ Function Node (berechnet priority_score)→ LLM Node (Action‑Synthesis nach Regeln)→ Branching → Tickets (Jira / Asana API), Figma Comments, Slack Digest→ Datastore (Airtable/GSheet) für Roadmap & Tracking→ QA Node (Acceptance‑Check via LLM: „Sind Kriterien messbar?“)  
## **Prompt‑Baustein (LLM) – Action‑Synthesis**  
**System:**Du bist eine UX‑Audit‑Engine. Du wandelst Findings in klare, umsetzbare Maßnahmen um.Nutze die Kategorien, Gewichte und Regeln aus dieser Spezifikation. Keine Meinungen ohne Evidenz.  
**User:**Konvertiere das Finding in maximal zwei konkrete Empfehlungen.• Wähle passenden action_type.• Generiere title, steps (3–5), acceptance_criteria (3–5), metrics (2), owner_role, effort_tshirt.• Berechne priority_score gemäß Formel.• Gib das Ergebnis als JSON im „recommendation“-Schema aus.  
## **Minimal‑Validator (Guardrails)**  
* Enthält die Empfehlung Akzeptanzkriterien?  
* Sind Metriken vorhanden und realistisch?  
* Sind Owner & Effort definiert?  
* Sind die Schritte klar umsetzbar (keine Floskeln)?  
* Ist der Bezug zur Evidence hergestellt?  
  
## **7 · YAML‑Promptbasis für LLMs**  
```

audit_engine:
  name: "NFX Audit Engine 2.0"
  mission: "Ein reproduzierbares, KI‑kompatibles Framework für UX‑Audits, das Findings identifiziert, bewertet und in priorisierte, messbare Handlungsempfehlungen überführt."
  philosophy:
    - Nur bei Evidenz kommentieren
    - Keine Pflicht‑Findings
    - Kurz, präzise, neutral
    - Unsicherheit = Frage (markiert)
  scoring:
    scale: {0: "nicht erfüllt", 1: "teilweise erfüllt", 2: "weitgehend erfüllt", 3: "voll erfüllt"}
    weights:
      Verständlichkeit: 1.5
      Einfachheit: 1.5
      Zielfokus: 1.5
      Navigation: 1.5
      Responsiveness: 1.0
      Wiedererkennung: 1.0
      Relevanz: 1.0
      Unterhaltungswert: 0.5
  action_synthesis:
    priority_formula: "severity_weight * category_weight * impact_estimate * confidence"
    sla_mapping:
      high: "3-5 Tage"
      medium: "10-14 Tage"
      low: "nächster Sprint"
    action_types:
      - Copy/Content
      - UX-Flow/IA
      - UI/Visual
      - CTA/Conversion
      - Responsive/Tech
    mapping_rules:
      Verständlichkeit: ["Copy Rewrite"]
      Einfachheit: ["UX-Flow Optimierung"]
      Zielfokus: ["CTA/Conversion"]
      Responsiveness: ["Responsive/Tech"]
      Wiedererkennung: ["UI/Visual"]
    output_fields:
      - recommendation_id
      - from_finding_id
      - title
      - action_type
      - owner_role
      - priority_score
      - steps
      - acceptance_criteria
      - metrics
      - notes

```
  
## **8 · Ziel**  
Eine einheitliche, skalierbare Audit‑Engine, die UX‑ und Content‑Qualität objektiv bewertet, messbar macht und automatisch in handlungsreife Tasks übersetzt – inklusive Priorisierung, Messgrößen und Tool‑Integration.  
