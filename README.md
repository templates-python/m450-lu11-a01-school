# M450 LU11.A01 - Schulverwaltung

Entwickeln Sie die Applikation als Gruppe nach dem Prinzip des Test Driven
Developments.

Wiki: <https://wiki.bzz.ch/modul/m450/learningunits/lu11/aufgaben/school>
(dort ist auch das UML-Klassendiagramm)

## Ausgangslage

`main.py` zeigt, wie die Klassen `SchoolClass`, `Student`, `ClassReport`,
`Subject` und `Grade` zusammenspielen sollen. Die Klassen selbst sind nur als
leere Hüllen vorhanden, die Testmodule `test_*.py` sind leer.

Beim Anlegen des Repositorys werden die Issues aus der Vorlage übernommen.
Sie zeigen, welche Unittests und Funktionen bereits geplant sind.

## Vorgehen

1. Aufgabe annehmen und einer offenen Gruppe beitreten oder eine neue Gruppe
   eröffnen. Neue Gruppen beginnen **zwingend** mit dem Klassennamen, z. B.
   `im23a-gruppenname`.
2. Das gemeinsame Repository klonen.
3. Zu Beginn schreibt jedes Gruppenmitglied die Unittests zu mindestens einer
   Funktion. Danach realisieren Sie entweder eine Funktion, zu der die Tests
   schon vorhanden sind, oder schreiben die Tests zu einer weiteren Funktion.

### Unittests schreiben

1. Wählen Sie eine Klasse (Konstruktor) oder Funktion, die noch niemand
   bearbeitet.
2. Erstellen Sie ein Issue «Unittests *Funktionsname*» und tragen Sie sich als
   verantwortlich ein.
3. Schreiben Sie die Unittests. Benötigt die Funktion ein Objekt einer anderen
   Klasse, verwenden Sie einen Mock.
4. Commit mit `resolves #n` in der Message, **Pull**, dann **Push**.
5. Erstellen Sie ein Issue mit dem Namen der Funktion, z. B. «add_student».

### Funktion realisieren

1. Wählen Sie ein offenes Issue und tragen Sie sich als verantwortlich ein.
2. **Pull**, Funktion realisieren und testen.
3. Commit mit `resolves #n` in der Message, **Pull**, dann **Push**.

Sind die Unittests unvollständig oder fehlerhaft, besprechen Sie das mit der
Person, die sie geschrieben hat.

## Hinweise

- `Grade` wird als `@dataclass` realisiert.
- Der Unittest für den Konstruktor einer Klasse wird immer zuerst geschrieben.

## Lokal testen

```bash
pip install -r requirements.txt
pytest
python _run_pylint.py
```

## Bewertung

| Teil | Punkte |
| --- | --- |
| Linting der Klassen und von `main.py` | 5 |
| **Total automatisch** | **5** |

`unittests.json` ist leer: Die Unittests und die Arbeit mit den Issues zählen
nicht automatisch.
