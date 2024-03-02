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

### Admin interface & customer database








## Django tuotannossa








###### Lähteet

Deploy Django 4 - Production Install. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2022/deploy-django/?fromSearch=django. Luettu: 1.3.2024.

Django 4 Instant Customer Database Tutorial. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2022/django-instant-crm-tutorial/. Luettu: 1.3.2024.

Linux Palvelimet 2024 alkukevät. Terokarvinen.com. Luettavissa: https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/. Luettu: 1.3.2024.
