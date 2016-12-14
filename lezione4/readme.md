# Lezione 4

Martedì 13 dicembre 2016


### Task 1 

Nel catalogo del fondo (Calzolari 2005), controlliamo il numero della busta in cui è contenuta la lettera.

Sul documento originale controlliamo (10 minuti per ognuno):

- trascrizione
- cambi di pagina **< pb / >** (*page breaks*). **Attenzione!** si tratta di un elemento vuoto, quindi invece di avere un tag che apre e uno che chiude, ne avremo uno solo, con la barra dopo il nome. **Non** bisogna lasciare uno spazio bianco dopo l'elemento. Esempio:

		Non c'è più spazio su questo foglio quindi passo <pb/>al seguente.

- maiuscole, accenti e punteggiatura
- sottolineature, da codificare con l'elemento **< hi >** (*highlight*) e l'attributo **@type** con valore **"underlined"**. Esempio:

		La nostra <hi type="underlined">Rivista di filologia romanza</hi> sarà pubblicata a breve.

- nel caso in cui ci siano altri tipi di evidenziatura, codificarli con **< hi >** e l'attributo **@type** con valore "evidenziato" o altro più appropriato. Esempio:
		
		Ci sono due parole scritte più grandi: <hi type="grande">la nostra Rivista</hi>; poi il testo continua.

- lettere in apice, da codificare con **< hi >** e l'attributo **@type** con valore **"sup"**. Esempio:

		V<hi type="sup">a</hi> excelencia

- Correzioni, cancellature, aggiunte. Da segnare a parte.
- **Opzionale**: a capo **< lb >** (*line breaks*). **Non** bisogna lasciare uno spazio bianco dopo l'elemento. Esempio:

		Questa è la prima riga, <lb/>questa è la seconda, <lb/>poi la terza <lb/>etc.

#### _Gruppi:_

- Marta Carpicei, Daniele De Sanctis (Mussafia)
- Arianna Moretti, Martina Liaci, Francesca Iacuzzo (Meyer)
- Chiara Cocciarelli, Elisabetta De Vergori, Naomi Secci (Meyer)
- Martina d'Arcangelo, Sabrina Artale (Rajna)
- Arianna Calcagnini, Veronica Aurizi (Rajna)


### Task 2

Titolo: **La *Rivista di filologia romanza*, II (1875)**. 

