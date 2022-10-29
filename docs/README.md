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
* Einarbeiten in Machine Learning besonders mit
    * [Machine Learning mit Python und Scikit-learn und TensorFlow : das umfassende Praxis-Handbuch für Data Science, Deep Learning und Predictive Analytics](https://books.google.de/books/about/Machine_Learning_mit_Python_und_Scikit_L.html?id=JM5CDwAAQBAJ&redir_esc=y)
        * nur wenig, zuviel Mathematik für den Einstieg
    * [Machine Learning kurz und gut](https://oreilly.de/produkt/machine-learning-kurz-gut/)
        * viel besser, mit Praxisbeispielen zum Nachprogrammieren
        * leider deckt das Buch nur Überwachtes Lernen ab, das wird bei diesem Vorhaben nicht viel Nützen - trotzem ein gutes Buch, um den Einstieg in Jupyther, Pandas und SciKi-Learn zu üben

### Inhaltliches
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
    * gesuchte Tweets ursprünglich (immer ohne Retweets):
        * mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz` **(A)**
        * mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz` in Verbindung mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` **(B)**
        * mit den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer ODER \#twlz` in Verbindung mit den Wörtern `Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` (ohne LRS) **(C)**

 Die ursprünglich gesuchten Begriffe sind die offiziellen Bezeichnungen *Lese- / Rechtschreibstörung* und *Lese- / Rechtschreibschwäche*. Die Twitter-API überspringt bei der Suche jedoch das Zeichen "/" und würde einen Fehler ausgeben, würde man dennoch danach suchen. (siehe https://twittercommunity.com/t/forward-slash-in-the-query/165927/2).

#### Ergebnisse

|                                 | A (nur Twlz) | B (+LRS) | C (-LRS) |
|---------------------------------|--------------|----------|----------|
| 01.01.20 - 31.07.20 (7 Monate)  | 90.014       | 23       | 2        |
| 01.03.20 - 31.07.20 (5 Monate)  | 111.600      | 33       | 3        |
| 01.03.20 - 28.02.21 (12 Monate) | 243.781      | 70       | 5        |
 Wegen der wenigen Ergebnisse bei den Kombinationen habe ich die Suche zusätzlich ohne die Hashtags rund um `Twitterlehrerzimmer`durchgeführt:
 * mit den Wörtern `Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` **(D)**
 * mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche` (mit LRS) **(E)**

|                                 | A (nur Twlz) | B (+LRS) | C (-LRS) | D (-Twlz ) | E (-Twlz mit LRS) |
|---------------------------------|--------------|----------|----------|------------|-------------------|
| 01.01.20 - 31.07.20 (7 Monate)  | 90.014       | 23       | 2        | 5.140      | 43.858            |
| 01.03.20 - 31.07.20 (5 Monate)  | 111.600      | 33       | 3        | 7.372      | 58.653            |
| 01.03.20 - 28.02.21 (12 Monate) | 243.781      | 70       | 5        | 15.178     | 153.153           |
Weil das Ergebnis der Query **E**  mit dem Stichwort *LRS* über 12 Monate vergleichsweise hoch ist, habe noch zusätzlich eine Einschränkung auf die Sprache Deutsch vorgenommen:

 * mit den Wörtern `LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- Rechtschreibstörung ODER Lese- Rechtschreibschwäche UND Deutsch` **(F)**

Außerdem wollte ich noch wissen, ob die Twitter-API bei der Suche ähnlich zum Zeichen "/" auch Leerzeichen irgnoriert und deswegen `Lese-Rechtschreibschwäche` und `Lese- Rechtschreibschwäche` redundant sind. Deswegen habe ich über den Zeitraum 12 Montate diese beiden Suchen vorgenommen:

* mit den Wörtern `(Lese-Rechtschreibschwäche ODER Lese- Rechtschreibschwäche` **(G)**
* mit den Wörtern `Lese-Rechtschreibschwäche` **(H)**

|                                 | A (nur Twlz) | B (+LRS) | C (-LRS) | D (-Twlz ) | E (-Twlz mit LRS) | F (lang:de) | G (+Leerz.) | H (-Leerz.) |
|---------------------------------|--------------|----------|----------|------------|-------------------|-------------|-------------|-------------|
| 01.01.20 - 31.07.20 (7 Monate)  | 90.014       | 23       | 2        | 5.140      | 43.858            |             |             |             |
| 01.03.20 - 31.07.20 (5 Monate)  | 111.600      | 33       | 3        | 7.372      | 58.653            |             |             |             |
| 01.03.20 - 28.02.21 (12 Monate) | 243.781      | 70       | 5        | 15.178     | 153.153           | 3586        | 343         | 285         |


Die drei Ergebnis-Dateien mit den exakten Queries befinden sich hier:
[tweetcount-01.01.2020-31.07.2020.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.01.2020-31.07.2020.txt)
[tweetcount-01.03.2020-31.07.2020.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.03.2020-31.07.2020.txt)
[tweetcount-01.03.2020-28.02.2021.txt](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/data/tweetcount-01.03.2020-28.02.2021.txt)

#### Gedanken dazu

* Das Tweet-Volumen zu den Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer und \#twlz` sowohl über 5, 7, als auch 12 Monate während der ersten Lockdowns ist  groß genug, um über diese Themen inhaltliche Auswertungen machen zu können
* Wird jedoch das Themenfeld *Dyslexie* kombiniert, reicht vermutlich sogar ein Zeitraum von 12 Monaten nicht aus. Hier wurden nur `70` Tweets gezählt. Lässt man das Stichwort `LRS` weg, sogar nur `5`
* Die Zeiträume 5, 7,  und 12 Monate während der ersten Lockdowns würden auch ausreichen, um nur das Themenfeld *Dyslexie* ohne die  Hashtags `\#twitterlehrerzimmer, \#Twitterlehrerzimmer und \#twlz`zu betrachten. Allerdings ist das Stichwort `LRS` vermutlich zu generisch. Damit sollte bei der Untersuchung später umgegangen werden: zum Beispiel durch Einschränkung auf Deutsch (es könnte immernoch die Ergebnisse verfälschen) oder durch Weglassen aus der Suche.
* Es muss sich vermutlich entschieden werden was betrachtet werden soll:
    * Twitterlehrerzimmer
    * Dyslexie
    * Zeitraum ausweiten

* Die Begriffe *Lese-Rechtschreibschwäche* und  *Lese- /Rechtschreibschwäche* können getrennt untersucht werden

---

# Meeting-Protokolle
##  Meeting 16.09.2022
#### Inhaltliches
* Was noch entschieden werden muss:
    * Themenschwerpunkt Dyslexia oder Twitterlehrerzimmer?

_Das Sammeln über Twitterlehrerzimmer Twlz im best Case scenario wird sich über Dyslexia ausgetauscht... Wenn nicht dann müssen wir schauen, was der Datensatz hergibt - Stichwort: data-driven analysis_

* Theoretisches Einarbeiten
- [Wiki](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/Literatur/Wiki%20MLCluster.html)
- [Masterarbeit](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/Literatur/Dyslexia%20and%20Twitter.pdf)
- Script  DSC Data Science

####  Technisches
* Klärung API: Welches API-Level ist für das Projekt nötig? Reicht Elevated oder muss es Academic Research sein?
* Mit den Elevated Credentials Zugriffe auf die API probieren
    * **Testergebnis Key Sharing und Elevated API**

        Das Key Sharing funktioniert problemlos. Man kann auf alle Endpunkte des Elevated Levels zugreifen.

        Die API im Elevated Level bietet leider keine Möglichkeit, die Suche zeitlich einzugrenzen bzw. weiter zurückzugehen. Der Endpunkt zur Tweetsuche ist [/2/tweets/search/recent](https://developer.twitter.com/en/docs/twitter-api/tweets/search/api-reference/get-tweets-search-recent) und die maximale Zeit, die zurückverfolgt werden kann, ist 7 Tage (siehe Parameter `start_time` ). Einen beliebigen Zeitraum kann man nur in der Kategorie "Academic Research" abfragen (siehe [ /2/tweets/search/all ](https://developer.twitter.com/en/docs/twitter-api/tweets/search/api-reference/get-tweets-search-all))

* ggf. Academic Research bei Twitter beantragen

#### Administratives
* Anmeldung Projekt ausfüllen "Bereitstellen und Aufbereiten von Datensätzen aus Twitter zur späteren Weiterverarbeitung mit Machine Learning"
* Welche Dokumentationsmöglichkeit soll genutzt werden?
    * **Dokumentationsmöglichkeiten**

        Ich schlage die eine Dokumentation über Github Pages und [Docsify](https://github.com/docsifyjs/docsify) vor. Das ist ein Dokumentationsstandard und damit wiederum in sich gut dokumentiert. Leider sind Github Pages nur mit öffentlichen Repositories kostenlos. Deswegen muss entweder das Repository öffentlich gemacht werden oder die Dokumentation würde in einem anderen (öffentlichen) Repository liegen. Zweiteres ist zwar etwas umständlich, weil dann immer zwischen den Repos gewechselt werden muss beim Arbeiten, hat aber den Vorteil, dass wir weiter Key-Sharing im eigentlichen Projekt betreiben könnten, wie wir es jetzt schon tun mit Twitter Key, Secret und Bearer Token.
        Desweiteren schlage ich vor, das Repository in ein GitHub-Projekt zu verschieben, beziehungsweise dafür ein Projekt zu eröffnen, weil dann das Feature einer Projektverwaltung genutzt werden kann, was die Übersichtlichkeit und Nachvollziehbarkeit deutlich erleichtert.

#### Stand
Datensatz-Export als .json möglich mit auswählbarem Hashtag ('Twitterlehrerzimmer', 'twlz', 'Dyslexia', 'LRS') und Standard-Twitter-API: [recent_tweets.py](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/recent_tweets.py)
## Meeting 23.09.2022

* Academic Research Account bei Twitter beantragt, jetzt warten auf Freigabe
* Projekt und zweites Repo auf Github eingerichtet für Projektverwaltung und Dokumentationsmöglichkeit mit Docsify
* Projektanmeldung ausgefüllt und zur Unterschrift vorgelegt

## Meeting 21.10.2022

* Academic Research App ist angelegt
* Projektanmeldung ist durch
* Dokumentation via Docsify & GitHubPages ist live unter https://rauschii.github.io/Praxisprojekt_Doku_MJ/#/
* bis zum nächsten Mal:
    * Datensätze in den Zeiträumen Januar 2020 - Juli 2020, März 2020 - Juli 2020 und März 2020 - März 2021 generieren
	* nach Häufigkeit von LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- / Rechtschreibstörung und Lese- / Rechtschreibschwäche suchen

#### Stand
Code für Datensatz mit Tweepy und Jupyter Notebook und dem Extended Account ist erstellt unter [search_recent_tweets.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/search_recent_tweets.ipynb):
* #twitterlehrerzimmer, #Twitterlehrerzimmer, #twlz ohne Retweets
* letzte 7 Tage


