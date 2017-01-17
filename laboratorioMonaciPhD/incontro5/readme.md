# Incontro 5

Mercoledì 18 gennaio 2017

## Correzione lettere

## App Tei Publisher Laboratorio Monaci

## Muoversi all'interno di un documento XML: XPATH

- [Tutorial XPATH](http://www.w3schools.com/xml/xpath_intro.asp), da *w3schools.com*
- Le espressioni XPATH possono essere testate nella finestra 'XPath 2.0' (dove c'è scritto Execute XPath on current file) in alto a sinistra in oXygen. I risultati saranno evidenziati nel documento e appariranno in una finestra in basso. Alcuni esempi:
	- Per selezionare tutto il < teiHeader >, scrivere
	
			/TEI/teiHeader

	- Per selezionare tutto il < body >, scrivere
	
			/TEI/text/body

	- Per selezionare il < opener >, scrivere
	
			/TEI/text/body/div/opener

	- Per selezionare tutti i < persName > nella lettera, scrivere 
				
			//persName


---


## Trascrizioni e interventi editoriali

Nella codifica della trascrizione di un documento, potremmo essere interessati a segnalare aggiunte, cancellature, note a margine, etc.; e in alcuni casi potremmo voler intervenire, normalizzando l'ortografia, correggendo un errore evidente, etc.

I principali elementi che servono per questo tipo di codifica sono presentati, con esempi, nelle slides [*Transcription and Editorial Interventions*](http://tei.it.ox.ac.uk/Talks/2015-07-dhoxss/Talks/3-transcription-and-criticapp.pdf). Qui sotto si trova un riepilogo degli stessi elementi.

### *Add*, *Del* e *Subst*: aggiunte e cancellature nell'originale

Se nel documento originale sono presenti aggiunte o cancellature, possiamo codificarle utilizzando gli elementi < add > e < del >.

- **< add >**, vd. [descrizione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-add.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-add.html) nelle Guidelines
- **< del >**, vd. [descrizione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-del.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-del.html) nelle Guidelines

Quando la cancellatura e l'aggiunta sono contestuali, ovvero quando ad una cancellatura corrisponde un'aggiunta, i due elementi possono essere raccolti all'interno dell'elemento < subst >

- **< subst >**, vd. [descrizione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-subst.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-subst.html) nelle Guidelines 

### *Choice*: scioglimento delle abbreviazioni, correzioni e normalizzazioni dell'editore

L'elemento **< choice >** si utilizza in tutti quei casi nei quali abbiamo due forme concorrenti che vogliamo visualizzare, non insieme, ma o una o l'altra. Ad esempio, nel caso di un'abbreviazione, vorremmo visualizzare la forma abbreviata o la forma sciolta (magari la forma abbreviata direttamente nel testo e la forma sciolta che appare in un rettangolo quando ci passiamo sopra con il mouse, o in una nota).

Le abbreviazioni possono essere codificate tramite l'elemento < abbr >. Se si vuole indicare anche lo scioglimento dell'abbreviazione, si utilizza l'elemento < expan > e i due elementi (< abbr > e < expan >) vanno racchiusi nell'elemento < choice >. 

- **< abbr >**, vd. [dichiarazione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-abbr.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-abbr.html) nelle Guidelines
- **< expan >**, vd. [dichiarazione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-expan.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-expan.html) nelle Guidelines
- **< choice >**, vd. [dichiarazione](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-choice.html) e [esempi](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/examples-choice.html) nelle Guidelines

Nel caso di un errore evidente, esso può essere segnalato con l'elemento < sic > e corretto con l'elemento < corr >. Quando sono presenti entrambi, andranno racchiusi nell'elemento < choice >.

- **< sic >** e **< corr >**. Cercare gli elementi nelle Guidelines: <http://www.tei-c.org/release/doc/tei-p5-doc/en/html/> (utilizzare il campo di ricerca in alto a sinistra!). Una volta che siete all'interno della dichiarazione dell'elemento, ad esempio [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-sic.html), scorrete la pagina per arrivare agli esempi. Per vedere altri esempi, cliccate su *Show all*.

Nel caso in cui volessimo modernizzare l'ortografia o fare un altro intervento di normalizzazione, si possono usare gli elementi < orig >, per codificare la forma originale, e  < reg >, per quella normalizzata. Nelle nostre lettere, ad esempio, si trova la forma *Jeri* per *Ieri*. Se decidessimo di modernizzarla, potremmo codificare nel modo seguente:

	<choice><orig>Jeri</orig><reg>Ieri</reg></choice> ho letto il tuo libro ...

- **< orig >** e **< reg >**. Cercare gli elementi nelle Guidelines: <http://www.tei-c.org/release/doc/tei-p5-doc/en/html/> (utilizzare il campo di ricerca in alto a sinistra!). Una volta che siete all'interno della dichiarazione dell'elemento, ad esempio [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-reg.html), scorrete la pagina per arrivare agli esempi. Per vedere altri esempi, cliccate su *Show all*.


---

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

---

## Separazione contenuto e visualizzazione
Torniamo su un concetto chiave, menzionato nella prima lezione: la separazione tra contenuto e visualizzazione.

Editori di testo come Word sono di tipo **WYSIWYG** (*what you see is what you get*), ovvero nella gestione del testo all'interno dell'editore decidiamo come quel testo sarà presentato, ad esempio cambiando la grandezza del font, mettendo una parola in corsivo, aggiungendo spazi bianchi.

Quando si codifica un testo in XML ci concentriamo invece nel descrivere la struttura e le caratteristiche rilevanti del testo (***descriptive markup***), che potranno poi essere visualizzate in modi diversi. Ad esempio, una volta codificata una parola come 'correzione' (tramite l'elemento < corr >), potrò decidere di visualizzarla (attraverso un ulteriore passaggio di elaborazione) al lato del testo, sopra il testo, con un determinato colore, etc.

Da ricordare:

- I testi codificati sono **indipendenti** dalla loro "renderizzazione" (*rendition*), ovvero dalla loro trasformazione in una versione da visualizzare
- gli stili grafici sono applicati al testo codificato in un passaggio successivo di **elaborazione**
- a partire dallo stesso documento (TEI = .xml) possono essere prodotti documenti in **diversi formati** (es. .pdf, .txt, .csv, .doc, .html).


### Da XML-TEI a ... qualcosa di più presentabile

Come detto, la separazione tra contenuto e visualizzazione prevede che
- nel file TEI (.XML) sia contenuto il testo con il markup
- attraverso un'ulteriore elaborazione si passa ad un output più leggibile.

In oXygen, abbiamo visto come produrre un documento .html (ovvero una pagina web) a partire dal documento .xml 

- Configure Transformation Scenario (icona chiave inglese sulla barra, oppure menu Document > Transformation)
- Selezionare l'opzione desiderata
- Apply associated

Cosa c'è dietro, che rende possibile questa trasformazione?

Nel caso di oXygen, ci sono dei fogli di stile XSLT, che contengono istruzioni su come processare i singoli elementi della codifica TEI. Nel foglio di stile .xslt sarà specificato, ad esempio, che l'elemento < title > diventerà un elemento < h1 > (*heading 1*) nel documento .html di output; o che l'elemento < corr > sarà trasformato nell'elemento < span > (generica porzione di testo) con stile associato *color:red*.

La Text Encoding Initiative (TEI) mette a disposizione numerosi fogli di stile di tipo XSLT, per trasformare i documenti .xml in altri formati. Un elenco si trova nell'applicazione [OxGarage](http://www.tei-c.org/oxgarage/).

I fogli di stile in OxGarage permettono di trasformare un documento .xml in diversi formati. Se ciò che ci interessa è esclusivamente produrre un documento da visualizzare nel web, sono disponibili altre soluzioni promosse dalla TEI. Ad esempio

- [TEI Boilerplate](http://dcl.ils.indiana.edu/teibp/)
- [CETEIcean](http://teic.github.io/CETEIcean/)
- [TEI Publisher](http://tei-publisher.com/index.html)

---

## Criteri di trascrizione e di codifica


