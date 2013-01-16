RAKENNUS OPTIMOINTIA

Tiedosto ja koodikielenä englanti, mutta dokumentaatioon suomea!


ONGELMA
Ongelma on tuttu Anno nimisessä pelissä, jossa on rakennettava mahdollisimman optimaalisesti Rakennuksina ovat varastot ja tuotantolaitos, jolla voi olla myös alirakennuksia. Nämä alirakennukset voidaan rakentaa vain tietyn matkan päähän omasta tuotantolaitoksestaan. Ainoastaan tuotantolaitokseen on oltava tie varastosta. Kulmiin rakennettu tie ei yhdistä laitoksia toisiinsa.


TAVOITTEET
Tarkoitus ei ole täydellisesti simuloida pelimaailmaa, koska rakennuksia on valtavasti. Kuitenkin tarkoitus on, että kun ohjelma on valmis, olisi pelimaailman rakennuksia helppo lisätä tarvitsematta muuttaa koodin tärkeimpiä osia. Ohjelmaan riittää, että on vain yksi varasto ja ennalta määrätty määrä tuotantolaitoksia.


BONUKSET
Jos aikaa ja innostusta riittää, lisätään alirakennuksia tuotantolaitoksille ja annetaan käyttäjälle mahdollisuus määrätä myös varastojen määrä. Varastojen määrä voi lisätä kohtuuttomasti laskentaa, koska näiden sijainti toisiinsa nähden lisää erilaisia mahdollisuuksia. Myös hyvän optimoinnin määrittely voidaan tehdä paremmaksi. Nythän hyvä on perusteltu teiden määrällä, mutta siihen vaikuttaa myös etäisyys. Voidaan rakentaa kahden palan tie yhteen suuntaan ja sen varrelle neljä tuotantolaitosta, mutta voidaan myös rakentaa varastosta yksi pala jokaiseen eri suuntaan ja niiden varrelle tuotantolaitokset:

V = varasto
-, | = tie
1, 2, 3, 4 = tuotantolaitos
        
    VVVV11
    VVVV1144
    VVVV--44
       2233
       2233

parempi olisi:

     44 33
     44|33
    VVVV
    VVVV
    VVVV
     22|11
     22 11

koska nyt jokaisella laitoksella on oikeasti yksi askel matkaa varastolle, kun taas edellisessä tuotantovarastolla 3 ja 4 on kahden palan matka. Tätä ajatusta voidaan oikeastaan käyttää optimointiin, että jos lasketaan matkattavan tien yhteismäärä, lopetetaan niiden mahdollisuuksien laskeminen, jotka tuottavat tuotantolaitoksille pitempiä reittejä silloinkin vaikka tiepaljoa on yhtä paljon. Ensimmäisessä tiessä on laitoksesta mahdollisia reittejä matkaa 1 ja 2, ja yhteensä 3, kun taas viimeisessä esimerkissä on mahdollisia matkoja vain 1 ja 1, eli yhteensä 2. Tällöin algoritmin pitäis hylätä ensimmäinen esimerkki ja tarjota viimeisintä.


ONGELMAN RATKAISU
Luultavasti paras olisi lähteä tien rakentamisesta. Ensin kokeilla yhdellä tiellä kaikki mahdollisuudet ja jokaiselle niille kokeillaan onko tuotantolaitoksia mahdollista rakentaa teiden varrelle. Kun mahdollisuus löytyy jatketaan erilaisten mahdollisuuksien kokeilemista vain sillä tiemäärällä. Isoimmista tiemääristä ei olla kiinnostuneita. Jos alirakennukset ovat mukana, kokeillaan saadaanko kaikki alirakennukset rakennettua, jos ei, niin hylätään ratkaisu. Tällä menetelmällä ei tarvita polkualgoritmeja, vaikka aluksi vaaikuttikin siltä, että ongelma nojaisi vahvasti niihin. Polkualgoritmia tarvitaan vain silloin, kun lasketaan polun pituutta myöhempää optimointia varten.
