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

-
-
-

# Tyhjän Linuxin asentaminen lopputehtävää varten


###### Lähteet

How to Make Script Executable in Linux | chmod Command. Geeksforgeeks.org. Luettavissa: https://www.geeksforgeeks.org/chmod-command-linux/. Luettu: 9.3.2024.

Linux Palvelimet 2024 alkukevät. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/. Luettu: 9.3.2024.

