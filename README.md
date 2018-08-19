# Convert-to-Religion-Mod
Mod for Europa Universalis IV that lets you convert to a religion by holding its holy sites.

This is my first mod for Europa Universalis IV.

Convert to Religion is a mod that lets you convert to other religions depending on whether you own holy sites of that religion.

I sat out to make the mod because I wanted a way to convert to other religions, especially the CK2 religions, that weren't just cheating or as some of the other mods do it by a simple click on a decision without any thought or drawbacks and which could be enacted at any time and point in the game.
Therefore I made it so that there are some requirements and a potentially big stability hit.
As I wanted to use the CK2 religions and wanted some requirements I quickly found out about the holy sites, which just made sense to me, that you would need to hold and own these sites to convert to that religion.
The more I dived into modding the more I wanted to do, and I discovered I could add province modifiers as an ingame visual representation of the holy sites.
This led me to adding standard permanent province modifiers via events for all holy sites, but those were changed with the recently introduced Province Triggered Modifiers, which I've swapped to using instead, some replacing the Religious Center province triggered modifier, as I have given all holy sites the same effect of having -5% local missionary strength if the province is of that religion, thus making it harder to convert away from the religion of a holy site.
Protestant and Reformed are triggered once they spawn and should get holy sites on the provinces which spawns Centers of Reformations, thus making it random each game.
When Sikh spawns, it spawns on a province based on certain criteria, which makes it partially random, and then randomly chooses 2 neighbouring provinces which also gets Sikh, which I made holy sites spawns on 2 of those 3.
For the Holy Sites themselves, I looked extensively at the CK2 Wiki and the Ck2 province conversion table which comes with the EU4 converter for CK2. Also used the CK2 province files as they list several holy sites in them and then the game (CK2) itself also. Also some Google.
I will also like to thank and credit Refumee's Holy Sites mod, which I have also borrowed a few holy sites from, especially the eastern religions.


Makes decisions available to be able to convert to a religion if you own holy sites of that religion:

Country Decision

Potential Requirements

The country:
	Owns at least 1 of the 5 holy site provinces OR own a province with the religion.
	Is not the same religion as the one you are trying to convert to.
	(In most cases) Is not The Papal State or the Holy Roman Empire.

Allow

The country:
	Is not at war.
	Is not a subject nation other than a tributary state.
	Stability at least 1.
	One of these:
		Both of these:
			If any of these countries or culture (varies depending on decision and religion), only need to own 3 Holy Sites.
			Owns 3 core provinces which is a holy site and have built either a temple (Tax Building 1) or cathedral (Tax Building 2) on the provinces.
		Owns all 5 core provinces which is a holy site and have built either a temple or cathedral on the provinces.

Effect

The country:
	Religion changes.
	Capital province changes religion.
	Change religion on any holy site provinces that has either a temple (Tax Building 1) or cathedral (Tax Building 2).
	If any of those countries or culture (varies depending on decision and religion), only need to own 3 Holy Sites.
		Stability -2.
	If not any of those countries or culture.
		Stability -4.
	Gets country modifier which makes it easier to convert and gives tolerance, for 10 years.


Compatibility:
Ironman NOT supported.
If I in an Update move a Holy Site (based on feedback), then I have made an event which you can trigger, after you have updated, from the console by typing "event ctr_events.99", which will remove all province modifiers and then the events that adds them will trigger again, thus adding the new updated province modifiers.
Extended Timeline NOT supported since I use religions variable names from vanilla and CK2 converter files. Also ET changes the map and adds provinces, which can lead to holy sites not being in the place that it should.
As I have made the holy sites use Religious Center mechanics (-5% Local Missionary Strength), I have removed (most of, if not all) the modifiers that is Religious Centers, thus there are a few events and such, which use it as a check such as, NOT = { has_province_modifier = religious_center }. One of the places this could have an impact is around and during the reformation wars. I would be pleased if you notice any suspicious behaviour that is not how it should work in an unmodded game around the reformation wars and report in in the bugreport section. Thanks.
This doesn't seem to impact the new religious center triggered province modifiers (2221 - Mashhad is one I've not removed), as those needs to be checked with, has_active_triggered_province_modifier, which I've not found any to use. In the code they Instead use, is_religious_center_province = yes, which checks the list for those in the scripted triggers province modifiers file, which I've not touched.


Future Plans:
Extended Timeline compatible version, updated with religions from ET such as Druidism, Germanic and Egyptian.
Keep it updated with the new map changes and patches of newer game versions.
Add more holy sites and decisions to convert to religions based on feedback.
	Anglican
	Totemist
	Animist
	Maybe some heresies
	and more...
