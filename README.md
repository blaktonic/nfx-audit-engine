# N**FX Audit Engine 1.2 – UX & Content Evaluation Framework**  
## **Mission**  
Ein reproduzierbares, KI-kompatibles Framework für UX-Audits, das Findings **identifiziert**, **bewertet** und in **priorisierte, messbare Handlungsempfehlungen** überführt.  
  
## **1 · Philosophie**  
Ergebnisoffene Prüfung.Nur belegbare Beobachtungen werden dokumentiert – kein Bauchgefühl, keine Pflicht-Findings.Kommentare bleiben kurz, präzise, neutral.Unsichere Einschätzungen werden als Fragen formuliert **und farblich markiert** (z. B. Gelb).  
  
## **2 · Bewertungssystem**  
## **2.1 Scoring-Skala**  

| Score | Bedeutung          |
| ----- | ------------------ |
| 0     | Nicht erfüllt      |
| 1     | Teilweise erfüllt  |
| 2     | Weitgehend erfüllt |
| 3     | Voll erfüllt       |
  
**Maximalwert pro Kriterium:** 3**Gesamtscore:** Gewichteter Mittelwert über alle Kategorien → Ausgabe 0–100  
## **2.2 Kategorie-Gewichtungen**  

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
  
## **3 · Audit-Regeln**  
1. Pro Screenshot oder Seite max. 3–5 Findings.  
2. Keine Kommentare ohne Evidenz.  
3. Kommentare: 1–2 Sätze, sachlich.  
4. Unsichere Beobachtungen als Frage formulieren und markieren.  
  
## **4 · Finding-Schema**  

| Feld             | Beschreibung                                  |
| ---------------- | --------------------------------------------- |
| Kategorie        | z. B. „Verständlichkeit“                      |
| Kriterium        | Prüfaspekt innerhalb der Kategorie            |
| Evidence         | Konkrete Beobachtung oder Beispiel            |
| Location         | Abschnitt / Viewport / Koordinaten (optional) |
| Severity         | low / medium / high                           |
| Comment          | 1–2 Sätze, evidenzbasiert                     |
| Suggestion Style | optional / evidence_based / question          |
  
## **5 · Kategorien & Kriterien**  
## 🟩** Verständlichkeit (1.5)**  
1. Einfache, klare Sprache  
2. Vollständigkeit & Informationshierarchie  
3. Konsistente Begriffe / Fachbegriffe erklärt  
4. Headlines fassen Inhalte zusammen  
## 🟦** Einfachheit (1.5)**  
1. Interaktionselemente wie gewohnt nutzbar  
2. Essentielle Inhalte & Features vorhanden  
3. Klare Handlungsanweisungen  
4. Kurze Sätze / keine Füllwörter  
## 🟧** Navigation (1.5)**  
1. Wichtige Inhalte schnell auffindbar  
2. Klare Headline-Struktur  
3. Eindeutige Navigation  
4. Zielerreichung mit minimalen Schritten  
5. Visuelle Struktur mit Abständen & Absätzen  
## 🟥** Zielfokus (1.5)**  
1. Primäres Ziel klar sichtbar  
2. Call-to-Actions deutlich formuliert  
3. Wichtige Inhalte am Anfang  
4. UX Laws nutzen (Framing, Isolation, Trust)  
5. Ladezeiten beachten  
## 🟨** Responsiveness (1.0)**  
1. Textlänge dem Device anpassen  
2. Native Device-Features nutzen  
3. Darstellung mobil klar erkennbar  
## 🟪** Wiedererkennung (1.0)**  
1. Klarer Absender sichtbar  
2. Konsistenter Look & Bildwelt  
3. Markenidentität spürbar  
4. Glaubwürdige Infos  
5. Differenzierung zum Wettbewerb  
## 🟫** Relevanz (1.0)**  
1. Zielgruppen-spezifischer Content  
2. USPs klar kommuniziert  
3. Essenzielle Features integriert  
## 🟧** Unterhaltungswert (0.5)**  
1. Emotionales Design & Bildwelt  
2. Interaktive Elemente / Videos / Grafiken  
3. Keine langen Textblöcke  
4. Aktive Sprache, direkte Ansprache  
5. Bezug zu Gefühlen der User  
  
## **6 · Praktischer Ablauf im Audit**  
1. Screenshots oder Live-Seiten werden viewport-basiert analysiert.  
2. Für jede Kategorie werden Beobachtungen dokumentiert.  
3. Jede Evidence erhält ein kurzes Kommentar-Template.  
4. Scores werden je Kriterium vergeben (0–3).  
5. Die Engine berechnet den gewichteten Gesamtscore & Top-3 Findings.  
6. Im Anschluss erzeugt die Engine **automatisch Handlungsempfehlungen** (siehe Abschnitt 6a).  
  
## **6a · Handlungsempfehlungen & Ticketing (Action Synthesis) **🔧  
## **Ziel**  
Aus Findings werden **klare, umsetzbare Tasks** mit Priorität, Akzeptanzkriterien und Owner abgeleitet.Ergebnisse können automatisiert an Jira, Asana, Figma-Kommentare oder Slack-Feeds übergeben werden.  
  
## **Priorisierungsformel**  
```

priority_score = severity_weight × category_weight × impact_estimate × confidence

```

| Parameter       | Bedeutung                       |
| --------------- | ------------------------------- |
| severity_weight | low = 1 · medium = 2 · high = 3 |
| category_weight | laut Tabelle oben               |
| impact_estimate | 0.5 – 1.5 (je nach Auswirkung)  |
| confidence      | 0.6 – 1.0 (Evidenzklarheit)     |
  
