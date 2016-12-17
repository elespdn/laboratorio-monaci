# Lezione 5

martedì 20 dicembre 2016

- controllo originali
- codifica bibliografia
- visualizzazione XML-TEI

---

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

---

### Codifica della bibliografia e collegamento dei titoli nel testo

Nel testo della lettera ci sono riferimenti a libri, riviste, articoli e manoscritti. La bibliografia relativa alla lettera troverà posto in una sezione specifica del documento *.xml*. Una delle soluzioni possibili è inserire la bibliografia nel < back >, all'interno di un < div > con @type="bibl". Vediamolo:

- all'interno del < text >, dopo il < body >, inserire < back >
		
		<text>
			<body>
				<!-- qui dentro c'è un <div> con la lettera -->
			</body>
			<back></back>
		</text>

- all'interno del < back >, inseriamo un < div > con @type="bibl".
		
		<text>
			<body>
				<!-- qui dentro c'è un <div> con la lettera -->
			</body>
			<back>
				<div type="bibl"></div>
			</back>
		</text>

- all'interno del < div >, inseriamo un elemento < head >, all'interno del quale scriviamo Bibliografia, e un elemento < listBibl >.

		<back>
			<div type="bibl">
				<head>Bibliografia</head>
				<listBibl></listBibl>
			</div>
		</back>

All'interno di < listBibl > possiamo inserire la bibliografia vera e propria. 

- Se si tratta di riviste (Rivista di Filologia Romanza, Romania), si trovano già codificate nel [GoogleDoc](https://docs.google.com/document/d/1a3w2RD7FX7GnFAryNSVaasCrAWV5DQj_bd0IqmV2Wt4/edit#). Possiamo copiare e incollare quella che ci interessa. Ad esempio, se nella lettera si parla del primo fascicolo della Rivista di Filologia Romanza, la nostra sezione della bibliografia risulterà:

		<back>
            <div type="bibl">
                <head>Bibliografia</head>
                <listBibl>  
                    <bibl xml:id="RFR1-1">
                        <title level="j">Rivista di Filologia Romanza</title>
                        <date>1872</date>
                        <biblScope unit="volume">I</biblScope>
                        <biblScope unit="issue">I</biblScope>
                    </bibl>
				</listBibl>
            </div>
        </back>

- Se nella lettera sono menzionati libri, articoli o altre pubblicazioni. Possiamo utilizzare l'export di Zotero, per avere una versione XML-TEI della bibliografia relativa. Per prima cosa, assicurarsi che il titolo sia presente nella biblioteca Zotero. Poi, seguire le istruzioni del [tutorial Export Zotero](zotero_export.md), sezione Export in TEI. Una volta aperto il documento generato da Zotero, copiare tutto l'elemento < biblStruct > e ciò che contiene e incollarlo all'interno della < listBibl > del file di codifica della lettera.

**Nota**: < biblStruct > è un'alternativa, più ricca e strutturata, di < bibl >. Entrambe sono valide e possono coesistere all'interno di una lista di fonti bibliografiche, ovvero all'interno di < listBibl >. 

#### Collegamento tra il testo della lettera e la Bibliografia

Come già abbiamo visto nella scorsa lezione per [i nomi e i metadati](https://github.com/elespdn/laboratorio-monaci/tree/master/laboratorioMonaci2016/lezione4#collegare-nomi-e-metadata), sarà necessario collegare la menzione della bibliografia nel testo della lettera alla descrizione bibliografica.

Utilizziamo lo stesso procedimento usato per i nomi. All'elemento < title > si aggiunge un attributo @ref, che punta all'@xml:id della fonte bibliografica. Ad es.

	... della <title ref="#RFR">Rivista</title> preparo una notizia particolareggiata ...

dove '#RFR' si riferisce all'elemento < bibl > con #xml:id="RFR" codificato nel < back >:

        <back>
            <div type="bibl">
                <head>Bibliografia</head>
                <listBibl>  
                    <bibl xml:id="RFR">
                        <title level="j">Rivista di Filologia Romanza</title>
                        <editor><persName ref="#EM">Ernesto Monaci</persName></editor>
                        <editor><persName ref="#EMS">Edmund Stengel</persName></editor>
                        <editor><persName ref="#LM">Luigi Manzoni</persName></editor>
                        <publisher>P. Galeati</publisher>
                        <pubPlace>Imola</pubPlace>
                        <date from="1872" to="1876">Dal 1872 al 1876</date>
                    </bibl>     
                </listBibl>
            </div>
        </back>
 

### Esempio

Una lettera codificata si trova [qui](18731122monaci_ascoli.xml).

---


### Separazione contenuto e visualizzazione
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

La Text Encoding Initiative (TEI) mette a disposizione numerosi fogli di stile di tipo XSLT, per trasformare i documenti .xml in altri formati. Un elenco si trova nella repository [OxGarage](http://www.tei-c.org/oxgarage/).

I fogli di stile in OxGarage permettono di trasformare un documento .xml in diversi formati. Se ciò che ci interessa è esclusivamente produrre un documento da visualizzare nel web, sono disponibili altre soluzioni promosse dalla TEI. Ad esempio

- [TEI Boilerplate](http://dcl.ils.indiana.edu/teibp/)
- [CETEIcean](http://teic.github.io/CETEIcean/)
- [TEI Publisher](http://tei-publisher.com/index.html)

---

### Muoversi all'interno di un documento XML: XPATH

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






