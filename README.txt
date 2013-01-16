RAKENNUS OPTIMOINTIA

Tiedosto ja koodikielenä englanti, mutta dokumentaatioon suomea!


ONGELMA
Ongelma on tuttu Anno nimisessä pelissä, missä on rakennettava mahdollisimman optimaalisesti. Rakennuksina ovat varastot ja tuotantolaitokset. Tuotantolaitoksilla voi olla myös alirakenneuksia, jotka on kaikki rakennettava kyseisen tuotantolaitoksen läheisyyteen. Ainoastaan tuotantolaitokseen on oltava tie varastosta. Kulmiin rakennettu tie ei yhdistä laitoksia toisiinsa. Kuinka voidaan rakentaa tehokkaasti siten, että matkaa on mahdollisimman vähän tuotantolaitoksista varastoihin?


TAVOITTEET
Tarkoitus ei ole täydellisesti simuloida pelimaailmaa, koska rakennuksia on valtavasti. Kuitenkin tarkoitus on, että kun ohjelma on valmis, olisi pelimaailman rakennuksia helppo lisätä tarvitsematta muuttaa koodin tärkeimpiä osia. Ohjelmaan riittää, että on vain yksi varasto ja ennalta määrätty määrä tuotantolaitoksia.


BONUKSET
Jos aikaa ja innostusta riittää, lisätään alirakennuksia tuotantolaitoksille ja annetaan käyttäjälle mahdollisuus määrätä myös varastojen määrä. Varastojen määrä voi lisätä kohtuuttomasti laskentaa, koska näiden sijainti toisiinsa nähden lisää erilaisia mahdollisuuksia. 


--------------------------------------------------------------------------------
RAPORTIT


1601
Esimerkki  pelimaailmasta:

V = varasto
-, | = tie
1, 2, 3, 4 = erilaisia tuotantolaitoksia
        
    VVVV11
    VVVV1144
    VVVV--44
       2233
       2233

mutta huomataan, että parempi olisi:

     44 33
     44|33
    VVVV
    VVVV
    VVVV
     22|11
     22 11

koska nyt jokaisella laitoksella on oikeasti yksi askel matkaa varastolle, kun taas edellisessä tuotantovarastolla 3 ja 4 on kahden palan matka. Matkojen pituutta ei voidakaan laskea teiden määrästä, vaan askelten määrästä miten paljon tuotantolaitoksilta kestää aikaa tuoda valmis tuote varastoon. Ensimmäisessä esimerkissä ensimmäisestä tiestä, joka rakennettiin varastosta, on matkaa yksi askel, mutta ensimmäistä tietä jatkavalla seuraavalla tiepalalla on jo kahden askeleen matka. Jos on löydetty jo joku tie, voidaan olla käymättä sellaisia vaihtoehtoja läpi, jotka tuottavat enemmän askelia.

Parasta olisi lähteä tien rakentamisella ja antaa jokaiselle tielle painoarvo miten pitkä matka kyseisestä tiepalasta on varastolle. Kun sopiva rakennus löytyy, ei enää jatketa ratkaisun löytämistä niissä vaihtoehdoissa, joissa teiden painoarvojen summa on korkeampi kuin jo löydetty ratkaisu. Tallennetaan vain ratkaisu, jossa on pienin mahdollinen painoarvo tai jossa painoarvo on sama, koska voi olla kiintoisaa nähdä myös muita ratkaisuja.

Jos alirakennukset otetaan mukaan se aiheuttaa uuden ehdon. Kaikkien alirakennukset on rakennettava, mutta jos jos se ei ole mahdollista - eli tilaa ei ole - hylätään ratkaisuehdotus. Alirakennukset luovat taas uuden kokeilupuun.
