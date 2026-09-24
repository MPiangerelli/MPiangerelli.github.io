---
layout: post
title: "Covid-19: qualche dato"
date: 2020-03-16 12:00:00+0100
description: Il modello SIR spiegato in modo semplice e qualche dato reale sulla diffusione del SARS-CoV-2 in Italia, con aggiornamenti fino all'8 aprile 2020.
tags: [covid-19, epidemiology, sir-model]
categories: [data-analysis]
redirect_from:
  - /2020/03/14/Covid1/
  - /general/2020/03/13/Covid-19/
---

*Post scritto con [Renato De Leone](http://rdeleone.sst.unicam.it/rdeleone/index.php/it/) nel marzo 2020 e aggiornato fino all'8 aprile 2020. I grafici interattivi originali (Fig. 1, 2, 4 e 6), ospitati su un servizio esterno, non sono più disponibili; il testo è riportato integralmente.*

In questi giorni l'attenzione di tutti è per il virus SARS-CoV-2, comunemente chiamato "Coronavirus". Esso è stato individuato per la prima volta nella città di Wuhan in Cina il 31-12-2019 e ha avuto una rapida diffusione (guarda la [cronistoria](https://www.who.int/emergencies/diseases/novel-coronavirus-2019/events-as-they-happen)).

#### Il virus

Il Coronavirus si è diffuso subito in molti paesi, tra cui l'Italia, creando non pochi problemi e costringendo i governi a varare misure eccezionali per cercare di contenere la sua diffusione e non gravare sui vari sistemi sanitari. In questo post si cercherà di spiegare, utilizzando modelli matematici, come si diffonde un virus e perché il virus SARS-CoV-2 è "pericoloso" per il SSN italiano. Infine commenteremo qualche dato per comprendere la motivazione delle misure di contenimento prese dal Governo italiano.

#### Il modello SIR

L'epidemiologia, cioè la scienza che studia la diffusione delle epidemie, ha sviluppato dei modelli matematico-computazionali per cercare di studiare l'andamento e prevedere parametri importanti nella diffusione delle epidemie. Uno di questi modelli è il SIR, acronimo di Susceptible-Infected-Recovered (Suscettibili-Infetti-Recuperati). Questo modello, introdotto da [Kermack e McKendrick](https://royalsocietypublishing.org/doi/10.1098/rspa.1927.0118) nel 1927, è un cosiddetto modello compartimentale poiché suddivide la popolazione in tre compartimenti (S, I ed R) e simula cosa potrebbe succedere, col passare del tempo, agli individui appartenenti a queste popolazioni. Come ogni modello, esso *cerca* di descrivere la realtà, partendo da alcune ipotesi iniziali, ma *non è* la realtà. Ciò che accade realmente è molto complesso e occorre comprendere che, pur essendo questo modello una buona approssimazione, esso non è esatto. Per chi fosse curioso, le equazioni che descrivono il modello SIR sono riportate di seguito:

$$
\frac{dS}{dt} = -\beta S I \qquad (1)
$$

$$
\frac{dI}{dt} = \beta S I - \gamma I \qquad (2)
$$

$$
\frac{dR}{dt} = \gamma I \qquad (3)
$$

Tali *equazioni* sono *equazioni differenziali*. Come *equazioni* esprimono l'idea di uguaglianza tra ciò che si trova a sinistra e ciò che si trova a destra del simbolo "=". Le *equazioni differenziali* "descrivono" la variazione di una quantità rispetto ad un'altra. A sinistra del simbolo "=" abbiamo i d/dt, che leggeremo come "la variazione nel tempo di S (1), I (2) ed R (3)" rispettivamente. A destra del simbolo "=" abbiamo moltiplicazioni, somme e sottrazioni.

La prima equazione si legge "la variazione nel tempo dei Suscettibili è uguale all'opposto del prodotto tra *β*, i Suscettibili e gli Infetti". I simboli *β* e *γ* sono i cosiddetti parametri del modello: rappresentano rispettivamente il parametro di *trasmissione* (tasso di contagio tra persone S e I) e il parametro dei *recuperati* (tasso di persone passate da I a R). La quantità *R*<sub>0</sub> = *β*/*γ* è chiamata *numero di riproduzione di base*: rappresenta il numero medio di infezioni secondarie, ovvero quelle prodotte da ciascun individuo infetto in una popolazione completamente suscettibile (mai venuta a contatto con il nuovo patogeno emergente). Questo parametro misura la *potenziale trasmissibilità* di una malattia infettiva. Quanto maggiore è il valore di *R*<sub>0</sub>, tanto più elevato è il rischio di diffusione dell'epidemia. Se il fattore *R*<sub>0</sub> di una malattia infettiva è circa 2, significa che, in media, un singolo malato infetterà due persone. Se invece il valore di *R*<sub>0</sub> è inferiore ad 1 significa che, in media, un singolo malato infetterà "meno di una persona" e dunque l'epidemia può essere contenuta.

Implementando il modello e simulando al computer la sua dinamica (la sua evoluzione nel tempo con dei valori fittizi), quello che otteniamo è un grafico come quello in Fig. 1: le curve indicano, al passare del tempo, la percentuale di individui che appartengono ad ogni compartimento. La curva degli Infetti raggiunge un picco e poi decade. Tale picco è *più o meno* alto e *più o meno* traslato nel tempo, a seconda dei parametri *β* e *γ*.

*Fig. 1 (grafico interattivo non più disponibile): simulazione del modello SIR utilizzando parametri fittizi.*

#### Perché il picco è importante?

Il picco è una caratteristica da tenere in considerazione: rappresenta il numero massimo di Infetti in un giorno. La Fig. 2 comparava due casi:

- curva rossa: la diffusione dell'epidemia è veloce e si ha un picco molto alto e "vicino nel tempo";
- curva blu: la diffusione dell'epidemia è meno veloce e si ha un picco più basso e più "lontano nel tempo".

In Fig. 2, inoltre, si poteva vedere una linea orizzontale nera: questa rappresenta la capacità di posti in terapia intensiva del SSN. Come riportato nelle [statistiche](https://www.thelancet.com/journals/lancet/article/PIIS0140-6736(20)30627-9/fulltext), nel caso specifico del SARS-CoV-2 circa un 11% di Infetti sviluppa delle complicazioni tali per cui è necessario un ricovero in terapia intensiva. Conoscere il picco di contagi aiuterebbe a stimare quante persone potrebbero aver bisogno della terapia intensiva. Confrontando questo con il numero effettivo dei posti disponibili in terapia intensiva si potrebbe stimare se il SSN *collasserebbe* oppure *riuscirebbe a far fronte* all'avanzata dell'epidemia. Le curve arancione e celeste rappresentavano l'11% degli Infetti rispettivamente nel primo (curva rossa) e nel secondo caso (curva blu) di epidemia: nel primo caso il SSN non riuscirebbe a far fronte al numero dei ricoveri in terapia intensiva (la curva arancione, nel momento del picco, è sopra la curva nera); nel secondo caso il SSN riuscirebbe a sistemare tutti i pazienti in terapia intensiva (la curva celeste è al di sotto della curva nera).

*Fig. 2 (grafico interattivo non più disponibile): andamento degli Infetti in due scenari diversi.*

La domanda che occorrerebbe porsi è "come si può passare dalla curva rossa alla curva blu, dando quindi tempo al SSN di assorbire i casi acuti?". La matematica (e il modello SIR) risponde con la NECESSITÀ di ridurre il valore del coefficiente *β*. In pratica è necessario ridurre il tasso di contagio EVITANDO I CONTATTI CON ALTRE PERSONE: SEMPLICEMENTE STANDO A CASA E USANDO MISURE PROTETTIVE. Stare TUTTI (non solo i malati) a casa si rende necessario in quanto la maggior parte dei contagiati dal virus è asintomatica (non mostra i sintomi e non sa di essere malata), ma può infettare gli altri. Limitare i contatti serve soprattutto ad evitare che gli asintomatici possano infettare le persone con cui vengono a contatto. Proprio per questo motivo il Governo ha varato delle misure che potrebbero essere definite di "allontanamento sociale" (la sospensione di aggregazioni pubbliche e dei trasporti) e di "riduzione della trasmissione per contatto" (ad esempio mediante l'uso di misure di protezione personale). In Cina sembrerebbe che tali misure riducano il numero di riproduzione di base *R*<sub>0</sub>, agendo sul coefficiente *β*.

#### Qual è la situazione italiana?

Per comprendere la situazione italiana possiamo leggere i dati reali (disponibili sul sito della [Protezione Civile](http://opendatadpc.maps.arcgis.com/apps/opsdashboard/index.html#/b0c68bce2cce478eaac82fe38d4138b1)) e possiamo fare una simulazione utilizzando il modello SIR (stimando i valori *β* e *γ*).

Il primo dato (reale) che ci occorre conoscere è quello che descrive il numero dei posti letto in terapia intensiva. In Fig. 3 è riportata una tabella presa dall'articolo [The variability of critical care bed numbers in Europe](https://link.springer.com/article/10.1007/s00134-012-2627-8) (di Rhodes et al.) apparso nel 2012 nella rivista Intensive Care Medicine. Dall'articolo si evince che al 2009 il numero di posti in terapia intensiva (ICU and IMCU beds) è di 12.5 ogni 100 000 abitanti. Calcolando tale numero per l'intera popolazione italiana (60 milioni di abitanti) abbiamo, in totale, circa 7500 posti letto in terapia intensiva.

{% include figure.liquid path="assets/img/blog/acutecaremedicine1.png" class="img-fluid rounded" alt="Tabella dei posti letto in terapia intensiva nei paesi europei" %}
<div class="caption">Fig. 3: tabella che descrive il numero dei posti letto nei paesi europei (Rhodes et al., 2012).</div>

Occorre poi conoscere il valore di *R*<sub>0</sub>, da cui ricaveremo *β* e *γ*. Da quando il Coronavirus SARS-CoV-2 ha iniziato a diffondersi, l'Organizzazione Mondiale della Sanità (OMS) e altri istituti di ricerca hanno diffuso *stime* di *R*<sub>0</sub>. I valori di *R*<sub>0</sub> vanno da [1.4 a 3.8](https://www.iss.it/primo-piano/-/asset_publisher/o4GR9qmvUz9/content/id/5268851). Nella nostra simulazione si è deciso di usare il caso "peggiore", ovvero *R*<sub>0</sub> = 3.8. Dal momento che *γ* = 1/14 (14 sono i giorni in cui una persona infetta può infettare altri; al passare dei 14 giorni la persona viene definita recuperata) otteniamo che *R*<sub>0</sub>·*γ* = *β*, quindi *β* = 3.8/14 = 0.271. Utilizzando questi valori nel modello SIR si ottiene l'andamento della Fig. 4, dove:

- curva blu: la popolazione totale, che può essere infettata;
- curva verde: la popolazione che non è più infetta;
- curva rossa: la popolazione infetta e che può infettare gli altri;
- curva arancione: la popolazione infetta, che può infettare gli altri e che richiede cure in terapia intensiva;
- curva nera: posti disponibili in terapia intensiva.

*Fig. 4 (grafico interattivo non più disponibile): simulazione del modello con parametri "reali", lo scenario che potrebbe accadere in Italia.*

La curva nera risultava notevolmente sotto la curva arancione: questo indica che i posti in terapia intensiva non riusciranno a soddisfare il bisogno dei pazienti. I dati che leggiamo risultano particolarmente allarmanti e catastrofici. Dobbiamo però tener conto di alcune riflessioni:

- il valore *R*<sub>0</sub> è solo una stima (l'esatto valore si conoscerà solo alla fine dell'epidemia) e descrive la realtà cinese, che potrebbe essere differente da quella italiana;
- in questa simulazione non si sta tenendo conto delle misure di contenimento che, come abbiamo visto in Fig. 2, abbassano e "rallentano" il picco;
- è probabile che il virus stia circolando in Italia da molto tempo (inizi/metà gennaio); se ciò fosse vero potrebbero esserci stati degli effetti di immunizzazione sulla popolazione di cui non siamo a conoscenza, che potrebbero abbassare ulteriormente il picco degli Infetti.

Cosa fare? Niente panico, ma evitate i contatti!

#### Le politiche di contenimento funzionano?

Per comprendere se le politiche di contenimento e di allontanamento sociale funzionino è necessario "leggere" cosa dicono i dati reali. In Fig. 5 sono mostrate due curve che rappresentano l'andamento dei nuovi contagi giornalieri nella provincia di Hubei (curva rossa) e in Italia (curva verde). La provincia di Hubei, dove si trova Wuhan, ha circa la stessa popolazione dell'Italia: confrontare queste due realtà è più coerente che confrontare tutta la Cina con l'Italia. Le due curve sono allineate: partono entrambe dal giorno in cui i dati sono stati confermati dai rispettivi organismi ufficiali (20 gennaio 2020 per la Cina e 24 febbraio 2020 per l'Italia). Bisogna dire, però, che i primi contagi in entrambi i paesi sono avvenuti almeno un mese prima di tali date. L'asse dei tempi per la Cina è in basso, mentre per l'Italia è in alto. Entrambe le curve riportano i dati fino al 14 marzo 2020. Nella Fig. 5 sono riportati anche gli inizi delle misure di contenimento (lockdown) prese dai due Governi: il Governo italiano è intervenuto quando la curva stava già assumendo un andamento esponenziale. Dopo 35 giorni di misure di contenimento, fonti non ufficiali dichiarano che le misure siano [state allentate](https://www.repubblica.it/esteri/2020/03/06/news/coronavirus_cina-250489446/). Notiamo che la curva della provincia di Hubei sta arrivando a saturazione: non cresce/decresce e si sta mantenendo costante. Questo comportamento si discosta un po' dal modello teorico (SIR), dove il picco è netto ed è seguito da una riduzione dei contagiati. La differenza tra teoria e realtà potrebbe essere dovuta a diversi fattori pratici nel procedimento di processamento dei dati ed anche al fatto che i 14 giorni di infettività sono, in realtà, una media.

{% include figure.liquid path="assets/img/blog/lockdown_tot_25.png" class="img-fluid rounded" alt="Nuovi contagi giornalieri nella provincia di Hubei e in Italia" %}
<div class="caption">Fig. 5: andamento dei nuovi contagi giornalieri nella provincia di Hubei e in Italia.</div>

Guardiamo solo la situazione italiana e facciamo riferimento alla Fig. 6. Qui erano presenti dei pallini neri, che rappresentano i dati reali dei nuovi contagi cumulati giornalieri, e due curve: una arancione ed una blu. La curva blu rappresenta l'andamento dei dati, approssimato con una curva esponenziale (il fit), fino al giorno in cui il Governo italiano ha decretato le misure di contenimento (lockdown); la curva arancione rappresenta il fit dei dati considerando anche i giorni successivi all'emanazione del decreto e fino al 15/03/2020. La curva verde rappresenta la stessa situazione della curva arancione ma fino al 17/03/2020. La differenza tra curva arancione e curva blu è minima, tuttavia notiamo due pendenze diverse. Si può notare che c'è stato un effettivo (anche se minimo) rallentamento nelle previsioni degli Infetti; la curva verde ha una pendenza minore sia della curva blu che della curva arancione, indicando ancora un abbassamento del numero di Infetti. Bisogna continuare a favorire questa tendenza.

Oggi, 8 aprile, si può vedere che i modelli esponenziali (curve blu, arancione, verde, gialla e celeste) usati inizialmente per descrivere i dati non riescono più a descriverli in maniera soddisfacente (curva marrone). Questo ha determinato la scelta di un modello diverso: si sono scelti un modello gaussiano (curva a campana), rappresentato dalla curva rosa, e un modello logistico (o curva sigmoide), rappresentato dalla curva viola. Si nota subito che il modello logistico è quello che descrive meglio i dati raccolti fino a questo punto. Il modello logistico è descritto da una curva che ad un certo punto arriva ad un valore costante: anche se la variabile sull'asse orizzontale cresce, ad esempio il tempo, il corrispondente valore sull'asse y non aumenta. Questo andamento è, teoricamente, in linea con quello che ci aspetteremmo di vedere: molto semplicemente significa che abbiamo raggiunto una situazione per cui tutti i soggetti infettabili sono stati infettati e quindi, non essendoci più nessuno suscettibile, il fenomeno epidemico è destinato ad estinguersi. È importante ribadire che i dati descrivono i nuovi contagi cumulati giornalieri e quindi non si vedranno mai questi dati andare a zero; si potrebbe capire che non ci sono più nuovi contagi quando il numero dei nuovi contagiati rimarrà costante per un periodo (lungo) di tempo. Ovviamente la curva sigmoide potrebbe raggiungere la situazione stazionaria, ovvero di "non crescita", molto lentamente. Purtroppo questa tendenza potrebbe non essere quella effettiva poiché, come si sa, il numero degli infetti dipende abbastanza fortemente dal numero dei tamponi (pochi) che vengono effettuati e quindi i contagi che risultano dai dati potrebbero essere (anzi sono) sottostimati.

*Fig. 6 (grafico interattivo non più disponibile): nuovi contagi cumulati giornalieri in Italia con fit esponenziali, gaussiano e logistico.*

Per concludere si può affermare che:

- i modelli mostrano che il SSN potrebbe essere messo a dura prova dal SARS-CoV-2;
- i dati confermano l'aumento dei casi giornalieri e provano che il picco dei casi italiani deve ancora arrivare (probabilmente entro metà aprile);
- i dati mostrano che, dall'entrata in vigore delle misure di "isolamento sociale", si è rilevata una lieve riduzione della velocità dei contagi, ma solo nei prossimi giorni si potrà determinare se tali misure hanno avuto realmente effetto; ora possiamo dire che qualcosa sta cambiando, ma bisogna essere consapevoli delle stime (al ribasso) del numero degli infetti;
- **rimanere a casa, evitare i contatti ed usare strumenti di protezione** erano le strategie da perseguire per ottenere un abbassamento del numero *R*<sub>0</sub>, e quindi un abbassamento della velocità di crescita delle curve in Fig. 6, al fine di limitare e rallentare il contagio;
- **rimanere a casa il più possibile, evitare i contatti ed usare strumenti di protezione** è la strategia che si dovrebbe continuare ad usare per permettere alla curva logistica di raggiungere la stazionarietà nella maniera più veloce possibile.

*(Aggiornato all'8 aprile 2020.)*
