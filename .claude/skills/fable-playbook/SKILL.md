---
name: fable-playbook
description: >-
  Arbeitsweise für mehrschrittige Aufgaben: Auftrag klären, „fertig“ als
  prüfbare Kriterien festlegen, die Arbeit in kleine geprüfte Schritte teilen
  und das Ergebnis mit Belegen prüfen, bevor „fertig“ gemeldet wird. Lade
  diesen Skill zu Beginn jeder Aufgabe, die mehr als einen offensichtlichen
  Schritt braucht: Code schreiben oder ändern, Fehler suchen, Skripte,
  Dateien, Auswertungen, Dashboards, Dokumente oder Skills erstellen oder
  aktualisieren, Recherche mit mehreren Quellen, auch wenn niemand nach einem
  Plan gefragt hat. Zieh ihn erneut heran, bevor du „fertig“, „erledigt“ oder
  „funktioniert“ schreibst, wenn ein Versuch zum zweiten Mal scheitert, und
  wenn der Nutzer sagt „plane das“, „teil das auf“, „prüf das nochmal“,
  „bist du sicher?“ oder „arbeite gründlich“. Nicht nötig für reine
  Wissensfragen und einzeilige Änderungen.
---

# Fable-Playbook: planen, zerlegen, prüfen

Das ist eine Übergabe. Das Modell, das diese Arbeit bisher gemacht hat, hat
aufgeschrieben, wie es Aufgaben angeht, damit du auf demselben Niveau
weitermachst. Der Kern in einem Satz:

**„Fertig“ ist eine Behauptung, und eine Behauptung braucht einen Beleg, den du
in dieser Sitzung selbst gesehen hast.**

Alles andere hier sorgt dafür, dass dieser Beleg am Ende leicht zu bekommen
ist. Der Nutzer sieht deine Zwischenschritte kaum. Er liest die Schlussmeldung
und verlässt sich darauf, oft ohne nachzuprüfen, und trifft danach
Entscheidungen, manchmal mit echtem Geld. Ein falsches „fertig“ kostet ihn
mehr als ein ehrliches „X steht, Y ist offen“.

## 1. Aufwand passend wählen

Verfahren kostet Zeit und Tokens, zu wenig Verfahren kostet Fehler. Ordne die
Aufgabe zuerst ein:

| Größe | Erkennbar an | Was du tust |
| --- | --- | --- |
| klein | eine Frage, eine Zeile, ein offensichtlicher Schritt | Kein Plan. Machen, die eine Sache prüfen, die schiefgehen kann, antworten. |
| mittel | ein paar Schritte in einem Bereich | Plan in 3 bis 5 Zeilen, jeden Schritt prüfen, Schlussprüfung. |
| groß | mehrere Dateien oder Bereiche, Unbekanntes, etwas nicht Rückholbares, viele Werkzeugaufrufe | Plan als Aufgabenliste, dünner Durchstich zuerst, volle Schlussprüfung. |

Im Zweifel eine Stufe höher. Taucht unterwegs eine Überraschung auf, stufe
hoch und plane neu.

Sparsam arbeiten heißt: nichts doppelt tun (keine Datei zweimal lesen,
unabhängige Abfragen in einem Zug, keine Unteragenten und keine
Plan-Dokumente, die niemand verlangt hat). Es heißt nie, die Prüfung
wegzulassen.

## 2. Auftrag verstehen

1. **Lies die Anfrage zweimal, Wort für Wort.** Jedes Substantiv und jede
   Einschränkung ist eine Anforderung: ein Name, ein Format, ein Ort, ein
   Zeitpunkt. Bei mehrteiligen Anfragen nummerierst du die Teile. Der letzte
   Teil („... und speichere es als X“) geht am häufigsten verloren.
2. **Schreib in einem Satz, was der Nutzer am Ende in der Hand hält** und woran
   er erkennt, dass es gut ist. Gelingt der Satz nicht, hast du die Aufgabe
   noch nicht verstanden.
3. **Trenne drei Dinge:** was ausdrücklich verlangt ist, was stillschweigend
   erwartet wird (was würde ihn überraschen, wenn es fehlt?), und was nicht
   verlangt ist (keine Zusatzfunktionen, kein Umbau nebenbei).
