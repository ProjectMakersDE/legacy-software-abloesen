# Phase 2: Anforderungen und Machbarkeit

Ziel: Sie legen fest, was die neue Software können muss. Danach wählen Sie die Technik und prüfen, ob das Vorhaben in Ihrem Haus umsetzbar ist. In dieser Reihenfolge.

## Anforderungen

Grundlage ist das Inventar aus [Phase 1](01-bestandsaufnahme.md) ohne die Streichliste. Dazu kommt, was heute fehlt: die Excel-Listen und Zettel neben dem Bildschirm.

Beschreiben Sie Anforderungen als Ergebnis für die Menschen, die damit arbeiten, nicht als Kopie der alten Maske. „Eine Rückgabe ist in unter einer Minute erfasst" lässt Raum für eine bessere Lösung. „Maske R12 nachbauen" lässt keinen.

Vergessen Sie die Anforderungen nicht, die niemand von selbst nennt:

- Mengengerüst: Datensätze, gleichzeitige Nutzer, Spitzenzeiten.
- Aufbewahrungspflichten: Altdaten müssen oft noch Jahre nach der Abschaltung lesbar sein, etwa nach Handels- und Steuerrecht.
- Schnittstellen zu Buchhaltung, Banken, Kunden und Lieferanten, mit den Formaten, die dort erwartet werden.

## Technik

Erst die Anforderungen, dann die Technik. Wer umgekehrt anfängt, passt die Anforderungen an ein Werkzeug an, das schon feststeht.

Fragen, die bei der Wahl mehr zählen als die aktuelle Mode:

- Wer betreibt und pflegt das System in zehn Jahren, und gibt es dafür Fachkräfte?
- Kommt die neue Technik zuverlässig an die alte Datenbank heran, lesend und schreibend? Ohne diese Brücke funktioniert der schrittweise Umzug aus [Phase 4](04-schrittweise-umziehen.md) nicht.
- Läuft das System in der Cloud, im eigenen Serverraum oder bei einem Dienstleister, und was bedeutet das für Datenschutz und Verträge?

Bauen Sie für die riskanteste Stelle einen kleinen Durchstich, bevor Sie sich festlegen. Meist ist das die Brücke zur alten Datenbank oder eine Schnittstelle mit wenig Dokumentation.

## Machbarkeit in Ihrem Haus

Die beste technische Lösung hilft nichts, wenn sie zu den Ressourcen des Unternehmens nicht passt. Prüfen Sie:

- Personal: Wer hat Zeit für Konzept, Tests und Pilotbetrieb? Die Menschen, die Sie dafür brauchen, sind meist die, die im Tagesgeschäft am meisten gefragt sind.
- Betrieb: Wer kümmert sich um Updates, Sicherungen und Störungen?
- Hardware: Was ist nötig, und wer betreibt es?

Ein Beispiel, bei dem das auseinanderläuft: Die neue Software soll viel mit KI arbeiten, und zwar mit sensiblen Kundendaten, die das Haus nicht verlassen dürfen. Das Unternehmen kann aber keine eigene Hardware für KI-Modelle betreiben. Dann muss eine der Annahmen weichen. Vielleicht genügt KI auf anonymisierten Daten. Vielleicht ist gemietete Rechenleistung mit einem passenden Vertrag vertretbar. Vielleicht kommt die KI-Funktion später. Wichtig ist, dass diese Entscheidung jetzt fällt und nicht erst mitten im Projekt.

## Ergebnis der Phase

- Eine Muss-Liste mit Prioritäten.
- Eine Technikentscheidung mit Begründung und einem Durchstich für die riskanteste Stelle.
- Eine Liste der Voraussetzungen im Unternehmen: Personal, Betrieb, Hardware.

## Fragen zum Nachdenken

- Welche Anforderung haben Sie aus der alten Software übernommen, ohne zu fragen, ob sie noch jemand braucht?
- Wer pflegt die neue Software, wenn das Projektteam weiterzieht?

---

[Übersicht](../README.md) | Zurück: [Phase 1](01-bestandsaufnahme.md) | Weiter: [Phase 3: Konzept mit den Mitarbeitern](03-konzept-mit-den-mitarbeitern.md)
