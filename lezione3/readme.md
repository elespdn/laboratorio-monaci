# Lezione 3
martedì 6 dicembre 2016

### Zotero 
- correzione
- import utilizzando plugin browser

### TEI Guidelines
- moduli, vd. slide [Intro TEI](https://elespdn.github.io/talks/labMonaci1-xmlTei.html#/17) della prima lezione
- schema, vd. tutorial su [ODD e Schema](https://github.com/elespdn/laboratorio-monaci/blob/master/lezione3/schema.md)
- guardiamo da vicino un elemento e la relativa documentazione: < author > [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-author.html)
	
### Intro a ..
- Meyer e Romania, vd. [scheda](https://github.com/elespdn/laboratorio-monaci/blob/master/lezione3/meyer_romania.md)
- Mussafia
- Rajna

### Codifica delle lettere: metadati e struttura del testo
- Vd. slides [*TEI for Correspondence*](https://drive.google.com/file/d/0B_1qUxvG29kvekJDZzQzZ1JZT0E/view) (DHOxSS 2016), di Sabine Seifert e Peter Stadler
- guardiamo da vicino un elemento e la relativa documentazione: < opener > [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-opener.html)

### Codifica delle lettere: named entities
Vd. slides [*Encoding Names, People, Places and
Dates*](http://tei.it.ox.ac.uk/Talks/2015-07-dhoxss/Talks/4-name-place-date.pdf)

- < persName >
- < placeName >
- < orgName >
- < date >

### Collezioni di edizioni digitali di lettere e strumenti per la visualizzazione
- [Early Modern Letters Online](http://emlo.bodleian.ox.ac.uk/home)
	- Esempio: [The Correspondence of Peter Paul Rubens ](http://emlo.bodleian.ox.ac.uk/blog/?catalogue=peter-paul-rubens)
	- Esempio: [Women's correspondences](http://emlo.bodleian.ox.ac.uk/forms/advanced?people_gend=female)
- [CorrespSearch: Search scholarly editions of letters](http://correspsearch.net/data.xql?l=en)
	- [Correspondence Metadata Interchange format](http://correspsearch.net/index.xql?id=participate_cmi-format)
- [Mapping the Republic of Letters](http://republicofletters.stanford.edu/index.html)
- [visual correspondence - Analysing Letters through Data Visualisation](http://letters.nialloleary.ie/)
- [Encyclopedia of Romantic Nationalism in Europe](http://romanticnationalism.net/viewer.p/21/59)

### Compiti per martedì 13 dicembre
#### 1
Codificare la propria lettera. Come?

- aprire oXygen
- creare un file TEIP5-All (come abbiamo visto nella lezione 2, istruzioni [qui](http://tei.it.ox.ac.uk/Talks/2015-07-dhoxss/oxygen-exercise/oxygen-exercise.xml))
- cancellare il paragrafo < p > all'interno del < body > e sostituirlo con un < div >
- all'interno del < div > incollare il testo della lettera
- codificare il testo, seguendo i materiali del corso e l'esempio di una [lettera  già codificata](https://github.com/elespdn/laboratorio-monaci/blob/master/lezione3/18731122-monaci-ascoli.xml)
- salvare il file
- copiarlo su una pennetta USB

#### 2
Controllare e se necessario cambiare le informazioni inserite nel [gDoc](https://docs.google.com/document/d/1a3w2RD7FX7GnFAryNSVaasCrAWV5DQj_bd0IqmV2Wt4/edit):

- sezione TAG, immaginando che esse siano le parole chiave che permetteranno la ricerca delle lettere in una base-dati o sito web
- sezione ALTRE INFO, inserendo persone, luoghi, istituzioni, titoli e date che si codificano

#### 3
Correggere entrate in Zotero, se necessario.