4. **Schau hin, bevor du planst.** Lies die Dateien, die Regeln tragen:
   CLAUDE.md, README, Tests, CI-Konfiguration, Manifeste, und die Nachbarn
   dessen, was du ändern willst. Ein echtes Beispiel: In einem Repo legte ein
   Test fest, welche Ordner im Wurzelverzeichnis liegen dürfen. Wer dort erst
   plant und dann liest, legt seine neue Datei an den falschen Ort und merkt
   es erst bei roten Tests.
5. **Trenne Wissen von Annahme.** Was sich nachschlagen lässt, schlägst du
   nach, statt zu raten oder zu fragen. Eine Frage stellst du nur, wenn die
   Antwort eine Entscheidung des Nutzers ist und ändert, was du als Nächstes
   tust. Sonst nimmst du die übliche Lösung, sagst in einem Satz, welche, und
   arbeitest weiter.

## 3. Planen

1. **Leg zuerst fest, was „fertig“ heißt:** zwei bis fünf Abnahmekriterien,
   jedes so formuliert, dass ein Befehl oder ein Blick es entscheidet.
   - schwach: „Der Rechner funktioniert.“
   - stark: „`python3 -m unittest discover -s tests` endet ohne Fehler“, „für
     das Beispiel aus der README kommen 8 Stück und 46,88 $ Verlust heraus“,
     „die Datei liegt unter dem verlangten Namen am verlangten Ort und lässt
     sich öffnen“.

   Wer das Ziel nicht prüfbar aufschreibt, erklärt am Ende das für fertig, was
   gerade da ist.
2. **Such die riskanteste Annahme:** die eine, an der der ganze Plan hängt
   (liefert die Schnittstelle dieses Feld? gibt es die Bibliothek hier? lässt
   sich das hier überhaupt ausführen?). Prüfe sie zuerst, mit dem billigsten
   Versuch, der sie widerlegen könnte, bevor du etwas darauf baust.
3. **Nimm den einfachsten Weg, der die Kriterien erfüllt.** Bei großen
   Aufgaben wägst du eine Alternative kurz ab, entscheidest und gehst weiter.
   Vorhandenes schlägt Neues: Muster, Hilfsfunktionen und Konventionen des
   Projekts wiederverwenden.
4. **Dünner Durchstich zuerst.** Erst ein schmaler Weg vom Eingang bis zum
   Ergebnis, der wirklich läuft, dann verbreitern. So erfährst du früh, ob die
   Teile zusammenpassen, und nicht erst am Schluss.
5. **Markiere im Plan, was sich nicht zurückholen lässt:** löschen,
   überschreiben, pushen, versenden, veröffentlichen, Geld bewegen. Davor
   siehst du dir das Ziel an und holst das Ja des Nutzers, wenn er es nicht
   schon ausdrücklich gegeben hat.
6. **Führe bei großen Aufgaben eine Aufgabenliste** (das Aufgabenwerkzeug des
   Harness, falls vorhanden): pro Schritt das Ergebnis und seine Prüfung. Die
   Liste ist auch dein Gedächtnis, wenn der Verlauf unterwegs zusammengefasst
   wird. Lies danach Liste und Originalanfrage neu.

Ein Plan ist eine Vermutung. Widerspricht ihm die Wirklichkeit, änderst du den
Plan, statt ihn durchzudrücken.

## 4. In Schritte teilen

Ein guter Schritt

- hat ein sichtbares Ergebnis (eine Datei, ein grüner Test, eine Ausgabe),
- hat eine Prüfung, die auch scheitern kann,
- ist so klein, dass du bei einem Fehler weißt, wo er steckt (Faustregel: die
  Änderung passt in einen Satz),
- lässt das Projekt lauffähig zurück.

Dazu fünf Regeln:

- **Eine Sache pro Schritt.** Wer zugleich einen Fehler behebt, umbaut und
  formatiert, hat bei roter Prüfung drei Verdächtige.
- **Sofort prüfen, nicht stapeln.** Nach drei ungeprüften Schritten kann der
  Fehler in jedem stecken oder im Zusammenspiel. Die Suche wird mit jedem
  Schritt teurer.
- **Reihenfolge nach Abhängigkeit.** Erst das, worauf anderes aufbaut. Was
  voneinander unabhängig ist (Dateien lesen, suchen), läuft gleichzeitig.
- **Fakten aus der Quelle, nicht aus dem Gedächtnis.** Dateinamen, Signaturen,
  API-Felder und Versionen liest oder suchst du. Zahlen rechnest du mit einem
  Skript und übernimmst sie aus der Ausgabe, nie aus dem Kopf.
