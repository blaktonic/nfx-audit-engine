# **UX-Audit-Framework-Optimiert.md**  
  
Dieses Dokument beschreibt ein vollständig operationalisierbares Framework, mit dem ein autonomer Agent einen UX‑Audit durchführen kann. Es basiert auf den heuristischen Kategorien (**Don’t make me think**, **Guide me** und **Create emotional impact**) und branchenspezifischen Best Practices. Die Kriterien und Prüfregeln wurden geschärft, um präzisere und technisch umsetzbare Empfehlungen zu gewährleisten.  
  
## **Audit‑Philosophie**  
  
* **Don’t make me think** – Inhalte sollen einfach und verständlich sein. Nutzer:innen dürfen im User Flow nicht ins Stocken geraten, weil Interaktionselemente ungewohnt sind oder Informationen fehlen. Verwende einfache Sprache, kurze Sätze und verzichte auf Jargon.  
* **Guide me** – Die Seite muss Zielhandlungen klar kommunizieren und Nutzer:innen durch Struktur, Hierarchie und Navigation leiten. Wichtige Inhalte sollen schnell auffindbar sein und der Weg zum Abschluss möglichst kurz. Primäre Call‑to‑Actions müssen hervorgehoben werden und sich deutlich von Sekundärelementen abgrenzen.  
* **Create emotional impact** – Markenidentität, Wiedererkennung und emotionales Design tragen zur Glaubwürdigkeit bei. Eine konsistente Bildsprache, passende Farben und glaubwürdige Informationen fördern Vertrauen. Interaktive Elemente, Multimedia‑Content und Storytelling erhöhen die Relevanz und machen die Nutzung unterhaltsamer.  
  
---  
  
## **Kategorien & Kriterien**  
  
Die Kriterien wurden erweitert und die Prüfregeln spezifischer gestaltet, um die automatisierte Evidenzgenerierung (DOM-Selektoren) zu verbessern und die UX-Begründung (UX-Laws) zu liefern.  
  
