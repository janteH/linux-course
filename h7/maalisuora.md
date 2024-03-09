# Hei maailma

Loin kotihakemistooni kansion scripts, jonne loin uuden ajettavan skriptin python kielellä.

Ensin loin skriptitiedoston kansioon:

    micro heimaailma.py

Tiedoston alkuun määrittelen, millä kielellä se ajetaan: #!/usr/bin/python3

Ja seuraavaksi itse koodi:

    print("Hei maailma")

![maalisuora-00](./images/maalisuora-00.png)

Seuraavaksi testasin komentoa:

    python3 heimaailma.py

![maalisuora-01](./images/maalisuora-01.png)

# Komennot kaikkien ajettavaksi

Seuraavaksi tein uuden komennon bash kielellä, jonka asetin kaikkien käyttäjien ajettavaksi.

Ensin loin tiedoston:

    micro moi.sh

Määrittelin tiedoston alkuun, että se on tällä kertaa bash kielellä ajettava komento: #!/usr/bin/bash

Seuraavaksi kirjoitin tiedostoon sisältöä, joka tervehtii käyttäjää ja kertoo päivän.

![maalisuora-02](./images/maalisuora-02.png)

Seuraavaksi annoin execute oikeudet kaikille käyttäjille:

    chmod a+x moi.sh

Ja kopioin tiedoston lokaaliin kansioon:

    sudo cp moi.sh /usr/local/bin/

![maalisuora-03](./images/maalisuora-03.png)

Seuraavaksi navigoin lookaaliin kansioon tarkistamaan, että tiedosto on siellä. Tarkistin myös, että execute oikeus löytyy kaikilta. Tämän jälkeen testasin vielä komentoa kotikansiosta.

![maalisuora-04](./images/maalisuora-04.png)

# Arvioitavan tehtävän harjoitus

Tein soveltuvin osin Final Lab for Linux Palvelimet 2023 -kurssin arvioitavaa tehtävää.

- Skripti, joka tulostaa ajankohtaista tietoa; päivämäärä ja käyttäjän nimi
- Asennettu micro-editori ja sille jokin plugin
- Asennettu Apache-weppipalvelin
- Asennettu ssh-palvelin
- Asennettu omalle käyttäjälle Django kehitysympäristö

# Tyhjän Linuxin asentaminen lopputehtävää varten

Aloitin luomalla VirtualBoxiin uuden Linuxin arvioitavaa labratehtävää varten. Käytin samaa iso-imagea kuin aikaisemmissa asennuksissa ja tein täysin samanlaisen asennuksen kuin aikaisemmatkin koneet.

Nimesin koneen labrakoneeksi, muistia 4000MB, kiintolevy 50GB ja iso-imageksi juuri ladattu tiedosto. Type Linux ja versio Debian 64bit.

Tämän jälkeen starttasin koneen ja kävin graafisen asennuksen läpi.

Asensin koneelle päivitykset, Guest Additions ja tulimuurin.

###### Lähteet

Final Lab for Linux Palvelimet 2023. Terokarvinen.com Luettavissa: https://terokarvinen.com/2023/linux-palvelimet-2023-arvioitava-laboratorioharjoitus/?fromSearch=Arvioitava%20laboratorioharjoitus. Luettu: 9.3.2024.

How to Make Script Executable in Linux | chmod Command. Geeksforgeeks.org. Luettavissa: https://www.geeksforgeeks.org/chmod-command-linux/. Luettu: 9.3.2024.

Install Debian on Virtualbox - Updated 2023. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/. Luettu: 9.3.2024.

Linux Palvelimet 2024 alkukevät. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/. Luettu: 9.3.2024.

