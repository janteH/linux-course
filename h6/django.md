### Tiivistelmä artikkeleista

- Virtual enviromentin asennus
- Uuden virtual envin asennus pythonin kanssa
- Pipin käyttö virtual envin kanssa
- Djangon asennus
- Django projektin luonti ja käynnistys
- Tuotantoasennuksessa käytetään mod_wsgitä yhdistämään python ja apache

###### Lähteet

- Karvinen 2021: Django 4 Instant Customer Database Tutorial. Luettavissa: https://terokarvinen.com/2022/django-instant-crm-tutorial/. Luettu: 1.3.2024.
- Karvinen 2021: Deploy Django 4 - Production Install. Luettavissa: https://terokarvinen.com/2022/deploy-django/. Luettu: 1.3.2024.

## Django testiasennus

Tein ensin kotihakemistooni "django" nimisen kansion, johon teen seuraavat asennukset.

Virtual envin asennus

    sudo apt-get install virtualenv -y

Luon uuden virtualenvin ja lataan sinne viimeisimmän version pythonista

    virtualenv --system-site-packages -p python3 env/

Tämä luo uuden kansion env/, jossa on uusimmat paketit tiedostossa lib/site-packages/.

![env-00](./images/env-00.png)

Nyt voidaan käyttää virtual enviä komennolla

    source env/bin/activate

Komentokehotteeseen pitäisi nyt ilmestyä (env) eteen.

![env-01](./images/env-01.png)

Seuraavaksi käytetään pip:iä asennuksissa. Pippiä ei tule käyttää ilman virtual enviä eikä sudon kanssa.

![env-02](./images/env-02.png)

Luodaan django kansioon tiedosto requirements.txt, johon kirjoitetaan "django". (tässä on tärkeää varmistaa, että django on kirjoitettu oikein)

![env-03](./images/env-03.png)

Sitten asennetaan pipillä django käyttäen juuri luotua tekstitiedostoa

    pip install -r requirements.txt

![env-04](./images/env-04.png)

Tarkistus vielä komennolla, joka kertoo meille djangon versionumeron

    django-admin --version

![env-05](./images/env-05.png)

### Django projektin luonti

Luodaan projekti nimeltä "jahaa" (Tämä on testi projekti eikä julkiseen internettiin koskaan julkaistava)

    django-admin startproject jahaa

Mennään juuri luotuun projektikansioon, josta se käynnistetään

    cd jahaa

![env-06](./images/env-06.png)

Käynnistys komennolla

    ./manage.py runserver

![env-07](./images/env-07.png)

Projekti on nyt käynnissä local osoitteessa http://127.0.0.1:8000

Sivun pitäisi nyt näyttää tältä

![env-08](./images/env-08.png)

### Admin interface

(projekti ei ole käynnissä seuraavien toimenpiteiden aikana)

Tietokannan päivitys

    ./manage.py makemigrations
    ./manage.py migrate

Lataan ensin salasana generaattorin, jolla luon salasanan uudelle käyttäjälle

    sudo apt-get install pwgen
    pwgen -s 20 1 # randomize a password

Käyttäjän lisäys

    ./manage.py createsuperuser

Täytän pyydetyt tiedot, ja käyttäjä on nyt luotu.

Projektin käynnistys takaisin päälle

    ./manage.py runserver

Nyt voimme kokeilla kirjautua osoitteeseen http://127.0.0.1:8000/admin/

![admin-00](./images/admin-00.png)

Lisätään vielä peruskäyttäjä admin paneelin kautta, ja kokeillaan kirjautua sillä sisään. Käyttäjälle lisätty "staff" oikeudet, ja "view" ja "add" oikeudet. 

Kirjautuminen testattu ja todettu onnistuneeksi.

### Customer Database

(projekti ei ole käynnissä seuraavien toimenpiteiden aikana)

Luodaan uusi kansio "crm" sovelluksellemme

    ./manage.py startapp crm

Lisätään sovellus listaan

    micro jahaa/settings.py

Asetus tiedostossa lisätään siis 'crm' listaan kuvan mukaisesti

![crm-00](./images/crm-00.png)

Lisätään muutama malli. Django voi luoda malleista automaattisesti tietokantoja, järjestelmänvalvojan näkymiä tai jopa lomakkeita.

    micro crm/models.py

Lisätään tähän:

    from django.db import models

    class Customer(models.Model):
       name = models.CharField(max_length=300)

![crm-01](./images/crm-01.png)

Asiakasluokka luo tietokantaan "asiakas" -taulukon "nimi"-sarakkeella.

    ./manage.py makemigrations
    ./manage.py migrate

![crm-02](./images/crm-02.png)

Nähdäksemme uuden tietokantaamme admin/-sivulla, meidän on rekisteröitävä se

    micro crm/admin.py

Tähän tiedostoon:

    from django.contrib import admin
    from . import models
    
    admin.site.register(models.Customer)

![crm-03](./images/crm-03.png)

Projektin käynnistys

    ./manage.py runserver

Sivulla pitäisi nyt näkyä CRM valikko

![crm-04](./images/crm-04.png)

Lisätään muutama asiakas "Customers" alle. Lista näyttää nyt "Customer object" listassa mutta muokataan crm/models.py tiedostoa siten, että saadaan listaan näkyviin asiakkaiden nimet.

![crm-05](./images/crm-05.png)

(projekti ei ole käynnissä seuraavien toimenpiteiden aikana)

    micro crm/models.py

Lisätään tiedostoon

    def __str__(self):
        return self.name

Tiedosto näyttää nyt tältä:

![crm-06](./images/crm-06.png)

Projekti käyntiin ja testaus admin sivulla

![crm-07](./images/crm-07.png)

## Django tuotannossa














###### Lähteet

Deploy Django 4 - Production Install. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2022/deploy-django/?fromSearch=django. Luettu: 1.3.2024.

Django 4 Instant Customer Database Tutorial. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2022/django-instant-crm-tutorial/. Luettu: 1.3.2024.

Linux Palvelimet 2024 alkukevät. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/. Luettu: 1.3.2024.
