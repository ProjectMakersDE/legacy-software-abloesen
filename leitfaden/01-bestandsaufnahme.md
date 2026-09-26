# Phase 1: Bestandsaufnahme

Ziel: Sie wissen, was die alte Software heute tatsächlich tut und was davon noch gebraucht wird. Handbücher und Pflichtenhefte von damals helfen dabei wenig. Sie beschreiben, was die Software können sollte, nicht wie sie heute benutzt wird.

## Über die Schulter schauen

Setzen Sie sich einen Tag lang neben die Menschen, die mit der Software arbeiten, und schreiben Sie mit. Welche Masken öffnen sie in welcher Reihenfolge? Wo tippen sie Daten ab, die schon an anderer Stelle stehen? Wo liegt eine Excel-Liste oder ein Zettel neben dem Bildschirm, weil die Software etwas nicht kann?

Das ist aufwendig, und es lohnt sich. Sie finden Umwege, die in keiner Dokumentation stehen. Und die Mitarbeiter erleben von Anfang an, dass ihre Arbeit ernst genommen wird. Sagen Sie vorher klar, worum es geht: um die Software, nicht um die Leistung der Person.

## Zählen, was genutzt wird

Beobachtung zeigt die Abläufe. Wie oft eine Funktion gebraucht wird, zeigt sie nicht. Prüfen Sie zuerst, ob es schon Nutzungszahlen gibt, etwa in Protokollen des Webservers oder der Schnittstellen. Wenn nicht, bauen Sie einfache Zähler ein: welcher Button, welche Maske, welcher Bericht und welche Schnittstelle wie oft aufgerufen wird. Lassen Sie die Zähler eine Woche bis einen Monat laufen.

Eine Messung dieser Länge übersieht seltene Termine. Jahresabschluss, Inventur oder Quartalsberichte laufen vielleicht nie im Messzeitraum. Null Aufrufe heißen deshalb nicht automatisch, dass eine Funktion überflüssig ist. Fragen Sie bei jeder solchen Funktion die Fachabteilung, bevor Sie sie streichen.

## Was wegfallen kann

Oft gibt es Funktionen, die niemand mehr braucht, weil sich das Geschäft verändert hat. Ein Produkt wird nicht mehr verkauft, ein Partner ist weggefallen, ein Bericht wird seit Jahren nicht mehr gelesen. Diese Funktionen bauen Sie nicht neu. Das spart in der Regel am meisten Geld: Eine Funktion, die Sie nicht bauen, müssen Sie auch nicht testen, migrieren und schulen. Wie stark das ins Gewicht fällt, zeigt das [Rechenbeispiel](../rechenbeispiel.md).

Wie viel das in Ihrem System ist, weiß vorher niemand. Eine Auswertung des Analyseanbieters Pendo aus dem Jahr 2019 kam über 615 Abonnements von Pendo-Kunden und drei Monate Nutzungsdaten zu diesem Ergebnis: 24 % der erfassten Funktionen wurden nie genutzt, weitere 56 % teilten sich die letzten 5 % der Nutzung. Die Zahlen stammen aus Softwareprodukten von Pendo-Kunden, nicht aus Individualsoftware im Mittelstand, und Pendo verkauft selbst Werkzeuge zur Nutzungsmessung. Sie zeigen, dass ungenutzte Funktionen häufig sind. Wie viele es bei Ihnen sind, zeigt nur Ihre eigene Messung. Quelle: [Pendo, The 2019 Feature Adoption Report](https://www.pendo.io/resources/the-2019-feature-adoption-report/).

## Messen, ohne Mitarbeiter zu überwachen

> Dieser Abschnitt ist keine Rechtsberatung. Klären Sie die Messung im Einzelfall mit Ihrem Betriebsrat, Ihrem Datenschutzbeauftragten und bei Bedarf mit einer Fachanwältin oder einem Fachanwalt für Arbeitsrecht.

In Deutschland kann eine solche Messung mitbestimmungspflichtig sein. Nach [§ 87 Abs. 1 Nr. 6 BetrVG](https://www.gesetze-im-internet.de/betrvg/__87.html) hat der Betriebsrat mitzubestimmen bei technischen Einrichtungen, die dazu bestimmt sind, das Verhalten oder die Leistung der Arbeitnehmer zu überwachen. Das Bundesarbeitsgericht legt das weit aus: Es genügt, dass eine Einrichtung dazu objektiv geeignet ist. Auf eine Überwachungsabsicht kommt es nicht an ([BAG, Beschluss vom 16.07.2024, 1 ABR 16/23](https://www.bundesarbeitsgericht.de/entscheidung/1-abr-16-23/)). Sobald sich Daten einer Person zuordnen lassen, gilt außerdem das Datenschutzrecht, allen voran die DSGVO.

Unsere Empfehlung:

- Zählen Sie nur anonym und zusammengefasst: Funktion, Tag, Anzahl. Keine Benutzerkennung, kein Rechnername, keine Uhrzeit je Aufruf.
- Achten Sie auf kleine Gruppen. Wenn nur eine Person eine Funktion nutzt, verrät auch die Summe etwas über diese Person. Zählen Sie dann gröber oder gar nicht.
- Binden Sie Betriebsrat und Datenschutzbeauftragten ein, bevor der erste Zähler läuft. Halten Sie Zweck, Dauer und Löschung schriftlich fest.
- Die Zähler helfen in [Phase 4](04-schrittweise-umziehen.md) noch einmal: Sie zeigen, ob eine alte Funktion weiter benutzt wird, obwohl die neue bereitsteht. Wenn Sie das vorhaben, nennen Sie diesen Zweck gleich mit.

## Ergebnis der Phase

- Ein Inventar: Funktionen, Masken, Berichte, Schnittstellen und Datenbanktabellen, jeweils mit gemessener Nutzung.
- Eine Streichliste mit den Funktionen, die nicht mehr gebraucht werden, bestätigt von der Fachabteilung.
- Die beobachteten Abläufe als Grundlage für das [Konzept in Phase 3](03-konzept-mit-den-mitarbeitern.md).

Einen Teil der Inventur kann ein Coding-Agent im Quellcode vorbereiten. Die Anweisung dafür steht auf Englisch in [agents/inventory.md](../agents/inventory.md).

## Fragen zum Nachdenken

- Wer in Ihrem Haus kann sagen, welche Funktionen nur einmal im Jahr gebraucht werden?
- Welche Excel-Listen existieren nur, weil die alte Software etwas nicht kann?
- Kennt Ihr Betriebsrat das Vorhaben schon?

---

[Übersicht](../README.md) | Weiter: [Phase 2: Anforderungen und Machbarkeit](02-anforderungen-und-machbarkeit.md)
