# WMC_Brom

## KM3-04 · CSS-Selektoren

Florian Brom · 3caif

### 1. Das Labor erweitern

Die [Speisekarte](demo.html#speisekarte) enthält sechs Gerichte und die Zubereitung für das Apfelkompott.

| Ziel | Selektor in demo.css |
| --- | --- |
| Kopfzeile | `#speisekarte thead` |
| Jede zweite Datenzeile | `#speisekarte tbody tr:nth-child(even)` |
| Letzter Eintrag | `#speisekarte tbody tr:last-child` |
| Zweiter Schritt | `#speisekarte li:nth-child(2)` |
| Vorletzter Schritt | `#speisekarte li:nth-last-child(2)` |

Die vorhandene Regel `.kasten:has(img)` gibt dem Apfelkasten einen violetten linken Rand. Mit `:has(img)` prüft der Browser, ob der Kasten ein Bild enthält. Bei `.kasten:is(img)` müsste der Kasten selbst ein Bild sein.

### 2. Selbsttest

- [x] `p.hinweis` trifft Absätze mit der Klasse `hinweis`.
- [x] `h2 ~ p` trifft alle nachfolgenden Absätze mit demselben Elternelement wie die Überschrift.
- [ ] `:nth-child(2)` und `:nth-of-type(2)` treffen immer dasselbe Element.
- [x] Bei gleicher Spezifität und sonst gleichen Kaskadenbedingungen gewinnt die später notierte Regel.

Stehen in einem Container eine Überschrift und danach zwei Absätze, trifft `p:nth-child(2)` den ersten Absatz, weil die Überschrift mitzählt. `p:nth-of-type(2)` zählt nur die Absätze und trifft den zweiten.

| Ziel | Selektor |
| --- | --- |
| Links mit Zielendung .pdf | `a[href$=".pdf"]` |
| Absätze ohne Klasse hinweis | `p:not(.hinweis)` |
| Erstes li jeder ul | `ul > li:first-of-type` |
| Elemente mit einem Bild als Nachfahren | `:has(img)` |
| Gesetztes Häkchen direkt vor einem label | `input[type="checkbox"]:checked:has(+ label)` |

Für die Beschriftung des gesetzten Häkchens verwendet die Kursdemo `input:checked + label`.

`p:nth-child(1)` greift nur, wenn das erste Kind ein Absatz ist. Diese Regel trifft den ersten Absatz auch nach einer Überschrift:

```css
p:first-of-type {
    font-weight: bold;
}
```

### 3. Prüfungsaufgabe

Die Regeln stehen in [loesung.css](loesung.css). In der Preistabelle zählt die Kopfzeile mit, deshalb steht das Hauptgericht an dritter Stelle.

Die Sektion trägt bereits das Attribut `data-topic`, das ihr Thema beschreibt. Mit `[data-topic^="css-adv"]` erreiche ich alle Sektionen mit diesem Themenpräfix, ohne eine Klasse ins HTML einzufügen.
