# NFX AUDIT ENGINE 1.0 — Design × Live Code Framework  
*(Unified Markdown – usable as Cursor Audit Instruction File)*  

## ⚙️ 0. Meta
**Version:** 1.0  
**Mode:** design-aware + live-aware  
**Input Required:**  
- Figma Frame (via HTTP-to-Design plugin)  
- Live URL of same page  
**Output:** Audit Summary + JSON Object + Action Recommendations  

---

## 1️⃣ Audit-Philosophie
Ziel: Von Beobachtung → Bedeutung → Handlung.  
Das Framework verbindet Figma-Layer (strukturelle Absicht) mit Live-DOM (reale Umsetzung).  

**Grundprinzipien:**  
1. Nur belegbare Beobachtungen (keine Mutmaßungen)  
2. Live-Code überstimmt Figma, falls Widerspruch  
3. Erkenntnis vor Score  
4. Kategorie-Scores beibehalten (Kompatibilität zu 0.9)  
5. Story-Layer ergänzt: *Was verrät das über Marke und Nutzererlebnis?*  

---

## 2️⃣ Kategorien & Kriterien (kompatibel zu 0.9)
| Kategorie | Kernfrage | Typische Kriterien |
|------------|------------|--------------------|
| **Verständlichkeit** | Wird der Inhalt klar vermittelt? | Textstruktur, Lesbarkeit, Hierarchie, Verständliche Sprache |
| **Einfachheit** | Ist die Nutzung intuitiv und reibungslos? | Reduktion, Konsistenz, Informationslast |
| **Zielfokus** | Wird die gewünschte Handlung klar gefördert? | CTA-Sichtbarkeit, Platzierung, Klarheit |
| **Navigation** | Finden sich Nutzer:innen zurecht? | IA, Breadcrumb, Footer, Orientierung |
| **Responsiveness** | Funktioniert das Layout auf allen Geräten? | Breakpoints, mobile Lesbarkeit, Overflow |
| **Wiedererkennung** | Bleibt das Design markenkonsistent? | Iconik, Stil, Farb- und Typo-Konstanz |
| **Relevanz** | Fühlt sich der Content nützlich und passend an? | Nutzerwert, Aktualität, thematische Passung |
| **Unterhaltungswert** | Wirkt das Erlebnis lebendig, emotional, aktivierend? | Motion, Tonalität, Bildwelt |

---

## 3️⃣ Audit-Workflow
1. **Input-Stage:**  
   - Figma Frame + Page URL werden geladen  
   - Viewports: 390 / 768 / 1024 / 1366 / 1440 px  

2. **Design-Analyse (Figma):**  
   - Parse Node-Tree (`component_name`, `y`, `text_content`)  
   - Detect key zones (Hero, Nav, Cards, Footer)  
   - Heuristik-Tagging nach Kategorie  

3. **Live-Analyse (DOM/CSS/JS):**  
   - Prüfe Sichtbarkeit, Kontrast, Performance (Web Vitals), A11y, Responsiveness  
   - Vergleiche Layer mit realem Rendering  

4. **Fusion:**  
   - Merge findings mit `evidence_figma` + `evidence_dom`  
   - Berechne Impact: (User Impact + Strategic Impact)/Effort × Confidence  

5. **Output:**  
   - Markdown Summary (dieses File)  
   - JSON Block im Code-Fence  

---

## 4️⃣ Live-Checks (Minimal-Set)
**Visibility:** CTA above-the-fold (Intersection ≥ 0.2)  
**Performance:** LCP ≤ 2.5 s | CLS ≤ 0.1 | INP ≤ 200 ms  
**Responsiveness:** No horizontal scroll | Text ≤ 85 chars per line  
**A11y:** Kontrast AA | Eindeutige H-Hierarchie | Keyboard-Fokus  
**Content:** Ein H1 | Meta Description | Korrekte Language Attr  
**Integrity:** Keine 404 Assets | Async/Defer JS  

