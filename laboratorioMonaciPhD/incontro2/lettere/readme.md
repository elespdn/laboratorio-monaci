In questa cartella sono raccolte le trascrizioni di alcune delle lettere contenute nell'Archivio di Ernesto Monaci.

Come è organizzata e cosa contiene.


### Nome dei file
Il file di ogni lettera è chiamato con

- data (anno, mese, giorno; senza spazi né trattini né barre all'interno)
- trattino
- nome del mittente
- trattino
- nome del destinatario.

Si consiglia di chiamare **nello stesso modo** i file XML/TEI di ogni lettera che saranno creati durante il corso, chiaramente con estensione **.xml** e non **.txt**


### Cosa contiene ogni file
I file contengono ognuno la trascrizione di una lettera.
All'inizio, è specificato chi ha trascritto la lettera (Dottorandi Scienze del Testo, a.a. 2012-2013). Questa informazione deve essere mantenuta e codificata nei metadati, nella sezione <resp>, come vedremo più avanti nel corso.


### Estensione dei file
L'estensione di un file è la convenzionale abbreviazione che segue il punto alla fine del nome del file e indica il tipo di file. Alcune estensioni comuni sono **.doc**, **.odt**, **.pdf**, **.xml**. L'estensione permette alle applicazioni (e a noi) di riconoscere il tipo di file e processarlo correttamente. Ogni file (ma NON le cartelle) devono avere un'estensione. Se l'estensione non è visibile, cambiare le impostazioni del computer al riguardo (cercare nella guida del computer o su internet come fare; su Windows, controllare la tab 'Visualizza', in una qualsiasi cartella, e spuntare l'opzione 'Visualizza estensione del file').

I file in questa cartella sono dei file di testo semplice, ovvero **.txt**, codificati in UTF-8. Il testo semplice è la forma meno ricca per un testo elettronico, ma proprio per questo leggibile e processabile dal maggior numero di applicazioni. Si può aprire e modificare un file **.txt** utilizzando Notepad (o Notepad++), TextEdit, oXygen e molte altre applicazioni (inclusi Microsoft Word e Open Office, che però non sono quelli sui quali lavoreremo, quindi sono poco consigliati). 

La codifica di caratteri UTF-8, così come altri tipi di codifica dei caratteri, associa un insieme di caratteri (i nostri grafemi) ad un insieme di numeri (il codice della macchina). [Vedi su wikipedia](https://it.wikipedia.org/wiki/Codifica_di_caratteri).

Per vedere cosa succede se proviamo a visualizzare un testo codificato in Unicode (di cui UTF-8 è una delle possibili realizzazioni) con un browser che prevede una codifica diversa, basta aprire il browser Mozilla Firefox e una qualsiasi pagina web. Nella barra dei menu cliccare su "Visualizza opzioni per la codifica del testo" (icona di tasto con 'ae' sopra). Provando a cambiare tra Unicode e Occidentale, si vedranno le conseguenze nel testo della pagina web: alcuni caratteri non saranno più correttamente visualizzati.


### More on file naming conventions (optional)

> The following is an extract of: Preparatory materials for the DiXiT 'Code and Collation' Workshop held in Amsterdam, November 2016 <https://github.com/DiXiT-eu/collatex-tutorial/blob/master/unit1/Command_line.ipynb>

Some applications will let you use characters in filenames that are not easily processed by other applications, and because in Digital Humanities we often process the same files with multiple applications, it is safest and wisest to use the most restricted inventory of filename characters. In our own work we observe the following conventions:

* Filenames should not contain any characters except letters, digits, hyphens, underscores, and periods. Most importantly, no space characters or punctuation other than hyphens, underscores, and periods should be used in filenames.
* Operating systems differ in whether they consider uppercase letters the same as or different from lowercase letters, and because it’s common to have project members who use different operating systems while working on the same, shared, files, it’s wisest to treat uppercase and lowercase as equivalent even if they aren’t in your personal operating system (that is, not to create different files with names like “contents.txt” and “Contents.txt”). For that reason, choose a capitalization strategy and observe it consistently throughout your project. One common convention avoids the use of uppercase letters except in camel case (see below)
* Filenames that contain multiple logical words can avoid the use of spaces and still maintain legibility by using underscores, hyphens, or *camel case*, e.g., “index_places.txt”, “index-places.txt”, or “indexPlaces.txt”. Choose a convention and use it consistently, so that you won’t have to search for all of the alternate ways your index of places might have been spelled when you need to find a file, and so that you won’t create files with all three types of names and lose track of which is the most recent.
* If you keep multiple versions or drafts of files in the same directory, include a date stamp in the filename. We recommend a year-month-date format, with a four-digit year and two-digit months and dates, e.g., “2016-07-30_index-places.txt”. It’s tempting to make up names on the spot like “chapter_one_new_version.txt” or “chapter_one_really_really_final_version.txt”—and it’s also clear why this is a really, really Bad Idea. You may find it least confusing to create date-stamped backup subdirectories and store old versions of file there, so that your working directory will contain only current versions of files.