Immagini: [uno](https://github.com/elespdn/laboratorio-monaci/raw/master/lezione4/images/rfr1875_1.png) e [due](https://github.com/elespdn/laboratorio-monaci/raw/master/lezione4/images/rfr1875_2.png). Copiare l'indice, un articolo sotto l'altro, indicando pagina (poi spazio *Tab*), autore (in maiuscolo), titolo.

Gruppo: Martina d'Arcangelo, Sabrina Artale, Daniele De Sanctis


### Task 3

Preparare una lista di persone (mittenti, destinatari, persone citate nelle lettere), utilizzando i dati raccolti nel gDoc (colonna *Metadata* e *altre info*)

Titolo: **Lista < persName >**. Inserire i nomi (nome e cognome) uno sotto l'altro.

Gruppo: Arianna Moretti, Martina Liaci, Francesca Iacuzzo

### Task 4

Preparare una lista di luoghi (luoghi di spedizione e destino, luoghi citati nelle lettere, luoghi di pubblicazione), utilizzando i dati raccolti nel gDoc (colonna *Metadata* e *altre info*).

Titolo: **Lista < placeName >**. Inserire i luoghi uno sotto l'altro.

Gruppo: Chiara Cocciarelli, Elisabetta De Vergori, Naomi Secci

### Task 5

Preparare una lista di istituzioni (biblioteche, istituti, università, scuole, etc.), utilizzando i dati raccolti nel gDoc (colonna *altre info*)

Titolo: **Lista < orgName >**. Inserire le istituzioni uno sotto l'altro.

Gruppo: Arianna Calcagnini, Veronica Aurizi, Marta Carpicei


---

Inserire tutto nel [googleDoc](https://docs.google.com/document/d/1a3w2RD7FX7GnFAryNSVaasCrAWV5DQj_bd0IqmV2Wt4/edit) (attenzione agli Stili, come Titolo, Intestazione 1, Intestazione 2, etc.; si accede alla Struttura del documento dal menu Strumenti).

---


## Metadata su persone, luoghi, organizzazioni

Nel < teiHeader > possiamo inserire metadata sulle persone, sui luoghi e sulle organizzazioni menzionati nel testo. Dove? Nel **< profileDesc>** (dopo il < fileDesc >). All'interno del < profileDesc > inseriamo **< particDesc >** per le persone e le organizzazioni, e **< settingDesc >** per i luoghi. 

Inseriamolo nella lettera. oXygen ci aiuterà: 

- cominciamo alla fine del < fileDesc > e apriamo la parentesi uncinata per avere dei suggerimenti, tra i quali sceglieremo < profileDesc >
- apriamo la parentesi uncinata al suo interno e tra i suggerimenti scegliamo < particDesc>
- procediamo inserendo gli elementi, aiutati dai suggerimenti di oXygen, fino ad ottenere la seguente struttura (i commenti non sono necessari):

		<teiHeader>
			<fileDesc> 
				<! -- ... -->
			</fileDesc>
			<profileDesc>
					<particDesc>
							<listPerson>
								<!-- ... lista delle persone ... -->
							</listPerson>
							<listOrg>	
								<!-- ... lista delle organizzazioni ... -->
							</listOrg>
					</particDesc>
					<settingDesc>
							<listPlace>
								<! -- ... lista dei luoghi ... -->
							</listPlace>
					</settingDesc>
			</profileDesc>
		</teiHeader>

Il seguente passo sarà inserire persone e luoghi, rispettivamente all'interno di < listPerson > e di < listPlace >.

### Codifica di persone

Ognuno codificherà una persona.

Per ogni persona moltissime informazioni possono essere codificate. Per maggiori informazioni, vd. [slides](http://tei.it.ox.ac.uk/Talks/2015-07-dhoxss/Talks/4-name-place-date.pdf) (in part. slides 14 e 15), dichiarazione dell'elemento [< person >](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-person.html), la sezione [Biographical and Prosopographical Data](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ND.html#NDPERS) nelle TEI Guidelines.

Nel nostro progetto, codificheremo per ogni persona: nome (nome e cognome), nascita, morte e identificatore. Esempio:

		<listPerson>
				<person xml:id="EM">
                       	<persName>
                            	<forename>Ernesto</forename>
                            	<surname>Monaci</surname>
                        </persName>
                        <birth when="1844-02-20">20 febbraio 1844,
	 							<placeName>Soriano nel Cimino</placeName>
                        </birth>
                        <death when="1918-05-01">1 maggio 1918,
 								<placeName>Roma</placeName>
                        </death>
                        <idno type="VIAF">64080350</idno>
                </person>
		</listPerson>

Da ricordare:

- ogni < person > deve avere un attributo **@xml:id**. Il valore dell'@xml:id non può cominciare con un numero. Per convenzione, diamo come valore le iniziali della persona.
- utilizzare l'attributo **@when** sugli elementi < birth > e < death >.
- assegnare un identificatore tramite un controllo di autorità per ogni persona, con l'elemento **< idno >**. In particolare, utilizziamo l'identificatore del VIAF. VIAF (Virtual International Authority File) è un catalogo per il controllo di autorità, gestito da diverse biblioteche del mondo. Per maggiorni informazioni, vd. <https://it.wikipedia.org/wiki/Controllo_di_autorit%C3%A0> e <http://www.oclc.org/viaf.en.html>


### Codifica di luoghi

Ognuno codificherà un luogo della lista.

Per ogni luogo tante informazioni possono essere inserite. Per maggiori informazioni, vd. [slides](http://tei.it.ox.ac.uk/Talks/2015-07-dhoxss/Talks/4-name-place-date.pdf) (in partic. slide 24), la dichiarazione dell'elemento [< place >](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-place.html), la sezione [Places](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ND.html#NDGEOG) nelle TEI Guidelines.

Nel nostro progetto per ogni luogo specificheremo: nome, paese, coordinate geografiche. Esempio:

		<listPlace>
				<place xml:id="roma">
                        <placeName>Roma</placeName>
                        <country>Italia</country>
                        <location>
                            	<geo>41.902783, 12.496366</geo>
                        </location>
                </place>
		</listPlace>

Da ricordare:

- ogni < place > deve avere un attributo **@xml:id**. Il valore dell'@xml:id non può cominciare con un numero. Per convenzione, diamo come valore il nome del posto, tutto minuscolo, se è molto lungo abbreviato
- per convenzione, inseriamo il nome del paese in italiano
- per una localizzazione senza equivoci dei nomi dei posti, utilizziamo le coordinate geografiche. Molti siti online permettono di conoscere le coordinate geografiche. Ad esempio: <http://www.latlong.net/>. Le coordinate andranno inserite nell'ordine 'latitudine, longitudine' (con virgola tra le due)
- l'elemento < geo > deve essere inserito all'interno dell'elemento < location >
- se il luogo da codificare è un paese, utilizzare direttamente < country > all'interno di < place >

## Collegare nomi e metadata

Ora che abbiamo codificato i nomi nel testo e inserito i metadati nell'Header, possiamo collegare l'uno all'altro.

Cerchiamo nel testo o nei metadati relativi alla corrispondenza un nome (di persona o di luogo) che abbiamo codificato. Inseriamo l'attributo **@ref** (basta aggiungere uno spazio alla fine del nome dell'elemento e oXygen ci suggerirà i possibili attributi, tra i quali scegliamo @ref), come nell'esempio:

	<persName ref="">Monaci</persName>

Se posizioniamo il cursore all'interno delle virgolette, appare la lista degli @xml:id tra i quali scegliere la persona o il luogo corrispondente. Il risultato è

	<persName ref="#EM">Monaci</persName>

Il valore dell'attributo @ref è un URI (Uniform Resource Identifier, tra i quali gli URL). Comincia con un **#** (asterisco) perché stiamo puntando a qualcosa che è all'interno del documento. Se i metadati fossero salvati in un altro documento (per esempio, 'listPerson.xml'), potremmo puntarvi inserendo il nome del documento e il punto specifico al suo interno, identificato tramite l'asterisco e l'@xml:id (per esempio, 'listPerson.xml#EM').

### Perché?
Collegare nomi e metadati permette di risalire alla forma standard del nome, compilare indici, fare ricerche e visualizzare informazioni attinenti.

## Condividere
Ognuno deve copiare la persona e il luogo codificato nel [google Doc](https://docs.google.com/document/d/1a3w2RD7FX7GnFAryNSVaasCrAWV5DQj_bd0IqmV2Wt4/edit).

## Compiti per martedì 20 dicembre

- Inserire i metadati degli altri luoghi e persone menzionati nella lettera e menzionati nella sezione dell'Header dedicata alla corrispondenza (< correspDesc >); si possono utilizzare i dati del google Doc, se qualcuno ha già codificato una persona o un luogo menzionato nella nostra lettera. 
- Collegare i nomi con i metadati.

### Esempio

Una lettera codificata si trova [qui](18731122-monaci-ascoli-nomi.xml).








