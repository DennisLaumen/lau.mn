--- 
layout: post
title: Google Maps-navigatie op ADP1
date: 2010-06-21 20:38:28 +02:00
categories:
- google maps
- android
---

Sinds een week of twee is Google Maps-navigatie beschikbaar voor Nederlandse Android-telefoons. Als eigenaar van de Android Developer Phone, de ADP1, wil ik natuurlijk gebruik maken van deze functionaliteit. Helaas wordt de ADP1 niet actief ondersteund door Google en HTC als consumententoestel. Als er vervolgens een fout in de software sluipt die (niet opgelost wordt en) tot gevolg heeft dat het onmogelijk is om Google Maps te updaten naar een nieuwere versie zit je als gebruiker met de spreekwoordelijke gebakken peren. Zonder te updaten naar deze nieuwe versie is de navigatiefunctionaliteit niet te gebruiken dus zit er maar een ding op, klooien!

De oplossing voor dit probleem is relatief simpel. We hoeven slechts de geïnstalleerde versie van Google Maps volledig te verwijderen van de telefoon om vervolgens via de Android Market Google Maps opnieuw te installeren. De ADP1 is niet voor niets een ontwikkelaarstoestel en dus beginnen we met [het installeren van de Android SDK][1]. Zodra dit gebeurd is kunnen we aan de slag! 

1. Zorg er om te beginnen voor dat je met de _Android Debug Bridge_ als _root_ kunt communiceren met je toestel. `adb root`
2. Vervolgens _mounten_ we de systeempartitie opnieuw zodat we bestanden van deze partitie kunnen verwijderen in de volgende stappen. `adb remount`
3. Sla een reservekopie op van het installatiepakket van de geïnstalleerde Google Maps-versie. Mocht er iets mis gaan kun je dit bestand altijd gebruiken om de oude versie opnieuw te installeren. `adb pull /system/app/Maps.apk ~/Maps.apk`
4. Verwijder vervolgens het installatiepakket van de geïnstalleerde Google Maps-versie. `adb shell rm /system/app/Maps.apk`
5. Deïnstalleer vervolgens de Google Maps-applicatie van het systeem. `adb uninstall com.google.android.apps.maps`

Ga vervolgens op je toestel naar de Android Market en installeer Google Maps et voilà, je draait nu de nieuwste versie met navigatie-ondersteuning! Google Maps is te installeren met behulp van onderstaande _QR-code_.

[![Google Maps QR-code](/public/images/2010/06/21/googlemapsqrcode.png)][2]

[1]: http://developer.android.com/sdk/installing.html "Installing the Android SDK"
[2]: market://search?q=pname:com.google.android.apps.maps "Google Maps on Android Market"
  
