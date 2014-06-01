--- 
layout: post
title: Java ME-ontwikkeling met 64-bits Ubuntu
date: 2010-06-01 17:56:50 +02:00
categories:
- java me
- ubuntu
---

Zoals sommigen van jullie [gisteren](http://twitter.com/DennisLaumen/status/15108375105 "@DennisLaumen's status") al op Twitter konden lezen, is het per ongeluk verplaatsen van de root van je Linux-systeem is niet aan te raden. Gelukkig ben ik door deze blunder geen data verloren (dankzij mijn vrij strikte backup-beleid en de begeleiding van [Pascal de Bruijn](http://blog.pcode.nl/ "PCode")). Wel was ik genoodzaakt mijn systeem opnieuw te installeren en dus ook mijn ontwikkelomgevingen opnieuw op te zetten. Een van deze omgevingen is gericht op de ontwikkeling van Java ME-applicaties in de NetBeans IDE. Normaliter werkt dit vlekkeloos op Ubuntu ware het niet dat ik per ongeluk de verkeerde CD-ROM van de stapel pakte en de 64-bits versie van Ubuntu installeerde. Helaas is er nog geen Java ME SDK met 64-bits ondersteuning. Dit hoeft echter geen probleem te zijn met onderstaande instructies.

Deze instructies zijn gebaseerd op de volgende softwarepakketten:

* [Ubuntu 10.04 Lucid Lynx 64-bit](http://www.ubuntu.com/desktop/get-ubuntu/download "Ubuntu Download")
* Sun Java 6 update 20
* [NetBeans 6.8 met Java ME-ondersteuning](http://netbeans.org/downloads/ "NetBeans Downloads")

De oplossing begint met het installeren van het Ubuntu-pakket _ia32-sun-java6-bin_. Dit bevat een aantal 32-bits pakketten welke nodig zijn voor de 32-bits Java ME SDK. Het is mogelijk dit pakket als standaard Java-installatie te specificeren maar dit betekent dat al onze Java-applicaties nu op 32-bits draaien. Omdat ik alle andere Java-code gewoon op 64-bits wil blijven draaien gaan we NetBeans en de Java ME SDK dusdanig configureren dat alleen zij gebruik maken van de 32-bits pakketten.

Ten eerste dienen we het standaard JDK-pad van NetBeans aan te passen. Dit is te vinden in het bestand _$NETBEANS_HOME/etc/netbeans.conf_ waarbij _$NETBEANS_HOME_ je NetBeans-installatiemap is. Wijzig hier de variabele _netbeans_jdkhome_ naar het pad van het zojuist geinstalleerde pakket. In mijn geval ziet dit er als volgt uit:

``netbeans_jdkhome="/usr/lib/jvm/ia32-java-6-sun"``

Vervolgens dienen we de Java ME-emulator te vertellen waar we deze 32-bits variant kunnen vinden. Dit doen we door het bestand _$NETBEANS_HOME/mobility8/WTK2.5.2/bin/emulator_ aan te passen. Verander hier de variabele _javapathtowtk_ als volgt:

``javapathtowtk=/usr/lib/jvm/ia32-java-6-sun/bin/``

Nu kun je aan de slag met Java ME op je 64-bits Ubuntu-installatie! Bij mij werkt bovenstaande oplossing vlekkeloos. Diverse fora afstruinende naar een oplossing kwam ik echter veel mensen tegen bij wie bovenstaande oplossing slechts gedeeltelijk werkte (met name debuggen werkte regelmatig niet). Tevens dient vermeld te worden dat NetBeans nu altijd de 32-bits variant gebruikt. Wil je NetBeans voor meer dingen gebruiken als Java ME-ontwikkeling is het verstandig een tweede NetBeans-installatie te gebruiken voor bovenstaande handelingen. Succes!
