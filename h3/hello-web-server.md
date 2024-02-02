## Name-based Virtual Host Support

- IP-pohjaiset virtuaaliset hostit käyttävät IP-osoitetta oikean virtuaalisen hostin määrittämiseen; Tällöin on oltava jokaiselle hostille oma IP osoite.
- Nimipohjaisessa virtuaalihostauksessa palvelin luottaa siihen, että asiakas ilmoittaa hostnamen osana HTTP-otsikkoa; Tätä tekniikkaa käyttämällä monet eri hostit voivat jakaa saman IP-osoitteen.
- DNS palvelinta käytetään yhdistämään hostname oikeaan IP-osoitteeseen

###### Lähde

Name-based Virtual Host Support. Apache.org. Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html Luettu: 30.1.2024.

## Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address

- Apachella voi olla useita verkkotunnuksia yhdessä IP-osoitteessa.
- Sivustoja voi lisätä tekemällä uuden nimipohjaisen virtual hostin.

###### Lähde

Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/ Luettu: 30.1.2024.

# Apache

## Apachen asennus

    sudo apt-get install apache2

Testaus:

    firefox "http://localhost" 

## Lokien analysointi

-
-

## Etusivu uusiksi

Luodaan uusi etusivu localhostille.

![hattu-2](./images/hattu-2.png)

Ensin uusi konffi tiedosto hattu.example.conf lisätään sites-availablen alle.

![hattu-3](./images/hattu-3.png)

![hattu-4](./images/hattu-4.png)

Lisätään konffitiedostoon tarvittavat tiedot:

    sudoedit hattu.example.conf

![hattu-1](./images/hattu-1.png)

Sitten lisätään kotihakemistoon määritelty paikka, johon index.html

![hattu-5](./images/hattu-5.png)

![hattu-6](./images/hattu-6.png)

![hattu-7](./images/hattu-7.png)

Sitten disabloidaan vanha sivu:

-

Ja enabloidaan uusi sivu:

-

## HTML5 -sivu

-
-

## Curl -komento

-
-

## GitHub Education

- Lähetetty hakemus Github Educationista 30.1.2024

## Nimipohjainen virtuaalipalvelu

-
-

## Kaksi eri sivua, sama osoite

-
-

##### Lähteet

