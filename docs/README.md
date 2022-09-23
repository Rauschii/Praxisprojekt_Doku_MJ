# Protokolle
##  Meeting 16.09.2022
### ToDos

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

## Meeting 23.09.2022

* Academic Research bei Twitter beantragt, jetzt warten auf Freigabe
* Projekt und zweites Repo auf Github eingerichtet für Projektverwaltung und Dokumentationsmöglichkeit mit Docsify
* Projektanmeldung ausgefüllt und zur Unterschrift vorgelegt
