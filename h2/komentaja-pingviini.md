## Command line basics

- Liikkuminen kirjastossa
  - 'pwd' tulostaa kirjaston, jossa ollaan
  - 'ls' listaa tiedostot ja kansiot, jossa ollaan
  - 'cd' eli change directory. Voidaan käyttää eri tavoin kansiossa liikkumiseen 'cd ..' tai 'cd xyz/'
- 'less xyz.txt' näyttää tekstitiedoston (välilyönti ja "b" sivujen kelaus, "/" hakutoiminto, "q" lopetus)
- 'nano xyz.txt' avaa muokkaustilan tekstitiedostolle ohjelmassa nano
- 'mkdir xyz' tekee uuden kansion nimeltä xyz
- 'mv' komennolla voi liikutella tai nimetä tiedostoja uudelleen
  - 'mv vanhanimi uusinimi'
  - 'mv tiedosto uusisijainti/'
- 'cp' -komennolla voidaan kopioida tiedostoja tai kansioita
- 'rmdir tyhjäkansio' poistaa kansion, joka on tyhjä
- 'rm' komennolla voidaan poistaa tiedostoja ja parametrilla '-r' kansioita

## Micro-editorin asennus

- Avataan komentokehote ja asennetaan Micro -editori sovellus komennolla

      sudo apt-get -y install micro

## Raudan testaus

Asennetaan lshw

    sudo apt-get install lshw -y

Listataan koneen rauta komennolla

    sudo lshw -short -sanitize

![lshw-1](./images/lshw-1.png)

## Apt. Ohjelmien asennus

Ohjelmien asennus apt-get -komennolla

Jos halutaan asentaa monta ohjelmaa, voi ne laittaa komentoon peräkkäin. Esimerkiksi tässä asennetaan ohjelmat screen, irssi ja vim

    sudo apt-get install screen irssi vim -y

![apt-get](./images/apt-get.png)

#### screen

Screenillä pystyy käynnistämään ja käyttämään useita shell-istuntoja yhdestä ssh-istunnosta. Käytännössä screeniin saa esimerkiksi irssin tai vaikka Minecraft serverin pyörimään taustalle.

Komennolla 'screen' saa ohjelman käyntiin. Näppäimillä ctrl+a ja ? näkee esimerkiksi eri näppäimien toiminnot.

![screen-1](./images/screen-1.png)

#### irssi

Modulaarinen tekstitilan chat ohjelma.

![irssi-1](./images/irssi-1.png)

Chat kanaville voi esimerkiksi liittyä komennolla: /j kanavannimi

#### vim

Tekstieditointi ohjelma.

![vim-1](./images/vim-1.png)

Vimissä tekstiä editoidaan komennolla 'i' <br>
Editointi tilasta pääsee "esc" -näppäimellä pois <br>
Tallennus tapahtuu komennolla ':w' <br>
Ja lopetus komennolla ':q' <br>

## FHS - Filesystem Hierarchy Standard

#### /

Root -kansio. Kaikki muut on tämän kansion alla.

Avataan komentokehote. 'pwd' -komento näyttää, että olemme käyttäjän kotikansiossa.

![fhs-1](./images/fhs-1.png)

Komennolla 'cd /' pääsemme suoraan "root" hakemistoon. 'pwd':llä vielä tarkistus.

![fhs-2](./images/fhs-2.png)

#### /home/

Kotihakemisto kaikkien käyttäjien kotihakemistoille.

'pwd':llä nähdään taas, että olemme käyttäjän kotihakemistossa. Mennään yksi hakemisto ylemmäksi komennolla 'cd ..'

Nyt olemme niin sanotusti kotien kotihakemistossa. Katsotaan vielä 'ls' -komennolla, että tässä kansiossa on käyttäjät. Tässä tapauksessa käyttäjiä on vain yksi.

![fhs-3](./images/fhs-3.png)

#### /home/jante/

#### /etc/

#### /media/

#### /var/log/

## Grep komento

-
-

## Pipe komento

-
-

## Tukki

-
-

###### Lähteet

freeCodeCamp.org https://www.freecodecamp.org/news/vim-beginners-guide/

Irssi.org https://irssi.org/New-users/ 

Linuxize.com https://linuxize.com/post/how-to-use-linux-screen/ 

Terokarvinen.com. https://terokarvinen.com/2020/command-line-basics-revisited/ 

Terokarvinen.com. https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/ 


