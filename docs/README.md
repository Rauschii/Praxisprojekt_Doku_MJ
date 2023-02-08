# Projekt-Protokoll
##  07. & 08.09.2022

Verbindung zu Twitter mit Test-Code zum generieren eines Account-Tokens [get_users_with_user_context.py](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/testcode/get_users_with_user_context.py)

Datensatz-Export von Tweets der letzten 7 Tage als .json mit auswählbarem Hashtag ('Twitterlehrerzimmer', 'twlz', 'Dyslexia', 'LRS') und Standard-Twitter-API: [recent_tweets.py](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/recent_tweets.py)

*Ziele*
* Wiederauffrischung von Python-Kenntnissen
* Einarbeitung in Twitter-API
* Verwendung von externen Libraries. Hier: inquirer & configparser


## Mitte September - Mitte Oktober
* Einrichten von Projektorganisatorischen Dingen, wie Projektdokumentation in Docsify (dieses hier) und einer Projektorganisation in [GitHub Project](https://github.com/users/Rauschii/projects/1)
* Recherche nach Literatur und Einarbeiten in Theorie von Machine Learning mit:
	* Masterarbeit "Dyslexia and Twitter"
	* Naked statistics : stripping the dread from the data
	* Machine Learning mit Python und Scikit-learn und TensorFlow : das umfassende Praxis-Handbuch für Data Science, Deep Learning und Predictive Analytics


## 16.10.2022

Erstellung einer Methode in Jupyter Notebook [search_recent_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_recent_tweets.ipynb) mit folgenden Features:
* Abfrage von Tweets der letzten 7 Tage mit Nutzung des Exteded Twitter Twitter Dev Accounts
* Verwendung der [Library Tweepy](https://www.tweepy.org) und damit Möglichkeit des Pagings der Ergebnisse, Abfragegröße ist per Parameter möglich
* Abfrage der Hashtags #twitterlehrerzimmer, #Twitterlehrerzimmer, #twlz ohne Retweets
* Angabe der Sprache möglich

*Ziele*
* Einarbeitung in Jupyter Notebooks, Panda und Numpy
* Ausprobieren und Bewerten von [Tweepy](https://www.tweepy.org/)
* Ausloten der Möglichkeiten der Twitter-API

## 17.-29.10.2022
### Theorie
* Einarbeiten in Machine Learning besonders mit
    * [Machine Learning mit Python und Scikit-learn und TensorFlow : das umfassende Praxis-Handbuch für Data Science, Deep Learning und Predictive Analytics](https://books.google.de/books/about/Machine_Learning_mit_Python_und_Scikit_L.html?id=JM5CDwAAQBAJ&redir_esc=y)
        * nur wenig, zuviel Mathematik für den Einstieg
    * [Machine Learning kurz und gut](https://oreilly.de/produkt/machine-learning-kurz-gut/)
        * viel besser, mit Praxisbeispielen zum Nachprogrammieren
        * leider deckt das Buch nur Überwachtes Lernen ab, das wird bei diesem Vorhaben nicht viel Nützen - trotzem ein gutes Buch, um den Einstieg in Jupyther, Pandas und SciKi-Learn zu üben

### Praxis
#### Vorhaben
* Größere Zeiträume durchsuchen anhand Acadamic Research Account
* Tweet-Volumen messen von Hashtags rund um *Twitterlehrerzimmer* in Kombination mit dem Themenfeld *Dyslexie* über drei verschiedene Zeiträume zu Beginn der Corona Pandemie

#### Umsetzung
* Acadamic Research Account eingebunden
* Erstellung eines Jupyter Notebooks [count-tweetVolume.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/count-tweetVolume.ipynb) zum Zählen von Tweets über bestimmte Zeiträume und mit bestimmen Hashtag- und Stickwortkombinationen:
    * Zeiträume:
        * 01.01.2020 - 31.07.2020 (7 Monate)
        * 01.03.2020 - 31.07.2020 (5 Monate)
        * 01.03.2020 - 28.02.2021 (12 Monate)
    * ursprünglich gesuchte Tweets (immer ohne Retweets):
        * **(A)** mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz`
        * **(B)** mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz` in Verbindung mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche`
        * **(C)** mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz` in Verbindung mit den Wörtern `Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` (ohne LRS)

 Die ursprünglich gesuchten Begriffe sind die offiziellen Bezeichnungen *Lese- / Rechtschreibstörung* und *Lese- / Rechtschreibschwäche*. Die Twitter-API überspringt bei der Suche jedoch das Zeichen "/" und würde einen Fehler ausgeben, würde man dennoch danach suchen. (siehe https://twittercommunity.com/t/forward-slash-in-the-query/165927/2).

#### Ergebnisse

|                                   | `A (nur Twlz)` | `B (+LRS)` | `C (-LRS)` |
|-----------------------------------|----------------|------------|------------|
| `01.03.20 - 31.07.20 (5 Monate)`  | `36.215`       | `23`       | `2`        |
| `01.01.20 - 31.07.20 (7 Monate)`  | `44.037`       | `33`       | `3`        |
| `01.03.20 - 28.02.21 (12 Monate)` | `127.962`      | `70`       | `5`        |
---
 Wegen der wenigen Ergebnisse bei den Kombinationen habe ich die Suche zusätzlich ohne die Hashtags rund um `Twitterlehrerzimmer`durchgeführt:
 * **(D)** mit den Wörtern `Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche`
 * **(E)** mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` (mit LRS)


|                                   | `A (nur Twlz)` | `B (+LRS)` | `C (-LRS)` | `D (-Twlz )` | `E (-Twlz mit LRS)` |
|-----------------------------------|----------------|------------|------------|--------------|---------------------|
| `01.03.20 - 31.07.20 (5 Monate)`  | `36.215`       | `23`       | `2`        | `5.089`      | `43.258`            |
| `01.01.20 - 31.07.20 (7 Monate)`  | `44.037`       | `33`       | `3`        | `7.312`      | `58.006`            |
| `01.03.20 - 28.02.21 (12 Monate)` | `127.962`      | `70`       | `5`        | `15.178`     | `150.474`           |
---
Weil das Ergebnis der Query **E**  mit dem Stichwort *LRS* über 12 Monate vergleichsweise hoch ist, habe noch zusätzlich eine Einschränkung auf die Sprache Deutsch vorgenommen:

 * **(F)** mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche UND Deutsch`

Außerdem wollte ich noch wissen, ob die Twitter-API bei der Suche ähnlich zum Zeichen "/" auch Leerzeichen irgnoriert und deswegen `Lese-Rechtschreibschwäche` und `Lese- Rechtschreibschwäche` redundant sind. Deswegen habe ich über den Zeitraum 12 Montate diese beiden Suchen vorgenommen:

* **(G)** mit den Wörtern `(Lese-Rechtschreibschwäche ODER Lese- Rechtschreibschwäche`
* **(H)** mit den Wörtern `Lese-Rechtschreibschwäche`

|                                   | `A (nur Twlz)` | `B (+LRS)` | `C (-LRS)` | `D (-Twlz )` | `E (-Twlz mit LRS)` | `F (lang:de)` | `G (+Leerz.)` | `H (-Leerz.)` |
|-----------------------------------|----------------|------------|------------|--------------|---------------------|---------------|---------------|---------------|
| `01.03.20 - 31.07.20 (5 Monate)`  | `36.215`       | `23`       | `2`        | `5.089`      | `43.258`            |               |               |               |
| `01.01.20 - 31.07.20 (7 Monate)`  | `44.037`       | `33`       | `3`        | `7.312`      | `58.006`            |               |               |               |
| `01.03.20 - 28.02.21 (12 Monate)` | `127.962`      | `70`       | `5`        | `15.178`     | `150.474`           | `3586`        | `343`         | `285`         |
---
Die drei Ergebnis-Dateien mit den exakten Queries befinden sich hier:
* [tweetcount-01.01.2020-31.07.2020.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.01.2020-31.07.2020.txt)
* [tweetcount-01.03.2020-31.07.2020.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.03.2020-31.07.2020.txt)
* [tweetcount-01.03.2020-28.02.2021.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.03.2020-28.02.2021.txt)

#### Gedanken dazu

* Das Tweet-Volumen zu den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer und \#twlz` sowohl über 5, 7, als auch 12 Monate während der ersten Lockdowns ist  groß genug, um über diese Themen inhaltliche Auswertungen machen zu können
* Wird jedoch das Themenfeld *Dyslexie* kombiniert, reicht vermutlich sogar ein Zeitraum von 12 Monaten nicht aus. Hier wurden nur `70` Tweets gezählt. Lässt man das Stichwort `LRS` weg, sogar nur `5`
* Die Zeiträume 5, 7,  und 12 Monate während der ersten Lockdowns würden auch ausreichen, um nur das Themenfeld *Dyslexie* ohne die  Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer und \#twlz`zu betrachten. Allerdings ist das Stichwort `LRS` vermutlich zu generisch. Damit sollte bei der Untersuchung später umgegangen werden: zum Beispiel durch Einschränkung auf Deutsch (es könnte immernoch die Ergebnisse verfälschen) oder durch Weglassen aus der Suche.
* Es muss sich vermutlich entschieden werden:
    * *Twitterlehrerzimmer* betrachen
    * *Dyslexie* betrachten
    * *Twitterlehrerzimmer* und *Dyslexie* betrachten und Zeitraum ausweiten

* Die Begriffe *Lese-Rechtschreibschwäche* und  *Lese- /Rechtschreibschwäche* können getrennt untersucht werden

## 7.11.2022
### Praxis
#### Vorhaben
* Daten mit der Library Twarc statt mit Tweepy auslesen (um eine Fehlerquelle auszuschließen und die gleichen Datensätze zu bekommen wie beim Tweet Count)
* Datensätze mit variablen Zeiträumen und Queries erstellen können mit für das Projekt möglicherweise interessanten Felder

#### Umsetzung
* die Queries A-H vom Messen der Tweet Volumen sind zur Wiederverwendung in die Kondigurations-Datei ausgelagert worden
* Erstellung des Jupyter Notebooks [search_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_tweets.ipynb), um Datensaätze aus variablen Zeiträumen und mit variablen Queries erstellen zu können
	* Speicherung als .json
	* Möglichkeit, die .json - Dateien als Dataframe wieder zu laden

#### Gedanken dazu
* das Laden und Aufbereiten der Datensätze dauert bei mehr als 100 Tweets recht lang. Es lohnt sich, sich vorher zu überlegen, welche Felder im Datensatz ausgelesen werden sollen.
* Bei der kleinen Stichprobe hat sich bereits gezeigt, dass es sich lohnt, auf die Sprache "Deutsch" einzuschränken, auch "Dyslexie" wird viel z.B. auf französisch verwendet
* **Mögliche interessante Fragen**:
	* Verhältnis Reichweite (Follower, Tweetmenge insgesamt) und Qualität der Tweets über Dyslexie
	* Verlauf von Dyslexie-Themen + #Twitterlehrerzimmer über einen längeren Zeitraum (vor-Corona, ab 03/20, 2021, 2022)
		* Menge
		* Qualität
	* Twitters gut/schlecht Algorithmus und "eigene" Themen-Cluster vergleichen: Wird eher gut oder eher schlecht über Dyslexie geschrieben?

## 13. & 14.11.2022
### Praxis
#### Vorhaben
* Tweetvolumen für die neuen Queries bekommen
* einzelne Queries stichprobenartig als Datensatz zusammenstellen
#### Umsetzung
* Queries sind jetzt durchnumeriert
* [count-tweetVolume.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/count-tweetVolume.ipynb) erweitert
	* Queries aus der config-Datei lesen, statt hart im Code
	* mehrere Queries hintereinander für einen Zeitraum abfragen können
	* Ergebnisse werden zusammengefasst und in einer .json Datei und in einer .md-Datei exportiert
* [search_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_tweets.ipynb) erweitert
	* Datensatz wird zu besseren Lesbarkeit zusätzlich zum .json auch als .md-Datei exportiert
* .json-Dateien dienen zur späteren Verarbeitung, .md-Dateien zur besseren Lesbarkeit
* Alle Ergebnisse sind in das Projekt-Protokoll eingebunden

## 29.12.2022
### Praxis
* Testcode gelöscht
* Counter in [search_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_tweets.ipynb) eingefügt zur besseren Überwachungsmöglichkeit beim erstellen des Datensets
* Code der beiden Jupyter Notebooks [count-tweetVolume.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/count-tweetVolume.ipynb) und [search_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_tweets.ipynb) bereinigt
* Navigation der Dokumentation repariert
* Datenset aus der Queries 2 und 25 erststellt, exportiert
* Datenset von Query 2 in Dokumentation eingebunden (Datenset von Query 25 ist 19MB groß, zu groß für die Dokumentation, kann im Projekt-Git eingesehen werden)
	* Datenset aus Query 1 wird aus Performance-Gründen später erstellt