---

## 5️⃣ Scoring-Matrix
| Dimension | Bedeutung | Skala |
|------------|------------|-------|
| **User Impact** | Effekt auf Vertrauen, Orientierung, Conversion | 1–5 |
| **Strategic Impact** | Beitrag zur Markenwirkung & Systemreife | 1–5 |
| **Effort** | Aufwand zur Behebung | 1–5 |
| **Confidence** | Sicherheit des Nachweises | 0.5–1.0 |

→ **Priority = (User Impact + Strategic Impact) / Effort × Confidence**

---

## 6️⃣ Output-Struktur (JSON)
```json
{
  "meta": {
    "engine_version": "1.0",
    "source": "cursor_figma_live",
    "audit_date": "{{date}}",
    "page_url": "{{url}}",
    "figma_frame": "{{frame}}"
  },
  "scores": {
    "Verständlichkeit": 0,
    "Einfachheit": 0,
    "Zielfokus": 0,
    "Navigation": 0,
    "Responsiveness": 0,
    "Wiedererkennung": 0,
    "Relevanz": 0,
    "Unterhaltungswert": 0
  },
  "findings": [
    {
      "id": "FND-001",
      "category": "Zielfokus",
      "title": "CTA nicht above-the-fold sichtbar",
      "evidence_figma": {"node_id": "2:2520","y":352,"text":"Strom sichern!"},
      "evidence_dom": {"selector": "main .hero button.primary","visible_in_vp": false,"intersection_ratio": 0.0},
      "impact_user": 5,
      "impact_strategic": 4,
      "effort": 2,
      "confidence": 0.9,
      "comment": "Der primäre CTA liegt unterhalb des sichtbaren Bereichs und schwächt die Aktivierung.",
      "recommendation": "CTA nach oben verschieben, Benefit emotionaler rahmen.",
      "priority": 4.5
    }
  ],
  "system_insights": [
    "Design priorisiert Ruhe über Momentum – Markenenergie bleibt ungenutzt."
  ]
}

7️⃣ Audit-Report Template (Ergebnistext)
Core Impression

→ Kurzbeschreibung in 3 Sätzen: Ton, Vertrauen, Momentum

Stärken

– {{3 Stärken mit Kategorie}}

Hauptherausforderungen

– {{3 Findings mit höchstem Impact}}

Handlungsempfehlungen

{{REC-001 aus Finding}}

{{REC-002 …}}

{{…}}

Impact Grid

User Impact × Strategic Impact – nach Priorität sortiert

Nächste Schritte

Top 2 High-Impact Findings testen (A/B)

Mobile-First Copy strukturieren

Breakpoints definieren und testen

8️⃣ Acceptance-Kriterien (automatisch prüfbar)

CTA bei 1366×768 und 390×844 sichtbar

Trust-Signal ≤ 120 px neben CTA

LCP ≤ 2.5 s | CLS ≤ 0.1 | INP ≤ 200 ms

Kontrast AA erfüllt | H1 eindeutig

Kein Overflow auf Mobile

9️⃣ Executive-Output (Beispiel)

Core Impression:
Solide, vertrauensbetont – aber zu zurückhaltend in der Handlungsaufforderung.

Top Findings:

Hero-CTA nicht sichtbar → Energieverlust

Lange Absätze → schwere Scanbarkeit

Trust-Signale erst weit unten → Conversion-Verlust

Empfohlene Aktionen:

CTA above-the-fold + Trust Signal kombinieren

Texte strukturieren (Bullets / Subheads)

Responsive Breakpoints dokumentieren

🔚 End of Framework

Hinweis: Dieses Dokument ist eine funktionsfähige Audit-Anleitung für Cursor.
Beim Run werden Figma-Layer und Live-DOM analysiert, Kategorien wie oben bewertet und die Resultate im JSON-Block gefüllt.
