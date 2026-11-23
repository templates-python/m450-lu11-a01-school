# M450 LU11.A02 - Schulverwaltung

Entwickeln Sie die Schulverwaltung als Gruppe testgetrieben (Test Driven
Development). Jede Person entwickelt eine Klasse und ersetzt die Klassen der
anderen in den Tests durch Mocks.

Wiki: <https://wiki.bzz.ch/modul/m450/learningunits/lu11/aufgaben/school>
(dort ist auch das UML-Klassendiagramm)

## Ausgangslage

`main.py` zeigt, wie die Klassen `SchoolClass`, `Student`, `ClassReport`,
`Subject` und `Grade` zusammenspielen sollen. Die Klassen selbst sind nur als
leere Hüllen vorhanden, die Testmodule `test_*.py` sind leer.

Die Klasse `StudentReport` aus dem Klassendiagramm heisst in diesem Repository
`ClassReport` (Datei `classreport.py`). Verwenden Sie diesen Namen.

## Vorgehen

1. Gruppe bilden (Classroom 50, höchstens 4 Personen):
   - Eine Person öffnet den Link zur Aufgabe, klickt auf **Create group**
     (der Gruppenname ist freiwillig) und fügt die anderen unter
     **Manage my group** mit ihrem GitHub-Username hinzu (**Add**).
   - Die anderen öffnen den Link danach erneut. Alternativ: bei der Gruppe
     **Ask to join**, auf GitHub **Request to join**, nach der Bestätigung auf
     der Accept-Seite **Check again**.
2. Das gemeinsame Repository klonen.
3. Klassen verteilen. **Jede Person** erstellt **ein** Issue für ihren Teil
   (Titel siehe Tabelle) und trägt sich selbst als *Assignee* ein.

   | Person | Klassen | Titel des Issues |
   | --- | --- | --- |
   | 1 | `Grade` und `Student` | Grade und Student |
   | 2 | `Subject` | Subject |
   | 3 | `ClassReport` | ClassReport |
   | 4 | `SchoolClass` | SchoolClass |

4. Entwickeln Sie Ihre Klasse im Zyklus **Red → Green → Refactor**. Beginnen
   Sie mit dem Test für den Konstruktor, danach folgen die Methoden einzeln.

   | Schritt | Was Sie tun | Commit-Message |
   | --- | --- | --- |
   | Red | einen Test schreiben, ausführen: rot | `red: test add_grade` |
   | Green | Methode programmieren, bis alle Tests grün sind | `green: add_grade` |
   | Refactor | aufräumen, bis pylint keine Meldungen mehr hat | `refactor: ...` |

5. Vor jedem Push die Änderungen der anderen holen: **Pull**, dann **Push**.
6. Ist Ihr Teil fertig, schliessen Sie Ihr Issue mit einem Commit, dessen
   Message `closes #n` enthält.
7. Sind alle Klassen fertig, ersetzen Sie in `main.py` die Aufrufe `print_...`
   durch `print(...show_...())` und führen Sie das Programm aus.

## Hinweise

- `Grade` wird als `@dataclass` realisiert. Eine Note liegt zwischen 1.0 und 6.0.
- Eine Klasse hat höchstens 20 Lernende, ein Fach höchstens 4 Noten. Wird die
  Grenze überschritten, löst die Methode einen `IndexError` aus.
- Die Methoden `show_...` liefern einen String zurück und geben nichts mit
  `print` aus.
- Benötigt eine Methode ein Objekt einer anderen Klasse, verwenden Sie im Test
  eine Mock-Klasse. Ihre Tests dürfen nicht davon abhängen, ob die Klassen der
  anderen schon fertig sind.

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

`unittests.json` ist leer: Die Tests (Konstruktor, Normalfälle, Grenzwerte,
Fehlerfälle, Mocks) und die Commits (Red, Green, Refactor nachvollziehbar)
werden von Hand bewertet.

## Abgabe

Die Abgabe erfolgt durch den Push ins gemeinsame GitHub-Repository.
