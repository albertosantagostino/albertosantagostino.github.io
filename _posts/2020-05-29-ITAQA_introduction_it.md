---
layout: article
title: "Hello, ITAQA"
lang: it
ref: itaqa-introduction
date: 2020-05-29
---

## Contesto ed introduzione

Durante la [pandemia di COVID-19 del 2020](https://it.wikipedia.org/wiki/Pandemia_di_COVID-19_del_2019-2020) il rallentamento delle attività umane ha causato molti effetti secondari. Uno dei più discussi e notati dai media è stata la riduzione dell'inquinamento atmosferico in molti paesi.

*(Piccolo disclaimer: in questa serie di post non parlerò delle conseguenze socioeconomiche derivanti dalla pandemia. Non sono un economista e non ho gli strumenti per discutere di questi aspetti)*

Anche in Italia sono stati osservati effetti positivi sull'ambiente: in molte città da febbraio a maggio 2020 l'inquinamento è diminuito, ed abbiamo tutti letto notizie sull'[acqua limpida dei canali di Venezia](https://www.rainews.it/dl/rainews/media/coronavirus-Venezia-acqua-dei-canali-tornata-limpida-Si-vedono-i-pesci-062af3c3-5cc9-4bb4-ab6b-76bace1ca8e6.html#foto-1) e di [animali selvatici girare in città deserte](https://www.3bmeteo.com/giornale-meteo/coronavirus-e-ambiente--animali-liberi-si-riprendono-i-loro-spazi--anche-in-citt----video-326854).

Mi ha colpito molto un video che mostra la riduzione dei livelli di diossido di azoto (NO<sub>2</sub>), misurato da un satellite dell'ESA. Particolarmente evidente è la diminuzione di questo inquinante (prodotto in larga misura dal traffico urbano) nella Pianura Padana, area dell'Italia che sappiamo essere pesantemente inquinata, anche a causa della sua [situazione geografica](https://it.wikipedia.org/wiki/Pianura_Padana#Inquinamento).

{% include youtube_video.html id='ARpxtAKsORw' %}

Dopo aver visto questo video, mi sono chiesto se fosse possibile ottenere una visualizzazione simile (o perfino più dettagliata, riguardante più sostanze inquinanti) usando non dati satellitari, ma ottenuti dalle **stazioni fisse di qualità dell'aria** distribuite sul territorio nazionale.


### Molte stazioni, nessun entrypoint comune

Il problema più grande è che **ogni regione italiana** (e ce ne sono 20) ha una versione "leggermente diversa" della stessa agenzia ambientale che si occupa di qualità dell'aria e di tematiche ambientali. Queste agenzie si chiamano tutte [**ARPA**](https://it.wikipedia.org/wiki/Agenzia_regionale_per_la_protezione_ambientale), ma sfortunatamente non distribuiscono dati nello stesso modo.

Anche i siti web sono tutti molto diversi fra loro e forniscono dati in formati differenti. Per alcune regioni, non ci sono API accessibili, rendendo lo scaricamento dei dati un processo da effettuarsi manualmente.

{:refdef: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200529/ARPA_websites.jpg'}}" title="Alcuni siti web dell'ARPA, tutti decisamente diversi" class="responsive" onclick="window.open(this.src)">
{: refdef}

## Introducing ITAQA (ITaly Air Quality Aggregator)

L'idea che ho avuto si è concretizzata in **ITAQA**, una collezione di strumenti in grado di **scaricare**, **aggregare** e **visualizzare** dati sulla qualità dell'aria, **unificando** misurazioni provenienti da comuni di diverse regioni in un unico posto.

{:refdef: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200529/ITAQA_banner.png'}}" title="ITAQA logo" class="responsive" onclick="window.open(this.src)">
{: refdef}

### Data flow e descrizione del processo

Allo stato attuale, il processo di raccolta dati è il seguente: 

* Vengono eseguiti una serie di **crawlers**, script in grado di automaticamente ottenere e processare dati della qualità dell'aria da differenti siti web ARPA, effettuando un parsing ed inserendoli in **strutture dati comuni** (oggetti `AirQualityStation`, `AQS` in breve)
* Le liste di oggetti `AQS` vengono **serializzate** e salvate, in modo da poterle ricaricare in seguito, evitando la ripetizione dello step precedente
* I dati unificati vengono **processati** tramite moduli di visualizzazione ed analisi, per ottenere grafici, mappe interattive e tabelle

#### Architettura

{:refdef: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200529/ITAQA_architecture.png'}}" title="Architettura di ITAQA" class="responsive" onclick="window.open(this.src)">
{: refdef}

## Quali sono i risultati?

La prima cosa che vorrei fare è produrre un grafico per ogni regione in grado di mostrare i cambiamenti della qualità dell'aria **correlati con i diversi "livelli" di lockdown** implementati a causa della pandemia. Molto probabilmente la riduzione della circolazione delle persone (meno macchine in giro, più remote working, quasi nessun viaggio) ha portato ad un evidente calo dell'inquinamento. Mi piacerebbe poter misurare questa riduzione in dettaglio e vedere se è avvenuta in modo uniforme in ogni parte d'Italia.

Già questo è un risultato indubbiamente interessante, ma si può fare molto di più.

Avere un singolo insieme di dati sull'inquinamento atmosferico (alla risoluzione del singolo comune, con informazioni aggiuntive come la posizione geografica di ogni sensore) significa avere uno strumento con cui verificare una varietà di correlazioni in modo quasi immediato, semplicemente aggiungendo moduli dedicati per l'aggregazione e la visualizzazione dei dati.

### Verificare congetture

Il lockdown di questi mesi definisce un periodo di tempo particolare su cui si possono fare congetture e considerazioni di svariato tipo, che diventano verificabili con ITAQA.

Per fare qualche esempio di congetture (poste in maniera semplificata, magari completamente sbagliate):

* Gli ossidi di azoto (NO<sub>X</sub>) sono diminuiti molto a causa del calo di movimento delle persone, mentre il monossido di carbonio (CO) non è variato molto, in quanto molte persone costrette a casa hanno usato in maniera maggiore i riscaldamenti domestici
* Le città costiere hanno diminuito il livello di inquinanti più velocemente rispetto alle città dell'entroterra
* La diminuzione dell'inquinamento è proporzionale alla dimensione della città

#### Considerazione rapida sullo scopo del progetto

Analisi simili (misurazione del calo dell'inquinamento durante il lockdown) sono già state effettuate da altri, fra cui le stesse ARPA. Molto probabilmente i risultati ottenuti da ITAQA non saranno nulla di nuovo. Detto ciò:

* Mi piace lavorare su questo progetto
* Sono abbastanza sicuro che un posto dove questi dati vengono aggregati, per tutte le regioni italiane e con una risoluzione a livello del singolo sensore, non esista (almeno pubblicamente)
* L'intero progetto richiede molte decisioni tecniche interessanti da affrontare e lo rendono un bell'esercizio di programmazione/architettura a lungo termine

## Stato attuale

Il framework è sviluppato in Python ed attualmente è ancora incompleto: solamente un crawler è funzionante (sebbene sia da migliorare) ed in grado di generare una lista di `AQS`.

A grandi linee lo "scheletro" c'è, mancano ancora molte cose, fra cui i moduli per la visualizzazione. Sto lavorando sul progetto in modo saltuario ma conto di riuscire a produrre i primi risultati a breve.

La cosa che impegnerà più tempo sarà la scrittura dei crawler: essendo ogni sito dell'ARPA differente, per ogni regione una soluzione tecnica ad-hoc deve essere adottata. Probabilmente in alcuni casi l'unica possibilità sarà il parsing di tabelle embeddate nelle pagine web (usando una libreria come `beautifulsoup`)

### Coming soon

Racconterò qualcosa sulla parte tecnica nei prossimi post. In ogni caso, il progetto è completamente open-source e disponibile per la consultazione: **[ITAQA-air-quality-aggregator](https://github.com/albertosantagostino/ITAQA-air-quality-aggregator)**

Argomenti su cui potrei scrivere qualcosa, in nessun ordine particolare:

* Oggetti comuni (`AQS`), `pandas.DataFrame` come struttura dati
* Digressione su inquinanti ed indicatori dell'inquinamento atmosferico
* Crawler della Lombardia, correlazione fra stazioni vicine e processo di raccolta dati
* Serializzazione ed encoding ("come salvo molti dati in un una struttura compatta?")



Grazie per la lettura, ed a presto! :)