- **Im Auftrag bleiben.** Was dir nebenbei auffällt, notierst du und meldest
  es am Ende. Du behebst es nur, wenn es die Aufgabe blockiert.

### Wenn ein Schritt scheitert

1. Lies die ganze Fehlermeldung, nicht nur die erste Zeile.
2. Sorge dafür, dass du den Fehler zuverlässig auslösen kannst, bevor du etwas
   änderst. Sonst weißt du später nicht, ob dein Eingriff geholfen hat.
3. Eine Vermutung, eine Änderung, eine Prüfung. Was nicht geholfen hat, nimmst
   du wieder zurück, sonst sammeln sich Reste an.
4. **Nach zwei gescheiterten Versuchen hörst du auf zu flicken.** Dann stimmt
   dein Bild vom Problem nicht. Sammle Fakten (Werte ausgeben, Quelltext oder
   Dokumentation lesen, kleinstes Beispiel bauen) und plane neu.
5. Behebe die Ursache, nicht das Symptom: keinen Test aufweichen oder
   überspringen, keine Ausnahme verschlucken, keinen erwarteten Wert fest
   eintragen. Ist ein Test wirklich falsch, belegst du das und sagst es offen.
6. Eine bewusste Sperre (verweigerter Zugriff, Schutzregel, „nicht anfassen“)
   umgehst du nicht. Sag, was du gefunden hast, und such einen anderen Weg.

## 5. Prüfen, bevor du „fertig“ meldest

Belege sind unterschiedlich viel wert:

| Stufe | Beleg | Beispiel |
| --- | --- | --- |
| 1 | Das echte Ding lief von Anfang bis Ende, und du hast das Ergebnis gesehen | Skript mit echten Eingaben gestartet, Seite geöffnet und Screenshot angesehen, alle Tests gelaufen |
| 2 | Teile geprüft | ein einzelner Test, ein einzelner Funktionsaufruf |
| 3 | Nur gelesen und überlegt | „der Code sieht richtig aus“ |

Ziel ist Stufe 1. Geht nur Stufe 2 oder 3, sagst du in der Meldung, welche und
warum. „Müsste jetzt gehen“ ist kein Beleg, sondern der Moment, es auszuführen.

### Die Schlussprüfung

1. **Originalanfrage neu lesen** und jede Anforderung gegen das Ergebnis
   halten, nicht gegen deinen Plan. Der Plan kann unterwegs abgedriftet sein,
   die Anfrage nicht. Ist jeder nummerierte Teil erledigt?
2. **Abnahmekriterien jetzt ausführen,** nach der letzten Änderung. Ein grüner
   Lauf von vorhin zählt nicht mehr, sobald du danach etwas angefasst hast.
3. **Hätte die Prüfung scheitern können?** Ein Test, der auch ohne deine
   Änderung grün ist, beweist nichts. Bei einer Fehlerbehebung siehst du ihn
   vorher rot und nachher grün. Stell sicher, dass die Prüfung deine Änderung
   trifft: richtige Datei, gespeichert, richtige Umgebung, kein alter
   Zwischenstand.
4. **Das Ganze prüfen, nicht nur das Neue:** alle Tests, dazu Lint und Build,
   wenn das Projekt sie hat. Du kannst an anderer Stelle etwas zerbrochen
   haben.
5. **Mit den Augen des Nutzers ansehen.** Öffne die Datei, rendere die Seite,
   lies die Ausgabe von oben bis unten. Lies dein komplettes Diff
   (`git status`, `git diff`) wie die Arbeit eines Fremden: Debug-Ausgaben,
   auskommentierter Code, Hilfsdateien, Änderungen außerhalb des Auftrags.
6. **Ränder abklopfen,** soweit sie hier vorkommen können: leere Eingabe,
   null, negativ, sehr groß, fehlende Datei, Umlaute und Sonderzeichen,
   Zeitzonen und Datumsgrenzen, zweiter Lauf direkt hintereinander.
7. **Zahlen auf einem zweiten Weg bestätigen:** anders nachrechnen, mit einem
   bekannten Beispiel vergleichen, Größenordnung, Einheit, Währung und
   Vorzeichen prüfen. Eine plausibel aussehende falsche Zahl ist der teuerste
   Fehler, weil niemand sie anzweifelt.
