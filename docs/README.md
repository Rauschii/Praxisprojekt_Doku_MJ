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