### **Kategorie 1 – Einfachheit (Simplicity)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln (Optimiert) | Visuelle Prüfregeln (Optimiert) | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| E1 | Konsistenz der Interaktionselemente | Interaktionselemente müssen so funktionieren wie auf anderen Seiten gewohnt (**Jakob’s Law**). | Prüfe, ob Buttons `<button>` oder `<a>` mit `role="button"` sind. **Zähle Inkonsistenzen** (`<div onclick>`). | Über Screenshots prüfen, ob Schaltflächen wie Buttons aussehen und ob ihre Gestalt (Farbe, Größe, Rahmen) **konsistent** ist. | 0–3 | 10 % |  
| E2 | Essentielle Inhalte & Funktionen vorhanden | Die Seite muss alle notwendigen Inhalte und Funktionen für die jeweilige Kategorie anbieten. | Durchsuche den DOM nach Elementen, die Schlüssel‑Funktionalitäten repräsentieren. Prüfe, ob `input`‑Felder mit `required` versehen sind. | Visuell prüfen, ob die erwarteten Bereiche (z. B. Produktinfo, Kontakt) sichtbar und leicht zugänglich sind. | 0–3 | 8 % |  
| E3 | Eindeutige Zielhandlungsanweisung | Erkläre klar, was Nutzer:innen tun müssen, um ihr Ziel zu erreichen. | Prüfe, ob CTA‑Buttons klare Texte besitzen (z. B. „Jetzt kaufen“) und ob sie mit `aria-label` versehen sind. | Über Screenshots analysieren, ob CTAs präsent sind, gut lesbar und ausreichend Abstand zu anderen Elementen haben. | 0–3 | 8 % |  
| E4 | Redundanzen und Füllwörter vermeiden | Lange Sätze, Füllwörter und doppelte Inhalte erschweren das Verständnis. | Durchsuche Texte (`innerText`) nach langen Sätzen ($> 20$ Wörter) und Füllwörtern („sehr“, „eigentlich“). | Über Screenshots prüfen, ob Textblöcke kurz sind und genügend Weißraum haben. | 0–3 | 5 % |  
| E5 | Gesprochene Sprache / Fragen | Der Text soll sich wie gesprochene Sprache lesen und durch Fragen aktivieren. | Analysiere Text auf Personalpronomen und Fragezeichen. Prüfe, ob **Passiv‑Formen** vermieden werden. | Visuell prüfen, ob Texte in **zweiter Person** formuliert sind und ob Fragen hervorgehoben werden. | 0–3 | 5 % |  
| **NEU E6** | **Sichtbarkeit des Systemstatus (Visibility of System Status)** | Prüfe auf Elemente zur **Statuskommunikation** (`aria-live`, Fortschrittsbalken). Misst die Time-to-Interaction (TII). | Ist der aktuelle Zustand (Laden, Validieren, Formularschritt) klar kommuniziert? Werden **Lade-Indikatoren** genutzt (Nielsen's Heuristik 1)? | 0–3 | **8 %** |  
  
### **Kategorie 2 – Verständlichkeit (Clarity)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln | Visuelle Prüfregeln | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| V1 | Einfache & verständliche Sprache | Vermeidet Fremdwörter, Jargon und erklärt nötige Begriffe. | Textanalyse: Zähle Vorkommen von Fachbegriffen und Abkürzungen. Prüfe, ob Tooltips (`<abbr title>`) oder Glossare vorhanden sind. | Über Screenshots prüfen, ob komplizierte Begriffe erklärt werden (z. B. Infoboxen). | 0–3 | 10 % |  
| V2 | Vollständigkeit der Informationen | Nutzer:innen sollen alle notwendigen Informationen finden. | Prüfe, ob Pflichtfelder im Formular vorhanden sind und ob Fehlermeldungen bei leeren Feldern erscheinen. Suche im DOM nach FAQ‑Bereichen oder ausführlichen Beschreibungen. | Visuelle Analyse: Gibt es Informationslücken (z. B. fehlende Preise, fehlende Beschreibungen)? | 0–3 | 8 % |  
| V3 | Klare Informationshierarchie | Überschriften und Strukturen führen Nutzer:innen. | Analysiere das Heading‑Level (`<h1>` bis `<h6>`) auf korrekte Reihenfolge und Semantik. Prüfe, ob Abschnitte logisch gruppiert sind. | Screenshots: Prüfe visuelle Abstände, Schriftgrößen, Layout‑Raster und Kontrast zwischen Überschriften und Text. | 0–3 | 10 % |  
| V4 | Konsistente Benennungen | Begriffe und Bezeichnungen müssen konsistent sein. | Suche nach Wiederverwendung identischer Komponenten (z. B. „Login“ vs. „Anmeldung“) und prüfe, ob gleiche Funktionen gleich benannt sind. | Visuell prüfen, ob Labels, Buttons und Menüpunkte konsistent beschriftet sind. | 0–3 | 5 % |  
| V5 | Aussagekräftige Headlines | Überschriften sollen Inhalte zusammenfassen. | Prüfe, ob `<h1>`–`<h3>` inhaltliche Schlüsselbegriffe enthalten (keine reinen Design‑Platzhalter). | Screenshots: Prüfe, ob Headlines optisch hervorstechen (Größe, Farbe) und inhaltlich klar sind. | 0–3 | 5 % |  
  
### **Kategorie 3 – Responsiveness (Responsivität)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln (Optimiert) | Visuelle Prüfregeln (Optimiert) | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| R1 | Angepasste Informationstiefe | Textlänge muss zum Gerät/Content passen. | Prüfe die Länge von Textabschnitten pro Viewport. Identifiziere Absätze, die $> 3$ Bildschirmseiten umfassen. | Screenshots: Analysiere Scrolltiefe; misst, wie weit man scrollen muss, um alle Informationen zu erfassen. | 0–3 | 8 % |  
| R2 | Nutzung nativer Gerätefunktionen | Für Standardfunktionen sollten native Elemente verwendet werden. | Prüfe, ob z. B. `<select>` für Dropdowns verwendet wird oder ob custom‑Components korrekt ARIA‑attribute implementieren. | Visuell prüfen, ob Interaktionselemente (z. B. Dateiupload, Kalender) dem Look & Feel des Betriebssystems entsprechen. | 0–3 | 5 % |  
| R3 | Lesbarkeit auf kleinen Geräten | Inhalte müssen auch auf kleinen Screens gut erkennbar sein. | Prüfe CSS‑Media‑Queries (`@media`), flexible Layouts und Schriftgrößen. **Target:** Schriftgröße mobil min. 16px. | Screenshots: Vergleiche mobile, tablet und Desktop‑Ansicht hinsichtlich Lesbarkeit (Zeilenlänge $< 70$ Zeichen, ausreichend Kontrast). | 0–3 | 10 % |  
| **R4** | Schnelle Ladezeit | Längere Ladezeiten reduzieren Konversionsraten. | Nutze Lighthouse/Performance-API. **Must-Have:** Lese **LCP-Wert für den primären `<H1>` und den Haupt-CTA**. **Target:** LCP $< 2.5\text{s}$. | Visuell: Prüfe, ob wichtige Inhalte innerhalb von 2 Sekunden erscheinen und ob kein Layout‑Shift auftritt. | 0–3 | **10 %** |  
  
### **Kategorie 4 – Navigation**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln (Optimiert) | Visuelle Prüfregeln (Optimiert) | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| N1 | Einfache Antrags‑/Checkout‑Strecke | Prozesse sollen schnell und einfach abschließbar sein. | Prüfe, ob Formulare logisch gegliedert sind. Suche nach **Schritt‑für‑Schritt‑Indikatoren** und **Feedback** bei Interaktionen. | Screenshots: Analyse der Formularlänge, Anzahl der Felder. | 0–3 | 10 % |  
| N2 | Auffindbarkeit wichtiger Inhalte | Wichtige Inhalte sollen schnell gefunden werden. | Prüfe interne Verlinkungen (`<nav>`, `<a>`) und BreadCrumbs. | Visuell: Prüfe, ob Suchfunktion, Menü und Filter klar erkennbar sind. | 0–3 | 8 % |  
| N3 | Klare Heading‑Struktur | Überschriften sollen Inhalte zusammenfassen. | Analysiere Heading‑Levels und ob keine Sprünge (z. B. `<h1>` $\to$ `###` ohne `<h2>`) vorkommen. | Screenshots: Prüfe, ob die visuelle Hierarchie den semantischen Ebenen entspricht. | 0–3 | 8 % |  
| **N4** | Navigation und Seitenstruktur | Der Weg durch die Seite muss klar und unkompliziert sein. | Prüfe, ob das `<nav>`‑Element vorhanden ist. **Zähle die Anzahl der Hauptnavigationspunkte (Target: $\le 7\pm 2$ Elemente (Miller's Law)).** | Visuelle Analyse: Prüfe, ob Navigationsleisten, Menü‑Buttons und Breadcrumbs klar positioniert sind. | 0–3 | **10 %** |  
| N5 | Visuelle Strukturierung | Überschriften, Unterüberschriften & Absätze sollen eine klare visuelle Struktur bieten. | Prüfe CSS‑Stylesheets auf definierte Heading‑Styles. | Screenshots: Bewerte Abstände, Alignment und Raster (z. B. 8‑px‑Grid). | 0–3 | 5 % |  
| **NEU N6** | **Fehlervermeidung & Hilfe** | Fehlermeldungen bei Nutzereingaben antizipieren. | Prüfe auf Client-Side-Validierung (`input:invalid`, `required`). Existieren **kontextbezogene Hilfen** in Formularen? | Werden **Fehlermeldungen** direkt am betroffenen Feld angezeigt und sind sie **konstruktiv** formuliert? **Visuelle Hervorhebung** von Pflichtfeldern (Nielsen's Heuristik 5 & 9). | 0–3 | **10 %** |  
  
### **Kategorie 5 – Zielfokus (Goal Focus)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln (Optimiert) | Visuelle Prüfregeln (Optimiert) | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| **Z1** | Primäres Ziel klar abgrenzbar | Das primäre Interaktionsziel muss sich sichtbar von anderen Elementen abheben. | Ermittele, ob es ein eindeutig definierter CTA gibt (z. B. `<button class="primary">`). **Target:** $\le 1$ primär hervorgehobener CTA. | Prüfe, ob der Haupt‑CTA farblich hervorgehoben und größer als andere Buttons ist. **Verifiziere die Einhaltung des Isolation Effect (Farbkontrast $\ge 3:1$).** | 0–3 | **10 %** |  
| Z2 | Call‑to‑Action‑Texte | Texte der CTA‑Elemente sollen als Handlungsaufforderung formuliert sein. | Prüfe, ob CTA‑Texte Verben enthalten (z. B. „Jetzt registrieren“) und ob sie per `aria-label` oder `title` ergänzt sind. | Screenshots: Prüfe, ob CTAs kurz sind ($< 4$ Wörter) und ob sie im Kontext aussagekräftig sind. | 0–3 | 5 % |  
| **Z3** | Platzierung wichtiger Inhalte | Wichtige Inhalte für die Zielsetzung müssen prominent am Seitenanfang platziert werden. | Prüfe DOM‑Struktur, ob Kernbotschaften und CTAs in den ersten **600-700px vertikal** erscheinen (Above-the-Fold-Ziel). | Screenshots: Analyse des „above‑the‑fold“‑Bereichs; sind USP‑Texte und CTAs dort zu sehen? | 0–3 | **8 %** |  
| Z4 | Nutzung von Biases & UX‑Laws | Psychologische Prinzipien wie Framing, Isolation, Trust etc. werden eingesetzt. | Prüfe, ob Preissignale (Ankerpreise), Social Proof (Testimonials), Trust‑Badges oder Scarcity‑Hinweise vorhanden sind. | Screenshots: Visuelle Analyse der Hervorhebungen und ob Ablenkungen minimiert sind. | 0–3 | 5 % |  
| Z5 | Performance/Core Web Vitals | Schnelle Seiten‑Performance unterstützt den Abschluss. | Nutze Lighthouse‑Berichte oder Performance‑API, um LCP, FID und CLS zu messen. | Visuell: Prüfe, ob keine spürbaren Layout‑Verschiebungen auftreten und ob Interaktionen sofort Feedback geben. | 0–3 | 7 % |  
  
### **Kategorie 6 – Wiedererkennung (Recognition)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln | Visuelle Prüfregeln | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| W1 | Klarer Absender/Branding | Am Seitenbeginn muss sofort erkennbar sein, wer der Absender ist. | Prüfe, ob Logo und Markenname im `<header>` eingebunden sind, ein `<title>`‑Tag und `meta‑description` vorhanden sind. | Screenshots: Prüfe, ob Markenlogo und Name prominent im Header erscheinen. | 0–3 | 8 % |  
| W2 | Konsistente Gestaltung | Einheitliche Bildwelt und Farben. | Prüfe CSS‑Variablen und wiederkehrende Klassen, ob Farbwerte konsistent verwendet werden. | Screenshots: Bewerte, ob Bilder, Icons und Farbpalette über die Seite hinweg zusammenpassen. | 0–3 | 8 % |  
| W3 | Markenidentität spürbar | Purpose & Werte sollen wahrnehmbar sein. | Prüfe, ob Mission‑Statements, Werte oder Markenbotschaften im DOM vorhanden sind. | Visuell: Analyse, ob Bildsprache, Tone‑of‑Voice und Farbstil zur Marke passen. | 0–3 | 6 % |  
| W4 | Glaubwürdigkeit & Versprechen | Vermeide falsche Versprechen oder Übertreibungen. | Prüfe Inhalte auf Marketing‑Buzzwords und vergleiche Aussagen mit Impressum/AGB. | Screenshots: Prüfe, ob Testimonials oder Zertifikate vorhanden sind und glaubwürdig wirken. | 0–3 | 5 % |  
| W5 | Abgrenzung zur Konkurrenz | Eigenständigkeit der Formulierungen & Bilder. | Prüfe Texte per Ähnlichkeitsvergleich gegen bekannte Konkurrenzseiten (optional). | Visuelle Analyse: Prüfe, ob Bildmaterial einzigartig ist (kein Stockmaterial, das bei Mitbewerbern auftaucht). | 0–3 | 5 % |  
| W6 | Brand‑Guide Konformität | Terminologie & Schreibweise gemäß Brand‑Guide. | Vergleiche Begriffe aus dem DOM mit Einträgen in einem optional bereitgestellten Brand‑Guide (falls verfügbar). | Screenshots: Prüfe orthografische Konsistenz und Schreibweisen. | 0–3 | 5 % |  
  
### **Kategorie 7 – Relevanz**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln | Visuelle Prüfregeln | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| Rlv1 | Essenzielle Inhalte & Features | Werden alle notwendigen Inhalte und Funktionen bereitgestellt? | Prüfe, ob Produkt‑/Service‑Features im DOM vorhanden sind und ob Kontaktmöglichkeiten angeboten werden. | Screenshots: Bewerte, ob Kerninformationen (USP, Preis, Vorteile) prominent dargestellt werden. | 0–3 | 10 % |  
| Rlv2 | Zielgruppen‑spezifischer Content | Inhalte müssen auf die Zielgruppe zugeschnitten sein. | Prüfe personalisierte Ansprache (z. B. segmentiertes Content, Anrede) und ob Personalisierungs‑Skripte (A/B‑Testing) integriert sind. | Visuell: Bewertet, ob Bildsprache, Sprache und Beispiele zur Zielgruppe passen. | 0–3 | 8 % |  
| Rlv3 | Präsentation der USPs | USPs des Angebots müssen präsent kommuniziert werden. | Suche nach Abschnitten wie „Vorteile“, „Warum wir?“ und prüfe, ob diese klar strukturiert sind. | Screenshots: Prüfe, ob USPs visuell hervorgehoben werden (Icons, Listen). | 0–3 | 8 % |  
| Rlv4 | Aktualität der Inhalte | Inhalte sollen aktuell sein (z. B. Datum, News). | Prüfe im DOM das Vorhandensein von Datumsangaben und Versionen. | Screenshots: Bewerte, ob Texte und Bilder modern wirken (z. B. aktuelle Jahreszahlen, moderne Geräte). | 0–3 | 4 % |  
| Rlv5 | Relevante Suchbegriffe | SEO‑Bezug: sind Keywords und Meta‑Informationen korrekt? | Prüfe `<title>`, `<meta name="description">` und `<h1>` auf relevante Keywords. | Visuell: Prüfe, ob Keywords im sichtbaren Text vorkommen. | 0–3 | 5 % |  
| Rlv6 | Nutzerprobleme antizipieren | Werden Fragen und Einwände proaktiv beantwortet? | Prüfe, ob FAQs, Help‑Sections oder Live‑Chat‑Integrationen vorhanden sind. | Screenshots: Prüfe, ob Problembereiche (z. B. Lieferzeiten, Kosten) erklärt werden. | 0–3 | 5 % |  
  
### **Kategorie 8 – Unterhaltungswert (Engagement)**  
  
| ID | Kriterium | Relevanz | Codebasierte Prüfregeln | Visuelle Prüfregeln | Skala | Gewicht |  
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |  
| U1 | Emotionale Gestaltung | Design & Bildwelt sollen emotional wirken. | Prüfe DOM nach emotionalen Worten und ob `alt`‑Attribute beschreibend sind. | Screenshots: Bewerte, ob Farben und Bilder eine angenehme Stimmung erzeugen. | 0–3 | 7 % |  
| U2 | Medienmix | Setzt die Seite interaktive Elemente, Videos, Bilder und Grafiken ein, um Inhalte aufzuladen? | Prüfe, ob `<video>`, `<audio>`, `<svg>` oder animierte Elemente existieren; validiere, ob Medien mit `controls` und `alt`‑Text versehen sind. | Screenshots: Analysiere, ob verschiedene Medienformate sinnvoll eingesetzt werden. | 0–3 | 8 % |  
| U3 | Aktive Sprache | Verwende direkte Ansprachen und vermeide Passivformen. | Textanalyse: Zähle Passivkonstruktionen (z. B. „wird gemacht“) und nominelle Formulierungen. | Visuell: Prüfe, ob CTA‑Texte und Headlines aktiv formuliert sind. | 0–3 | 5 % |  
| U4 | Emotionale Ansprache der Nutzer | Texte sollen Gefühle der Nutzer:innen ansprechen. | Prüfe, ob Worte wie „Freude“, „Sicherheit“, „Spaß“ oder ähnliche genutzt werden. | Screenshots: Prüfe, ob Testimonials, Storytelling‑Elemente oder Personas vorhanden sind. | 0–3 | 5 % |  
| U5 | Gamification & Engagement | Werden spielerische Elemente oder Feedback‑Mechanismen genutzt, um Engagement zu steigern? | Prüfe, ob Punktesysteme, Fortschrittsbalken oder Mikrointeraktionen implementiert sind. | Visuell: Suche nach Animationen, Mikrointeraktionen oder Gamification‑Elementen. | 0–3 | 5 % |  
  
---  
  
## **Scoring‑Modell**  
  
1.  **Bewertung pro Kriterium (0–3)**: Jedes Kriterium wird anhand der beschriebenen Regelwerke bewertet. **0** bedeutet, dass das Kriterium nicht erfüllt ist, **3** steht für eine vorbildliche Umsetzung.  
2.  **Subscores**: Für jedes Kriterium wird ein **Code‑Subscore** und ein **Visual‑Subscore** (jeweils 0–3) vergeben. Der Gesamtscore des Kriteriums ist der Durchschnitt der beiden.  
3.  **Kategoriewert**: Der gewichtete Mittelwert der Kriterien innerhalb einer Kategorie ergibt den Kategorienscore.  
4.  **Gesamtscore**: Der Gesamtwert der Seite wird aus den Kategorienscores gebildet und auf eine Skala von **0–100** normalisiert.  
5.  **Priorisierung**: Probleme werden nach **Impact $\times$ Aufwand** sortiert.  
    $$\text{Impact} = \text{Kriteriengewicht} \times (3.0 - \text{Durchschnittsscore})$$  
  
---  
  
## **Ablaufplan für den Agenten (Optimiert)**  
  
1.  **Vorbereitung und Informationsbeschaffung**  
    * 1.1. Lade das Framework (diese Datei).  
    * 1.2. Hole vom Auftraggeber die Zielgruppe, KPIs, primären und sekundären Ziele sowie Markenwerte.  
    * 1.3. Lege gegebenenfalls einen Brand‑Guide als Vergleichsquelle fest.  
2.  **Seite analysieren**  
    * 2.1. **Seite aufrufen** – öffne die Ziel‑URL in einem Browser.  
    * 2.2. **Viewports anpassen** – rendere die Seite in drei Ansichten: Mobile (360 × 640 px), Tablet (768 × 1024 px) und Desktop (1440 × 900 px).  
    * 2.3. **Screenshots erstellen** – erstelle für jede Ansicht einen Screenshot des sichtbaren Bereichs (above the fold) und einen vollständigen Screenshot durch Scrollen. Speichere Pfade für spätere Evidenz.  
    * 2.4. **DOM‑Extraktion** – extrahiere den DOM als HTML, einschließlich CSS‑ und JavaScript‑Dateien.  
    * 2.5. **Kriterien prüfen** – gehe Kategorie für Kategorie und Kriterium für Kriterium durch. Nutze DOM‑Abfragen, Textanalysen und Core‑Web‑Vitals‑Messungen für die Code‑Checks; verwende die Screenshots, um visuelle Aspekte zu beurteilen.  
    * 2.6. **Bewertung vergeben** – vergib Code‑ und Visual‑Scores (0–3) für jedes Kriterium. Berechne aus Gewichtungen den Kategorienscore und den Gesamtscore.  
    * 2.7. **Probleme dokumentieren** – für jede Abweichung vom Ideal **dokumentiere DOM‑Selektoren** (`querySelector`‑Pfade) und **Screenshots** (Ausschnitt mit Koordinaten).  
    * 2.8. **Impact & Aufwand abschätzen** – ordne jedem Problem einen Impact (low/medium/high) und einen geschätzten Implementierungsaufwand zu.  
3.  **Quick Wins und Empfehlungen ableiten (Neu)**  
    * 3.1. Identifiziere Punkte mit hohem Impact und niedrigem Aufwand als Quick Wins.  
    * 3.2. **Priorisierungsgrundlage:** Berechne den **Impact** anhand der gewichteten Score-Differenz zum Ideal (3.0).  
    * 3.3. **Empfehlungsstruktur (Must-Have):** Formuliere für jedes Problem mit der Priorität **Medium** oder **High** eine präzise Handlungsempfehlung in diesem **3-teiligen Format** (speichere es in der `recommendation` im JSON):  
        * **Handlung (Was):** Kurze, direkte Anweisung (z.B. "CTA-Farbe ändern").  
        * **Begründung (Warum):** Nennung des verletzten **UX-Prinzips** (z.B. Isolation Effect, Miller's Law, Heuristik 9).  
        * **Technische Anweisung (Wie):** Konkreter **CSS-Selektor** oder DOM-Pfad mit direktem Änderungsvorschlag (z.B. `.hero-cta { background-color: var(--brand-color-primary); }`).  
    * 3.4. Gruppiere Empfehlungen nach Kategorien und priorisiere sie.  
4.  **Audit‑Bericht erzeugen**  
    * 4.1. Verwende das unten definierte Template.  
    * 4.2. Füge eine Executive Summary hinzu, die die wichtigsten Erkenntnisse, den Gesamtscore und die Prioritäten zusammenfasst.  
    * 4.3. Liste alle Probleme mit Evidenz und konkreten Empfehlungen auf.  
    * 4.4. Füge einen Anhang mit Screenshots und Metriken an.  
    * 4.5. Benenne den Bericht nach dem Muster ux-audit-<hostname>-<YYYYMMDD>.md.  
  
---  
  
## **Audit‑Output‑Template**  
  
```markdown  
# UX‑Audit für <Hostname> (<Datum>)  
  
## Executive Summary  
  
Kurze Zusammenfassung der wichtigsten Erkenntnisse, Scores und Quick Wins.  
  
* Gesamtscore: <Gesamtscore>/100 (Code‑Score <Code‑Score>, Visual‑Score <Visual‑Score>).  
* Stärken: <...>.  
* Schwächen: <...>.  
* Empfohlene Quick Wins: <...>.  
  
## Scoreübersicht  
  
| Kategorie | Score (0–100) | Beschreibung |  
|---|---|---|  
| Einfachheit | <…> | Kurze Beschreibung der Stärken/Schwächen |  
| Verständlichkeit | <…> | … |  
| Responsiveness | <…> | … |  
| Navigation | <…> | … |  
| Zielfokus | <…> | … |  
| Wiedererkennung | <…> | … |  
| Relevanz | <…> | … |  
| Unterhaltungswert | <…> | … |  
| **Gesamt** | **<…>** | … |  
  
## Detailanalyse nach Kategorie  
  
### <Kategorie>  
  
| Kriterium | Code‑Score | Visual‑Score | Gewicht | Problem (falls vorhanden) | **Empfehlung (3-teilig)** |  
|---|---|---|---|---|---|  
| <Kriterium ID – Kurzbeschreibung> | <0–3> | <0–3> | <Gewicht> | <Beschreibung des Problems mit Verweis auf Evidenz> | <Handlung, Begründung (UX-Prinzip), Technische Anweisung> |  
  
<Optionaler Screenshot oder Codeausschnitt>  
  
[… weitere Kategorien …]  
  
## Quick Wins  
  
Stichpunktartige Liste von Maßnahmen mit hohem Impact und geringem Aufwand.  
  
## Anhang



##**Audit Output json Struktur**
{
  "$schema": "[http://json-schema.org/draft-07/schema#](http://json-schema.org/draft-07/schema#)",
  "title": "UXAuditResult",
  "type": "object",
  "properties": {
    "url": { "type": "string", "format": "uri" },
    "date": { "type": "string", "format": "date" },
    "overallScore": { "type": "number", "minimum": 0, "maximum": 100 },
    "categories": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": { "type": "string" },
          "name": { "type": "string" },
          "score": { "type": "number", "minimum": 0, "maximum": 100 },
          "criteria": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "id": { "type": "string" },
                "description": { "type": "string" },
                "codeScore": { "type": "number", "minimum": 0, "maximum": 3 },
                "visualScore": { "type": "number", "minimum": 0, "maximum": 3 },
                "weight": { "type": "number", "minimum": 0, "maximum": 1 },
                "evidence": {
                  "type": "object",
                  "properties": {
                    "domPaths": { "type": "array", "items": { "type": "string" } },
                    "screenshotPaths": { "type": "array", "items": { "type": "string" } },
                    "notes": { "type": "string" }
                  },
                  "required": ["domPaths", "screenshotPaths"]
                },
                "recommendation": { "type": "string" },
                "impact": { "type": "string", "enum": ["low", "medium", "high"] },
                "effort": { "type": "string", "enum": ["low", "medium", "high"] }
              },
              "required": ["id", "codeScore", "visualScore", "weight"]
            }
          }
        },
        "required": ["id", "name", "score", "criteria"]
      }
    },
    "quickWins": { "type": "array", "items": { "type": "string" } },
    "issues": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "criterionId": { "type": "string" },
          "description": { "type": "string" },
          "evidence": { "$ref": "#/definitions/evidence" },
          "recommendation": { "type": "string" },
          "impact": { "type": "string", "enum": ["low", "medium", "high"] },
          "effort": { "type": "string", "enum": ["low", "medium", "high"] }
        },
        "required": ["criterionId", "description", "recommendation"]
      }
    }
  },
  "definitions": {
    "evidence": {
      "type": "object",
      "properties": {
        "domPaths": { "type": "array", "items": { "type": "string" } },
        "screenshotPaths": { "type": "array", "items": { "type": "string" } },
        "notes": { "type": "string" }
      },
      "required": ["domPaths", "screenshotPaths"]
    }
  },
  "required": ["url", "date", "overallScore", "categories"]
}
  
* Screenshots (mobile, tablet, desktop; above‑the‑fold und fullpage)  
* Core‑Web‑Vital‑Metriken  
* DOM‑Ausschnitte oder HTML‑Snippets, die Probleme demonstrieren  
* Kompletter JSON‑Export gemäß Schema  
