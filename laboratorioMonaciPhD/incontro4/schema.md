### XML schema e ODD

Uno schema XML è un documento che definisce il set di elementi e attributi da utilizzare e la loro reciproca posizione all'interno di un documento XML; lo schema indica, ad esempio, quali elementi possono essere utilizzati all'interno di quali altri.

Un documento XML è **well formed** quando rispetta la sintassi dell'XML (e in particolare le [*golden rules*](https://elespdn.github.io/talks/labMonaci1-xmlTei.html#/6)), mentre è **valido** rispetto ad uno schema.

La TEI mette a disposizione alcuni schemi (vd. sotto), ma consiglia di creare uno schema personalizzato per ogni progetto, che risponda alle esigenze specifiche.

Alcuni degli schemi predisposti dalla TEI sono elencati di seguito:

- **tei\_all** include tutti gli elementi e attributi presenti nelle Guidelines e le regole per il loro utilizzo
- **tei\_lite** una selezione ristretta di elementi e attributi, che permette di effettuare una codifica di base su diversi tipi di testi
- **tei\_drama** una selezione di elementi e attributi per la codifica di testi teatrali
- **tei\_speech** una selezione di elementi e attributi per la codifica di testi orali.

### ODD e formati degli schemi
Le TEI Guidelines sono esse stesse uno schema, corrispondente al **tei\_all**, o meglio una specifica(zione)/*specification* **ODD** (‘One Document Does it All’). Una ODD è un documento XML che contiene lo schema **e** tutta la relativa documentazione (in prosa e non).

La ODD TEI può essere trasformata in uno dei formati adatti per lo schema (DTD, RELAX NG schema o W3C Schema) utilizzando Roma (vd. sotto)

Per saperne di più: [Getting Started with P5 ODDs](http://www.tei-c.org/Guidelines/Customization/odds.xml#body.1_div.2_div.7).

### Roma
[Roma](http://www.tei-c.org/Roma/) è un'applicazione web per creare personalizzazioni della TEI, che permette, attraverso un'interfaccia composto da diversi formulari, di scegliere i moduli, aggiungere e eliminare elementi, cambiare gli attributi, e atre operazioni di personalizzazione.

Per saperne di più: [Customising TEI, ODD, Roma](http://teibyexample.org/modules/TBED08v00.htm#summary).


#### Associazione di uno schema a un documento
L'associazione di un documento con uno schema avviene automaticamente in oXygen quando creiamo un documento TEI utilizzando i templates a disposizione. Ogni documento XML-TEI, infatti, si aprirà con la dichiarazione XML e di codifica dei caratteri:

	<?xml version="1.0" encoding="UTF-8"?>

Di seguito, troviamo l'associazione con lo schema:

	<?xml-model href="http://www.tei-c.org/release/xml/tei/custom/schema/relaxng/tei_all.rng" type="application/xml" schematypens="http://relaxng.org/ns/structure/1.0"?>

Se volessimo associare uno schema ad un documento che ne fosse privo, in oXygen possiamo utilizzare il menu > *Document* > *Schema* > *Associate schema*, oppure utilizzando il bottone *Associate schema* (con puntina rossa) sulla barra degli strumenti.

L'associazione con uno schema è ciò che permette a oXygen di suggerire gli elementi e gli attributi a disposizione in un determinato luogo del documento, di visualizzare brevi descrizioni degli elementi contestualmente o nelle finestre laterali.

Associare uno schema o un altro ad un documento non è ovviamente senza conseguenze. Per vederne gli effetti, facciamo un piccolo esempio.

Utilizziamo il sonetto già codificato, al quale sono stati aggiunti alcuni elementi, e in particolare la codifica degli aspetti metrici (limitatamente alla prima quartina). 

- aprire oXygen
- creare un nuovo documento vuoto (ossia creare un documento TEI o XML e cancellarne tutto il contenuto)
- copiare il contenuto di ['sonettoTEI_rhyme.xml'](https://github.com/elespdn/laboratorio-monaci/blob/master/lezione3/sonettoTEI_rhyme.xml) 
- incollarlo nel documento vuoto aperto in oXygen
- salvarlo

Si può notare che il documento ha uno schema associato, **tei\_all**, come si vede nella immagine qui sotto.

<img style="border:1px solid; margin:5%" src="images/teiall.png" width="80%"/>

Proviamo a cambiare lo schema, associando ad esempio lo schema **tei\_lite**. Sarà sufficiente cambiare la dicitura direttamente nel documento, mentre oXygen troverà il percorso verso il file di riferimento, salvato insieme agli altri che costituiscono il framework TEI in oXygen.

**tei\_all.rng** adnrà dunque cambiato in **tei\_lite.rng**

Si noterà che il quadratino verde diventerà rosso: c'è qualche problema! Quale? L'elemento < rhyme > (e anche l'attributo @rhyme in < lg >) **non** sono ammissibili nello schema **tei\_lite**. 

### Perché utilizzare uno schema. Conclusione

Uno schema permette di dare consistenza alla codifica, all'interno di un documento o tra più di uno, definendo gli elementi e gli attributi da utilizzare e le loro reciproche posizioni. Definire lo schema è dunque un compito fondamentale per un progetto che preveda la codifica in XML di documenti.

Come abbiato visto, la TEI offre uno strumento per la creazione di schemi, Roma. Ma prima ancora della questione tecnica, bisognerà interrogarsi su **cosa e come** si vuole codificare, definire quindi formalmente quelle istruzioni per la codifica che poi potranno essere codificate nello schema.






