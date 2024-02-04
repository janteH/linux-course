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

Logit löytyvät /var/log/apache2

![logs-1](./images/logs-1.png)

Logeja voi tarkastella komennolla:

    tail /var/log/apache2/error.log

![logs-2](./images/logs-2.png)

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

    sudo a2dissite jante.example.conf

![hattu-8](./images/hattu-8.png)

Apachen uudelleen käynnistys:

    sudo systemctl restart apache2

Ja enabloidaan uusi sivu:

    sudo a2ensite hattu.example.conf

![hattu-9](./images/hattu-9.png)

ja apachen uudelleen käynnistys

    sudo systemctl restart apache2

## HTML5 -sivu

Muokataan sivusta validi HTML sivu ja tarkisteaan se validatorilla (https://validator.w3.org/)

![hattu-10](./images/hattu-10.png)

Validator huomautti kielen määrityksestä, joten lisäsin tämän vielä html tagiin.

![hattu-11](./images/hattu-11.png)

## Curl -komento

#### curl

Komento palauttaa webbisivun HTML-sisällön.

![curl-1](./images/curl-1.png)

## GitHub Education

- Lähetetty hakemus Github Educationista 30.1.2024
- Hyväksytty hakemus 2.2.2024

##### Lähteet

Terokarvinen.com. Linux Palvelimet 2024 alkukevät. Luettavissa: https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/ Luettu: 04.02.2024
