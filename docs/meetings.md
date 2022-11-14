# Meeting-Protokolle
##  16.09.2022
#### Inhaltliches
* Was noch entschieden werden muss:
    * Themenschwerpunkt Dyslexia oder Twitterlehrerzimmer?

_Das Sammeln über Twitterlehrerzimmer Twlz im best Case scenario wird sich über Dyslexia ausgetauscht... Wenn nicht dann müssen wir schauen, was der Datensatz hergibt - Stichwort: data-driven analysis_

* Theoretisches Einarbeiten
- [Wiki](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/Literatur/Wiki%20MLCluster.html)
- [Masterarbeit](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/Literatur/Dyslexia%20and%20Twitter.pdf)
- Script DSC Data Science

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


* Datensatz-Export als .json möglich mit auswählbarem Hashtag ('Twitterlehrerzimmer', 'twlz', 'Dyslexia', 'LRS') und Standard-Twitter-API: [recent_tweets.py](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/recent_tweets.py)
## 23.09.2022

* Academic Research Account bei Twitter beantragt, jetzt warten auf Freigabe
* Projekt und zweites Repo auf Github eingerichtet für Projektverwaltung und Dokumentationsmöglichkeit mit Docsify
* Projektanmeldung ausgefüllt und zur Unterschrift vorgelegt

## 21.10.2022

* Academic Research App ist angelegt
* Projektanmeldung ist durch
* Dokumentation via Docsify & GitHubPages ist live unter https://rauschii.github.io/Praxisprojekt_Doku_MJ/#/
TwitterLehrerZimmer2022/blob/main/search_recent_tweets.ipynb):
	* #twitterlehrerzimmer, #Twitterlehrerzimmer, #twlz ohne Retweets
	* letzte 7 Tage

* bis zum nächsten Mal:
    * Datensätze in den Zeiträumen Januar 2020 - Juli 2020, März 2020 - Juli 2020 und März 2020 - März 2021 generieren
	* nach Häufigkeit von LRS, Dyslexie, Lese-Rechtschreibschwäche, Lese- / Rechtschreibstörung und Lese- / Rechtschreibschwäche suchen
	* Code für Datensatz mit Tweepy und Jupyter Notebook und dem Extended Account ist erstellt unter [search_recent_tweets.ipynb](https://github.com/Rauschii/

## 11.11.2022
* [count-tweetVolume.ipynb](https://github.com/Rauschii/TwitterLehrerZimmer2022/blob/main/count-tweetVolume.ipynb) vorgestellt
* weitere Queries entwickelt:
	* Dyslexia (#Twitterlehrerzimmer OR #twlz)
	* Leseschwäche (#Twitterlehrerzimmer OR #twlz)
	* Rechtschreibschwäche (#Twitterlehrerzimmer OR #twlz)
	* Leserechtschreibschwäche (#Twitterlehrerzimmer OR #twlz)
	* Legasthenie (#Twitterlehrerzimmer OR #twlz)
	* Legastheniker (#Twitterlehrerzimmer OR #twlz)
	* Dyslexia
	* Leseschwäche
	* Rechtschreibschwäche
	* Leserechtschreibschwäche
	* Legasthenie
	* Legastheniker
* Aufgabe zunächst: Tweetvolumen für einzelne Stichpunkte/Keywords herausbekommen und erst im zweiten Schritt kombinieren
* eventuell ist SLR eine geeignete Methode um den Datensatz zusammenzustellen
* weitere Ideen für Queries:
	* Rechtschreibfehler einbauen
	* 2019, 2020 und 2021 vergleichen

* bis zum nächsten Mal:
	* Tweetvolumen für die neuen Queries bekommen
	* einzelne Queries stichprobenartig als Datensatz zusammenstellen