**SLA-Richtwerte:**  
* high (≥ 4.5) → innerhalb 3–5 Tagen  
* medium (3.0 – 4.49) → 10–14 Tage  
* low (< 3.0) → im nächsten Sprint  
  
## **Action-Typen (Heuristik)**  

| Typ             | Beschreibung                                    |
| --------------- | ----------------------------------------------- |
| Copy/Content    | Microcopy, Headlines, Struktur                  |
| UX-Flow/IA      | Klickpfade, Navigation, Reduktion von Schritten |
| UI/Visual       | Abstände, Bildwelt, Typografie, Tokens          |
| CTA/Conversion  | Labeling, Platzierung, Framing, Trust-Signale   |
| Responsive/Tech | Breakpoints, Inputs, Performance                |
  
## **Ableit-Regeln (Mapping-Beispiele)**  

| Kriterium | Abgeleitete Action |
| ----------------------------- | ---------------------------------------------------------------------- |
| Einfache, klare Sprache | Copy-Rewrite mit Plain-Language-Guideline |
| Vollständigkeit & Hierarchie | Struktur-Refactor: H-Level, Reihenfolge, Inhaltsverzeichnis |
| Primäres Ziel sichtbar / CTA | CTA-Optimierung: Above-the-Fold, eindeutiges Label, visuelle Isolation |
| Textlänge dem Device anpassen | Responsive Text-Splits, kürzere Absätze |
| Wichtige Inhalte auffindbar | IA-Kürzung, prominente Suche / Filter |
| Konsistenter Look & Bildwelt | Design-Konsolidierung: Tokens synchronisieren |
| Ladezeiten beachten | Asset-Optimierung: Bildgrößen, Lazy-Loading |
  
## **Output-Schema (empfohlen)**  
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
    "CTA-Label von 'Start Onboarding' zu 'Jetzt Konto eröffnen' ändern",
    "CTA above-the-fold platzieren, visuelle Isolation (Whitespace + Kontrast)",
    "Trust-Signale direkt in CTA-Nähe ergänzen"
  ],
  "acceptance_criteria": [
    "CTA ist auf 1366×768 und 390×844 sofort sichtbar",
    "Label beschreibt die Aktion explizit (Verb + Ziel)",
    "Mind. 1 Trust-Signal im direkten Umfeld (<120px)"
  ],
  "metrics": [
    "CTR Hero-CTA +15% ggü. Baseline",
    "Time-to-CTA-Click -10%"
  ],
  "notes": "Framing konsistent mit Brand Voice"
}

```
  
## **Ticket-Template (Jira / Asana)**  
**[TITLE]** {action_type}: {kurze Maßnahme} – {Seite/Abschnitt}**[BESCHREIBUNG]**Aus Finding {FND-ID}: {evidence}Problem: {kriterium} in {location} | Severity: {severity}  
**[ZIEL]**{user_outcome} (z. B. schnellere Zielerreichung, klarere Entscheidung)  
**[SCHRITTE]**– …– …  
**[AKZEPTANZKRITERIEN]**– …– …  
**[IMPACT & PRIORITÄT]**priority_score: {score} | Effort: {T-Shirt} | SLA: {high/medium/low}  
**[ABHÄNGIGKEITEN]**Design Tokens / Tracking / Backend  
**[METRIKEN]**CTR, Conversion Step-Through, Dwell Time …  
  
## **Figma-Kommentar-Snippet (Kurzform)**  
**Finding FND-123 → REC-001:**CTA zu vage & spät sichtbar. Maßnahme: Label präzisieren, Above-the-Fold, Trust-Signale daneben.**Akzeptanz:** sichtbar @1366 & @390, Verb + Ziel, ≥ 1 Trust-Signal.  
  
## **n8n-Flow (Beispiel-Orchestrierung)**  
Webhook/Ingest → Findings JSON→ Function Node (berechnet priority_score)→ LLM Node (Action-Synthesis nach Regeln)→ Branching → Tickets (Jira / Asana API), Figma Comments, Slack Digest→ Datastore (Airtable / GSheet) für Roadmap & Tracking→ QA Node (Acceptance-Check via LLM: „Sind Kriterien messbar?“)  
  
## **Prompt-Baustein (LLM) – Action-Synthesis**  
**System:**Du bist eine UX-Audit-Engine. Du wandelst Findings in klare, umsetzbare Maßnahmen um.Nutze Kategorien, Gewichte und Regeln aus dieser Spezifikation. Keine Meinungen ohne Evidenz.  
**User:**Konvertiere das Finding in max. 2 konkrete Empfehlungen.  
* Wähle passenden action_type.  
* Generiere title, steps (3–5), acceptance_criteria (3–5), metrics (2), owner_role, effort_tshirt.  
* Berechne priority_score gemäß Formel.  
* Output als JSON nach Schema „recommendation“.  
  
## **Minimal-Validator (Guardrails)**  
* Enthält Empfehlung Akzeptanzkriterien?  
* Sind Metriken vorhanden und realistisch?  
* Owner & Effort gesetzt?  
* Steps durchführbar (keine Floskeln)?  
* Evidence-Bezug gegeben?  
  
## **7 · YAML-Promptbasis für LLMs**  
```

audit_engine:
  name: "NFX Audit Engine 2.0"
  mission: "Ein reproduzierbares, KI-kompatibles Framework für UX-Audits, das Findings identifiziert, bewertet und in priorisierte, messbare Handlungsempfehlungen überführt."
  philosophy:
    - Nur bei Evidenz kommentieren
    - Keine Pflicht-Findings
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
  
## **8 · Ziel**  
Eine einheitliche, skalierbare Audit-Engine, die UX- und Content-Qualität objektiv bewertet, messbar macht und automatisch in handlungsreife Tasks übersetzt – inklusive Priorisierung, Messgrößen und Tool-Integration.  