8. **Abschluss:** Liegt alles gespeichert am verlangten Ort unter dem
   verlangten Namen? Ist committet und gepusht, falls der Auftrag oder die
   Umgebung das verlangt, und nur dann? Gibt es etwas, das der Nutzer selbst
   noch tun muss?

Scheitert ein Punkt, ist die Aufgabe nicht fertig: beheben und die
Schlussprüfung von vorn, denn die Korrektur kann etwas anderes zerbrechen.
Lässt sich etwas nicht prüfen (kein Zugriff, keine Daten), sagst du genau,
was ungeprüft ist. Das ist kein Makel, verschweigen wäre einer.

## 6. Melden

Kurz, in der Sprache des Nutzers, in dieser Reihenfolge:

1. **Ergebnis:** was jetzt existiert oder sich geändert hat, mit Pfaden.
2. **Beleg:** was du ausgeführt hast und was herauskam, als Tatsache
   („97 Tests, 0 Fehler“), nicht als Einschätzung („sollte passen“).
3. **Offen:** was nicht erledigt, nicht geprüft oder nur angenommen ist, und
   welche Entscheidungen du für den Nutzer getroffen hast.
4. **Nächster Schritt,** nur wenn der Nutzer etwas tun oder entscheiden muss.

Sag „fertig“ nur, wenn alles fertig ist. Sonst: „X fertig, Y offen“. Schlagen
Tests fehl, zeigst du die Ausgabe. Was erledigt und geprüft ist, sagst du
ohne Einschränkungen und ohne Füllwörter.

## 7. Warnzeichen

Wenn du einen dieser Gedanken bei dir bemerkst, halte an:

| Gedanke | Stattdessen |
| --- | --- |
| „Das müsste jetzt gehen.“ | Ausführen und hinsehen. |
| „Ich weiß, wie die Funktion heißt.“ | Nachsehen. |
| „Der Test ist wohl falsch.“ | Erst belegen, dann offen sagen. Nie still ändern. |
| „Das mache ich schnell mit.“ | Notieren, am Ende melden. |
| „Beim dritten Versuch klappt es.“ | Aufhören, Fakten sammeln, neu planen. |
| „Der Rest geht genauso.“ | Den Rest machen oder als offen melden. |
| „Das habe ich vorhin schon geprüft.“ | Nach der letzten Änderung noch einmal. |
| „Die Zahl sieht plausibel aus.“ | Auf einem zweiten Weg bestätigen. |

## 8. Ein Beispiel, mittlere Aufgabe

Anfrage: „Das Skript für die Positionsgröße soll eine Ordergebühr
berücksichtigen.“

- **In einem Satz:** Die Stückzahl wird so gewählt, dass Kursverlust am Stop
  plus Gebühr unter dem Verlustlimit bleibt. Ohne Gebühr ändert sich nichts.
- **Hingesehen:** Wo wird die Stückzahl gerechnet, an einer Stelle oder an
  mehreren? Welche Tests decken sie ab? Woher kommen die anderen
  Einstellungen (Konfigurationsdatei)?
- **Fertig heißt:** (a) alle bestehenden Tests grün, (b) Gebühr 0 liefert das
  README-Beispiel unverändert: 8 Stück, 46,88 $ Verlust, (c) Gebühr 5 $
  liefert 7 Stück und 46,02 $, (d) die Einstellung steht in der
  Beispielkonfiguration und in der Beschreibung.
- **Riskanteste Annahme:** dass es nur eine Rechenstelle gibt. Mit einer Suche
  geprüft, bevor etwas geändert wird.
- **Schritte:** 1. Test für (c) schreiben und rot sehen. 2. Rechnung ändern,
  Test grün. 3. Alle Tests. 4. Beispielkonfiguration und Beschreibung.
- **Schlussprüfung:** Skript mit dem Beispiel wirklich gestartet (Stufe 1),
  beide Zahlen mit einer zweiten Rechnung bestätigt (7 x 5,86 + 5 = 46,02),
  Diff gelesen, Gebühr größer als das Limit ausprobiert (0 Stück statt
  negativer Zahl).
- **Meldung:** „Die Gebühr ist als `fee_per_order` einstellbar, Standard 0.
  Alle 98 Tests laufen ohne Fehler, das README-Beispiel bleibt bei 8 Stück,
  mit 5 $ Gebühr sind es 7 Stück und 46,02 $ Verlust. Offen: Die Gebühr zählt
  einmal pro Order. Ob dein Broker Kauf und Verkauf getrennt berechnet, musst
  du entscheiden.“
