# Oma Linux


## Tiivistelmä artikkelista "What is Free Software?"

- Ilmaisella sovelluksella tarkoitetaan kaikkien käytössä olevaa sovellusta
- Sovellus on kopioitavissa, ja sitä saa muokata ja muovata oman mielen mukaan
- Ilmainen sovellus on eri asia kuin vapaan lähdekoodin sovellus
- Artikkelin mukaan ilmaisella sovelluksella on neljä olennaista vapautta
    1. Vapaus suorittaa ohjelmaa kuten haluaa
    2. Pääsy lähdekoodiin, ja oikeus muokata sitä
    3. Vapaus jakaa kopioita auttaakseen muita
    4. Vapaus jakaa muokattua versiota edellyttäen myös lähdekoodin jakamista

  ###### Lähteet

  GNU Operating System. What is Free Software? Luettavissa: https://www.gnu.org/philosophy/free-sw.html Luettu: 20.01.2024.


## Linuxin asentaminen virtuaalikoneeseen

Tehtävässä on käytetty Debian Linuxia, ja asennettu se VirtualBoxiin.

Latasin Debian ISO imagen netistä. Tässä asennuksessa käytin versiota 12.4.0 xfce-työpöytäympäristöä. Latasin myös Oraclen VirtualBoxin ja asensin sen tietokoneelleni.

#### Virtuaalikoneen luominen VirtualBoxiin

Käynnistin VirtualBoxin sovelluksen latauksen jälkeen, ja valitsin ikkunasta "New"

![New](./images/new.png)
  
Nimesin virtuaalikoneen, valitsin ladatun ISO imagen, tyypiksi Linux, versio Debian 64-bit. Ja ruksi ruutuun skip unattanded installation.

![step1](./images/step1.png)

Lisäsin RAM muistia, muutaman prosessorin lisää, ja loin kovalevyn.

![step2](./images/step2.png)

![step3](./images/step3.png)

#### Virtuaalikoneen käynnistys ja asennus

Kohtasin tässä ongelmaan, ettei virtuaalikoneeni käynnisty. Sain virheeksi AMD-V is disabled in the BIOS (or by the host OS) (VERR_SVM_DISABLED).

Googletin ongelmaa, ja kokeilin luoda Virtuaalikoneen uudelleen vain yhdellä prosessorilla. <br>
Tämä ei kuitenkaan auttanut, joten päätin bootata koneeni BIOS:iin ja tutkia sieltä, pystynkö enabloimaan prosessorin asetuksista Secure Virtual Machine Moden

Löysin BIOS asetuksista SVM (Secure Virtual Machine Mode) asetuksen, jonka nyt sallin. <br>
Tämä ei kuitenkaan auttanut.
