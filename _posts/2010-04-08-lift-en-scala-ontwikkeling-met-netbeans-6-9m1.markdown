--- 
layout: post
title: Lift en Scala ontwikkeling met Netbeans 6.9M1
date: 2010-04-08 20:49:05 +02:00
---

Na een aantal weken geleden een [Scala](http://www.scala-lang.org/ "Scala")-workshop van [Jan-Willem Tulp](http://www.janwillemtulp.com/ "Jan-Willem Tulp") en [Martin van Amersfoorth](http://www.twitter.com/mamersfo "@mamersfo on Twitter") heb mogen bijwonen ben ik in de avonduurtjes regelmatig aan de slag gegaan met deze (voor mij) nieuwe programmeertaal. Vooralsnog bevalt Scala erg goed en ik hoop dan ook dat ik de taal in de toekomst voor een “echt” project kan inzetten.

Tegenwoordig zijn het gros van de voorgenoemde “echte” projecten webapplicaties. Na wat zoekwerk blijkt het [Lift-framework](http://liftweb.net/ "Lift Framework") de de facto standaard te zijn voor het ontwikkelen van webapplicaties in Scala. Doordat ik privé over het algemeen de aller-, aller-, allernieuwste versie wil gebruiken van applicaties draai ik dan ook al een tijdje de eerste milestone release van mijn favoriete Java IDE, [Netbeans](http://www.netbeans.org/ "Netbeans"). Helaas brengt deze keuze een wirwar van afhankelijkheden met zich mee. De Scala-integratie in Netbeans 6.9M1 vereist Scala 2.8 en stabiele Lift-versies bieden geen Scala 2.8 ondersteuning. Help!

Gelukkig valt het allemaal wel mee om de boel aan het draaien te krijgen. Helaas heeft het me wel wat zoek- en sprokkelwerk gekost. Dat wil ik jullie middels dit artikel besparen.

Netbeans heeft sinds de 6.9M1 versie een officiële Scala-plugin aan boord. Deze is gemakkelijk te installeren met behulp van de  ingebouwde pluginmanager. Nadat dat is gebeurd kun je eigenlijk gewoon aan de slag met Lift. Zoals gezegd ondersteunt de stabiele Liftversie, 1.0, Scala 2.8 niet. De aanstaande Liftversie, 1.1, ondersteunt Scala 2.8 ook niet. Rest ons de uiterst premature versie 2.0. Deze ondersteunt Scala 2.8 maar vereist wel het gebruik van enkele specifieke Maven archetypes. Deze archetypes zijn, voor de gemiddelde Scala- en Liftleek (lees: mij), lastig te vinden. Onderstaande Maven-commando lost dit echter op door netjes voor je een Lift 2.0 project met Scala 2.8 ondersteuning te initialiseren.

```
mvn archetype:generate -U -DarchetypeGroupId=net.liftweb 
-DarchetypeArtifactId=lift-archetype-blank 
-DarchetypeVersion=2.0-scala280-SNAPSHOT 
-DremoteRepositories=http://scala-tools.org/repo-snapshots 
-DgroupId=nl.dennislaumen
-DartifactId=voorbeeldproject
-Dversion=0.1
-DarchetypeRepository=http://scala-tools.org/repo-snapshots
```
Nogmaals, een bijzonder simpele oplossing. Maar oh zo lastig te vinden als je niet bekend bent in het Scala en Liftwereldje.