Add more and better flavor-text to each holy site. Feedback would be appreciated.
Maybe add events that could make a holy site province flip to it's religion, thus spawning or reintroducing religions that have become unavailable. Maybe even spawn religious rebels via event or that sort-of idea, and if you don't want it flipped there would be an option for that or something like that. Or just religious rebels to get some of the lesser religions to get provinces.



List of holy sites:

Hellenic:
118 # Roma
146 # Athens
358 # Alexandria
148 # Thessaloniki
2296 # Biga

Zoroastrian:
4332 # Siraf
4327 # Jask
450 # Balkh
2206 # Urmia
2236 # Bojnord

Mayan:
842 # Peten
843 # Belize
846 # Yucatan
2632 # Xicallanco
2633 # Mani

Nahuatl:
852 # Mexico
854 # Sayultecas
2626 # Tulucan
2644 # Cholula
2647 # Cuetlaxtlan

Inti:
804 # Puno
806 # Nazca
808 # Cuzco
809 # Lima
812 # Chanchan

Romuva:
38 # Riga
47 # Stralsund
269 # Podlasia
4244 # Trubchevsk (Pochep)
1859 # Chelmno (Culm, Torun)

Slavic:
47 # Stralsund
256 # Plock
268 # Moldavia
280 # Kiev
2749 # Tikhvin

Suomenusko:
30 # Viborg
35 # Ösel
301 # Ryazan
305 # Perm
2749 # Tikhvin

Norse:
1 # Uppland
12 # Sjaelland
20 # Trondelag
96 # Zeeland
2972 # Paderborn

Tengri:
284 # Crimea
464 # Astrakhan
716 # Tannu Uriankhai
1076 # Kurgan
1970 # Syghnak

Fetishist:
344 # Marrakech
1132 # Timbuktu
2249 # Sibiridugu
2454 # Kairouan (El Kef)
2463 # Maaskar

Catholic:
85 # Köln
118 # Roma
206 # Galicia
235 # Kent
379 # Jerusalem

Orthodox:
148 # Thessaloniki (Mount Athos)
151 # Constantinople
318 # Sugla
379 # Jerusalem
2313 # Antioch

Monophysite:
358 # Alexandria
379 # Jerusalem
1227 # Tigre (Aksum)
2322 # Wadi Halfa
2313 # Antioch

Coptic:
358 # Alexandria
419 # Yerevan (Armenia)
1227 # Tigre (Aksum)
1234 # Qasr Ibrim
2313 # Antioch

Nestorian:
535 # Kochin
379 # Jerusalem
410 # Baghdad (Iraq-i-Arab)
428 # Rey
2308 # Urfa

Sunni:
225 # Cordoba
379 # Jerusalem
384 # Medina
385 # Mecca
410 # Baghdad (Iraq-i-Arab)

Shia:
379 # Jerusalem
382 # Damascus
384 # Medina
385 # Mecca
2311 # Samawah

Ibadi:
379 # Jerusalem
384 # Medina
385 # Mecca
403 # Nizwa
2463 # Maaskar

Jewish:
365 # Sinai
379 # Jerusalem
382 # Damascus
401 # Dhofar
414 # Hamadan

Mahayana:
558 # Patna
740 # Malwa
2077 # Margalla
1836 # Luoyang
613 # Dong Kinh

Theravada:
558 # Patna
740 # Malwa
2077 # Margalla
2099 # Kandy
609 # Angkor

Vajrayana:
558 # Patna
740 # Malwa
2077 # Margalla
677 # Lhasa
2133 # Dege

Hindu:
2095 # Varanasi
740 # Malwa
523 # Oudh
524 # Central Doab
2052 # Navanagar

Sikh:
2075 # Doaba
558 # Patna
1948 # Bidar
2 Random at spawn

Jain:
515 # Girnar
533 # Mysore
2053 # Patan
2067 # Gorwar
2096 # Damin

Zunist:
361 # Cairo
447 # Kandahar
451 # Kabulistan
506 # Multan
2236 # Bojnord

Confucian:
667 # Canton
679 # Chengdu
691 # Jinan
700 # Xi'an
1816 # Beijing

Shinto:
1018 # Izumo
1020 # Kyoto
1025 # Dewa
4359 # Ise
1029 # Kai

Protestant:
118 # Roma
379 # Jerusalem
3 Random Centers of Reformation

Reformed:
118 # Roma
379 # Jerusalem
3 Random Centers of Reformation

Bön: (no decision yet)
450 # Balkh
508 # Kashmir
677 # Lhasa
676 # Shigatse
710 # Hotan

Yazidi: (no decision yet)
379 # Jerusalem
385 # Mecca
411 # Mosul
2236 # Bojnord
4332 # Siraf

Manichean: (no decision yet)
379 # Jerusalem
410 # Baghdad
412 # Khuzestan
454 # Samarkand
2077 # Margalla



Feedback is always welcome.
