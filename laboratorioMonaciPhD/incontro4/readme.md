# Lezione 4

Giovedì 12 gennaio 2017


## TEI Guidelines: moduli, schema, elementi
- schema, vd. tutorial su [ODD e Schema](schema.md)
- moduli, vd. slide [Intro TEI](https://elespdn.github.io/talks/labMonaci1-xmlTei.html#/17) della prima lezione
- guardiamo da vicino un elemento e la relativa documentazione: < opener > [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-opener.html)
- guardiamo da vicino un elemento e la relativa documentazione: < hi > [qui](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-hi.html)

## Controllo sugli originali

Nel catalogo del fondo (Calzolari 2005), controlliamo il numero della busta in cui è contenuta la lettera.

Sul documento originale controlliamo:

- trascrizione
- cambi di pagina **< pb / >** (*page breaks*). **Attenzione!** si tratta di un elemento vuoto, quindi invece di avere un tag che apre e uno che chiude, ne avremo uno solo, con la barra dopo il nome. **Non** bisogna lasciare uno spazio bianco dopo l'elemento. Esempio:

		Non c'è più spazio su questo foglio quindi passo <pb/>al seguente.

- maiuscole, accenti e punteggiatura
- sottolineature, da codificare con l'elemento **< hi >** (*highlight*) e l'attributo **@rend** con valore **"underlined"**. Esempio:

		La nostra <hi rend="underlined">Rivista di filologia romanza</hi> sarà pubblicata a breve.

- nel caso in cui ci siano altri tipi di evidenziatura, codificarli con **< hi >** e l'attributo **@rend** con valore "evidenziato" o altro più appropriato. Esempio:
		
		Ci sono due parole scritte più grandi: <hi rend="grande">la nostra Rivista</hi>; poi il testo continua.

- lettere in apice, da codificare con **< hi >** e l'attributo **@rend** con valore **"sup"**. Esempio:

		V<hi rend="sup">a</hi> excelencia

- Correzioni, cancellature, aggiunte. Da segnare a parte.
- **Opzionale**: a capo **< lb >** (*line breaks*). **Non** bisogna lasciare uno spazio bianco dopo l'elemento. Esempio:

		Questa è la prima riga, <lb/>questa è la seconda, <lb/>poi la terza <lb/>etc.


## Da fare per 18 gennaio
- codificare la nuova lettera e mandarla a Elena entro il 16 gennaio 
- n.b.: il nome del file deve essere composto da data (yyyymmdd), mittente e destinatario (tutto minuscolo), intramezzati da trattino basso. Es.

		18720507_rajna_monaci.xml