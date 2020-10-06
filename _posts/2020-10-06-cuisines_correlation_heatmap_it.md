---
layout: article
title: "La cucina più famosa del mondo (su Wikipedia)"
lang: it
ref: cuisines-correlation-heatmap
date: 2020-10-06
---

Dall'[ultimo post](https://albertosantagostino.github.io/blog/2020/06/28/servicehandler_it) è passato un po' di tempo, ma nel mentre un paio di progettini interessanti sono nati[^1]

Fra una [bozza di ricettario](https://albertosantagostino.github.io/ricettario/) creato per organizzare alcune mie note ed il [calcolo del baricentro della Sardegna](https://github.com/albertosantagostino/sardinia-geographical-centroid) (improvvisato rientrando dalle vacanze), girando su Wikipedia a leggere voci su cucine straniere mi sono chiesto:

{:refdef: .centerbig}
<u>Qual è la cucina più "famosa" del mondo (su Wikipedia)?</u> [^2] [^3]
{: refdef}

Posta così è una domanda vaga. Entrando nel dettaglio:

* **Cucina**: intendo cucina nazionale, quindi escludendo quelle regionali
* **Famosa**: è difficile quantificare quanto una pagina su Wikipedia sia "famosa"[^4]. Ho usato come metro di giudizio la lunghezza della pagina in caratteri[^5]
* **Wikipedia**: esistono ben **303** [edizioni linguistiche di Wikipedia](https://it.wikipedia.org/wiki/Edizioni_linguistiche_di_Wikipedia) attive. La stessa pagina, lunghissima in una lingua, potrebbe essere solamente uno [stub](https://it.wikipedia.org/wiki/Wikipedia:Stub) (un *abbozzo*) in un'altra

In parole povere, per ogni cucina nazionale ho misurato la lunghezza della pagina in ogni sua edizione linguistica, producendo grafici intuitivi e facili da consultare

Prima di parlare dell'aspetto tecnico vediamo direttamente i risultati! :)  
*(Ogni grafico è disponibile anche in versione interattiva, tramite l'apposito link. Ne è consigliata la visione da PC)*

## Heatmap (matrice di correlazione) delle cucine su Wikipedia

{: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200922/correlation_heatmap.jpg'}}" title="Matrice di correlazione (heatmap) risultante" class="responsive" onclick="window.open(this.src)">
<a href="{{site.url | append: '/media/20200922/correlation_heatmap.html'}}" target="_blank" rel="noopener noreferrer">↬ Link alla versione interattiva ↫</a>

Ci sono un sacco di cose da dire su questo grafico! Prima di spiegare come è stato realizzato, vediamo come leggerlo e cosa rappresenta!

* Ogni **colonna** rappresenta la cucina di uno stato[^6]
* Ogni **riga** indica una lingua (in cui un'edizione di Wikipedia esiste)[^6]
* Ogni **cella** corrisponde alla pagina di Wikipedia sulla cucina indicata dalla colonna, scritta nella lingua indicata dalla riga (la "cucina italiana in inglese" indica la voce sulla cucina italiana presente nella Wikipedia in lingua inglese)
* Il **colore** di ogni cella rappresenta la lunghezza della pagina (la barra colorata a destra è la legenda)
* I **pallini bianchi** in alcune celle evidenziano ciò che in una matrice di correlazione pura (1:1) sarebbe la diagonale: sono infatti le celle che rappresentano la pagina di una cucina di una certa nazione **X** scritta nella lingua ufficiale di **X**[^7]

Si consideri una porzione di matrice (ottenuta ingrandendo la [versione interattiva]({{site.url | append: '/media/20200922/correlation_heatmap.html'}})):

{: style="text-align: center; padding: 0 10%;"}
<img src="{{site.url | append: '/media/20200922/correlaton_heatmap_zoom.png'}}" title="Un pezzo di matrice" class="responsive" onclick="window.open(this.src)">

Alcune cose interessanti che si possono notare solo dal colore: la pagina sulla [cucina italiana in coreano](https://ko.wikipedia.org/wiki/%EC%9D%B4%ED%83%88%EB%A6%AC%EC%95%84_%EC%9A%94%EB%A6%AC) è decisamente lunga, così come la pagina sulla [cucina israeliana in indonesiano](https://id.wikipedia.org/wiki/Hidangan_Israel)!

### Cucine famose inaspettate

Esplorando la matrice si possono trovare strane combinazioni e cucine inaspettatamente "note e ben documentate" in altre lingue. Ne elenco alcune:

* La pagina della [cucina greca in greco](https://el.wikipedia.org/wiki/%CE%95%CE%BB%CE%BB%CE%B7%CE%BD%CE%B9%CE%BA%CE%AE_%CE%BA%CE%BF%CF%85%CE%B6%CE%AF%CE%BD%CE%B1) (una cella sulla "diagonale") è lunga circa 25000 caratteri (circa 7 fogli A4 stampati con font 12), ma la pagina sulla [cucina tedesca in greco](https://el.wikipedia.org/wiki/%CE%93%CE%B5%CF%81%CE%BC%CE%B1%CE%BD%CE%B9%CE%BA%CE%AE_%CE%BA%CE%BF%CF%85%CE%B6%CE%AF%CE%BD%CE%B1) è lunga ben 93000 caratteri! Forse i greci adorano così tanto la cucina tedesca da non essere interessati alla loro?[^8] `¯\_(ツ)_/¯`
* La [pagina sulla cucina olandese in polacco](https://pl.wikipedia.org/wiki/Kuchnia_holenderska) è estremamente lunga (130000 caratteri)!
* La [pagina sulla cucina statunitense in francese](https://fr.wikipedia.org/wiki/Cuisine_des_%C3%89tats-Unis) (218000 caratteri) è lunga il triplo della pagina sulla [cucina francese in francese](https://fr.wikipedia.org/wiki/Cuisine_fran%C3%A7aise) (70000 caratteri)!

### Osservazioni e disclaimer

* È superfluo dire che la lunghezza di una pagina su Wikipedia non rappresenta il sentimento di un'intera nazione nei confronti di una cucina straniera. Quest'analisi è chiaramente circoscritta a Wikipedia. Ci sono inoltre alcuni fattori da tenere in considerazione:
  * Alcune edizioni di Wikipedia sono [più attive di altre](https://meta.wikimedia.org/wiki/List_of_Wikipedias#All_Wikipedias_ordered_by_number_of_articles) ed hanno mediamente articoli più lunghi
  * Alcune delle voci analizzate contengono solamente elenchi di piatti tipici, casi rappresentativi di come la lunghezza non sia un metro di giudizio così efficace
  * Raffinando ulteriormente questa analisi, il numero di caratteri potrebbero essere normalizzati sulla lunghezza media di una voce per ogni specifica edizione di Wikipedia. Tuttavia, per avere "a colpo d'occhio" un'idea di "quanto è lunga la voce di una determinata cucina", ritengo la normalizzazione superflua e la lascio implementare a chi fosse curioso od interessato
* Le cucine nazionali totali[^9] sono **167**, mentre i linguaggi sono **119**[^10]. La matrice presentata sopra è una versione filtrata (53×36)[^11]. La matrice di correlazione intera è esteticamente interessante ma non molto leggibile. Per chi fosse curioso, la matrice completa (167×119) è le seguente:

{: style="text-align: center; padding: 0 10%;"}
<a href="{{site.url | append: '/media/20200922/correlation_heatmap_full.html'}}" target="_blank" rel="noopener noreferrer">↬ Link alla versione interattiva (con assi etichettati) ↫</a>[^12]
<img src="{{site.url | append: '/media/20200922/correlation_heatmap_full.jpg'}}" title="La gigantesca matrice completa" class="responsive" onclick="window.open(this.src)">

## Statistiche e podio 🏆

Le statistiche presentate di seguito sono state calcolate utilizzando la versione completa del dataset, senza escludere voci o linguaggi nazionali (lingue regionali e dialetti locali sono stati ignorati)[^13]

### Le cucine più "famose" del mondo (somma su tutte le lingue)

{: style="text-align: center;"}
<a href="{{site.url | append: '/media/20200922/cumulative_cuisines_length.html'}}" target="_blank" rel="noopener noreferrer">↬ Link alla versione interattiva ↫</a>
<img src="{{site.url | append: '/media/20200922/cumulative_cuisines_length.jpg'}}" title="Lunghezza complessiva di ogni cucina mondiale, ottenuta sommando le lunghezze nei vari linguaggi" class="responsive" onclick="window.open(this.src)">

Sommando per ogni cucina la lunghezza delle pagine in tutte le lingue considerate, si ottiene la seguente classifica:

{: style="margin: auto;"}

|      | Cucina                                                                 | Lunghezza |
| ---- | :--------------------------------------------------------------------- | --------- |
| 1 🥇 | 🇮🇹 **[Italiana](https://it.wikipedia.org/wiki/Cucina_italiana)**       | 1263679   |
| 2 🥈 | 🇩🇪 **[Tedesca](https://it.wikipedia.org/wiki/Cucina_tedesca)**         | 1016720   |
| 3 🥉 | 🇯🇵 **[Giapponese](https://it.wikipedia.org/wiki/Cucina_giapponese)**   | 981386    |
| 4    | 🇰🇷 **[Coreana](https://it.wikipedia.org/wiki/Cucina_coreana)**         | 912384    |
| 5    | 🇺🇸 **[Americana](https://it.wikipedia.org/wiki/Cucina_statunitense)**  | 893520    |
| 6    | 🇫🇷 **[Francese](https://it.wikipedia.org/wiki/Cucina_francese)**       | 874603    |
| 7    | 🇮🇩 **[Indonesiana](https://it.wikipedia.org/wiki/Cucina_indonesiana)** | 832875    |
| 8    | 🇷🇺 **[Russa](https://it.wikipedia.org/wiki/Cucina_russa)**             | 793379    |
| 9    | 🇮🇳 **[Indiana](https://it.wikipedia.org/wiki/Cucina_indiana)**         | 778534    |
| 10   | 🇳🇱 **[Olandese](https://it.wikipedia.org/wiki/Cucina_olandese)**       | 681041    |

Al primo posto, la **cucina italiana**, con un totale complessivo di **1,26 milioni di caratteri**! :tada:

### Le pagine più lunghe (indipendentemente dalla lingua)

La top 10 delle cucine più lunghe in assoluto (su tutte le edizioni di Wikipedia considerate) è la seguente:

{: .hightable style="margin: auto;"}

|      | Cucina e lingua                                                                        | Titolo in lingua originale | Lunghezza |
| ---- | :------------------------------------------------------------------------------------- | :------------------------- | --------- |
| 1 🥇 | 🇷🇺 **[Russa in polacco](https://pl.wikipedia.org/wiki/Kuchnia_rosyjska)**              | Kuchnia rosyjska           | 363864    |
| 2 🥈 | 🇩🇪 **[Tedesca in russo](https://ru.wikipedia.org/wiki/Немецкая_кухня)**                | Немецкая кухня             | 279328    |
| 3 🥉 | 🇦🇷 **[Argentina in italiano](https://it.wikipedia.org/wiki/Cucina_argentina)**         | Cucina argentina           | 227606    |
| 4    | 🇺🇸 **[Americana in francese](https://fr.wikipedia.org/wiki/Cuisine_des_États-Unis)**   | Cuisine des États-Unis     | 218192    |
| 5    | 🇺🇸 **[Americana in giapponese](https://ja.wikipedia.org/wiki/アメリカ料理)**             | アメリカ料理                 | 190920    |
| 6    | 🇺🇸 **[Americana in inglese](https://en.wikipedia.org/wiki/American_cuisine)**          | American cuisine           | 181443    |
| 7    | 🇮🇩 **[Indonesiana in russo](https://ru.wikipedia.org/wiki/Индонезийская_кухня)**       | Индонезийская кухня        | 175120    |
| 8    | 🇲🇾 **[Malese in inglese](https://en.wikipedia.org/wiki/Malaysian_cuisine)**            | Malaysian cuisine          | 162794    |
| 9    | 🇮🇹 **[Italiana in kannada](https://kn.wikipedia.org/wiki/ಇಟ್ಯಾಲಿಯನ್‌_ಪಾಕಪದ್ಧತಿ)**           | ಇಟ್ಯಾಲಿಯನ್‌ ಪಾಕಪದ್ಧತಿ            | 152911    |
| 10   | 🇦🇷 **[Argentina in spagnolo](https://es.wikipedia.org/wiki/Gastronomía_de_Argentina)** | Gastronomía de Argentina   | 140174    |

Al primo posto, la cucina nazionale più lunga in assoluto: la pagina sulla **[cucina russa (scritta in polacco)](https://pl.wikipedia.org/wiki/Kuchnia_rosyjska)** con ben **363864 caratteri**! :tada:

**Curiosità sul 9° posto**  
Non conoscevo l'esistenza della [lingua kannada](https://it.wikipedia.org/wiki/Lingua_kannada) (una lingua parlata nel sud dell'India) ma a quanto pare sono molto interessati alla [cucina italiana (ಇಟ್ಯಾಲಿಯನ್‌ ಪಾಕಪದ್ಧತಿ)](https://kn.wikipedia.org/wiki/ಇಟ್ಯಾಲಿಯನ್‌_ಪಾಕಪದ್ಧತಿ). Trovo stupendo leggere una pagina scritta in un alfabeto completamente diverso dal nostro e trovare immagini di caffettiere, focacce e tiramisù:

{: style="text-align: center; padding: 0 10%;"}
<img src="{{site.url | append: '/media/20200922/kannada_italian_cuisine.png'}}" title="Pagina sulla cucina italiana in lingua kannada" class="responsive" onclick="window.open(this.src)">

Mi fanno notare che la parte sul [bicerin di Torino](https://it.wikipedia.org/wiki/Bicerin) sembra intraducibile (_"penso esista una parola per dire latte in Kannada"_). Ma le traduzioni incomplete ci sono un po' ovunque su Wikipedia, nulla di troppo strano! :)

### Le lingue con più voci di cucina

{: style="text-align: center;"}
<a href="{{site.url | append: '/media/20200922/cumulative_languages_length.html'}}" target="_blank" rel="noopener noreferrer">↬ Link alla versione interattiva ↫</a>
<img src="{{site.url | append: '/media/20200922/cumulative_languages_length.jpg'}}" title="Lunghezza complessiva per ogni lingua, ottenuta sommando tutte le voci sulle cucine nazionali scritte nella stessa lingua" class="responsive" onclick="window.open(this.src)">

Nessuna sorpresa, l'edizione linguistica di Wikipedia con più voci di cucina è la **[Wikipedia in lingua inglese](https://en.wikipedia.org/wiki/)** 🇬🇧

## Com'è stata fatta questa analisi?

Per evitare una lunga digressione sull'implementazione, citerò le librerie utilizzate e riassumerò a grandi linee il processo di raccolta ed analisi dati, rimandando direttamente chi è interessato ad approfondire alla [repository del progetto su GitHub](https://github.com/albertosantagostino/wiki-cuisines-correlation-heatmap)

**Librerie utilizzate**  
L'intero progetto è stato sviluppato in Python. Le principali librerie utilizzate (gestite con [Poetry](https://python-poetry.org/)) sono le seguenti:

{: style="margin: auto;"}

| Libreria         | PyPi link                                      | Descrizione                                                |
| ---------------- | ---------------------------------------------- | :--------------------------------------------------------- |
| `beautifulsoup4` | [🔗](https://pypi.org/project/beautifulsoup4/) | Manipolazione a basso livello di pagine HTML[^14]          |
| `pandas`         | [🔗](https://pypi.org/project/pandas/)         | Insostituibile, per salvataggio ed analisi dati            |
| `emoji`          | [🔗](https://pypi.org/project/emoji/)          | Per inserire emoji, utilizzata per le bandiere nazionali   |
| `plotly`         | [🔗](https://pypi.org/project/plotly/)         | Un'ottima libreria grafica per creare visualizzazioni[^15] |

**Download ed elaborazione dei dati**  
Ci sono 4 step di preparazione dei dati. Ad ogni step la stessa struttura dati viene arricchita con sempre più informazioni.  
Le funzioni (che corrispondono agli step) sono le seguenti:

* `step1_prepare_cuisines_data`  
  L'elenco di "tutte le possibili cucine" viene ottenuto a partire da questo [template della Wikipedia inglese](https://en.wikipedia.org/wiki/Template:Cuisines). I redirect vengono ignorati e solamente le cucine nazionali vengono considerate. Insieme alle cucine vengono salvati anche gli ID che identificano le singole pagine su Wikipedia
* `step2_populate_other_languages`  
  Per ogni cucina nell'elenco vengono identificate le traduzioni in altre lingue (diverse dall'inglese) della pagina in questione. Titoli ed URL vengono salvati
* `step3_fill_lengths`  
  Tramite delle chiamate alle varie [API](https://www.mediawiki.org/wiki/API:Main_page), si ottengono le lunghezze di ogni pagina da analizzare
* `step4_preprocess_data_frame`  
  La struttura viene convertita da dizionario a `pandas.DataFrame`. In questo step viene effettuato un filtraggio per ridurre la quantità dei dati, che vengono infine salvati in due versioni: `table_dataframe.dat` (versione ridotta) e `table_dataframe_full.dat` (versione completa, per il calcolo delle statistiche assolute)

**Visualizzazione e grafici**  
Un ultimo step (`step5_create_plots`, in `visualization.py`) utilizza le strutture dati ottenute in precedenza per creare grafici, tabelle e statistiche che vengono salvate in immagini, HTML e Markdown

## Conclusioni

Quest'analisi è stata effettuata *just for fun*, per curiosità e per fare qualcosa di nuovo. Detto ciò, sono soddisfatto del risultato ottenuto! È molto interessante cercare strane correlazioni nella heatmap e scoprire cucine e lingue che non conoscevo!

Se trovate qualcosa di curioso o volete provare a creare statistiche simili con una categoria differente di Wikipedia, fatemelo sapere o provate direttamente voi (il codice è come sempre open-source ([repository su GitHub](https://github.com/albertosantagostino/wiki-cuisines-correlation-heatmap)) e rilasciato con licenza MIT)

### Cose (ancora) da fare

Da quando ho iniziato la stesura di quest'articolo ho pensato ad alcuni miglioramenti da fare e a nuovi grafici da produrre. Sono soddisfatto dello stato attuale, ma vorrei implementare in futuro (in ordine di importanza):
* Automatizzare il processo di analisi/pubblicazione dei grafici[^16]. Le voci su Wikipedia cambiano decisamente spesso, quest'analisi potrebbe già essere obsoleta nel giro di qualche mese[^17]
* Aggiungere statistiche che evidenzino le cucine più famose per ogni lingua, <u>escludendo le celle diagonali</u>
* Provare a normalizzare le lunghezze in modo da "far spiccare" le pagine in relazione alla lunghezza media di ogni edizione di Wikipedia
* Considerare anche linguaggi locali, magari provare a creare una versione dedicata ai dialetti italiani[^18]

Grazie per l'attenzione, alla prossima! :)

<br>

[^1]: Mentre [ITAQA](https://albertosantagostino.github.io/blog/2020/05/29/ITAQA_introduction_it) prosegue, ne riparlerò fra non troppo!
[^2]: Restringere il campo a Wikipedia semplifica di molto il lavoro!
[^3]: Dovendo indovinare, avevo già un'idea della [risposta](https://it.wikipedia.org/wiki/Cucina_italiana), ma non potevo dimostrarlo (*non ancora, almeno*)
[^4]: Un posto che raccoglie voci notevoli è la [vetrina](https://it.wikipedia.org/wiki/Wikipedia:Vetrina), ma è solamente un'indicazione binaria
[^5]: Come spiegato più avanti, so che la lunghezza di una pagina non è un'indicazione certa di quanto una voce sia "famosa". Inoltre mi è stato fatto notare che diversi linguaggi hanno diversa [densità di informazione](https://linguistics.stackexchange.com/questions/30408/density-of-information-semantic-of-chinese-and-korean-language-versus-european-l)
[^6]: Ok, lo so, mancano un sacco di nazioni ed un sacco di lingue, più avanti spiego perché
[^7]: Si noti infatti che su alcune righe compaiono più pallini, ad indicare tutti gli stati in cui quella lingua è la più parlata. A questo proposito: in alcuni stati vengono parlate più lingue (Svizzera, Lussemburgo, Belgio...), quindi si dovrebbero vedere colonne con più pallini. Quest'ulteriore livello di dettaglio non è (ancora) implementato
[^8]: Un mio carissimo amico (che adora la cucina greca) ha commentato: "c'è *veramente* poco da dire sulla loro cucina, è riassumibile in: [feta](https://it.wikipedia.org/wiki/Feta), [moussaka](https://it.wikipedia.org/wiki/Moussakà), [gyros](https://it.wikipedia.org/wiki/Gyros), i [cosi con la vite](https://it.wikipedia.org/wiki/Dolma), [olive](https://it.wikipedia.org/wiki/Oliva). Stop."
[^9]: Ovvero tutte le cucine nazionali che sono presenti anche sulla Wikipedia in inglese
[^10]: Ovvero tutti i linguaggi che hanno almeno una voce che parla di una delle cucine nazionali considerate
[^11]: Ho ignorato le voci più corte di 4000 caratteri, le cucine che compaiono in meno di 13 lingue, i linguaggi con meno di 14 pagine riguardanti cucine nazionali e tutte le edizioni di Wikipedia nei vari dialetti locali
[^12]: La versione interattiva ha sull'asse dei linguaggi alcuni prefissi di lingue non convertiti in linguaggi estesi. È comunque interessante da vedere!
[^13]: Statistiche e grafici basate sulla situazione al 04/10/2020
[^14]: Inizialmente contavo di fare quasi tutto con la libreria `wikipedia` ([🔗](https://pypi.org/project/wikipedia/)), ma allo stato attuale è incompleta e non molto ottimizzata. Per questo ho ripiegato sull'approccio di basso livello usando `beautifulsoup`
[^15]: Diciamocelo, `matplotlib` è un po' una zavorra, ci sono alternative come `plotly` che sono leggere e rendono facile produrre visualizzazioni interattive. Devo ancora provare `seaborn` ([sito web](https://seaborn.pydata.org/)), ho letto belle cose
[^16]: Magari provando ad utilizzare direttamente [GitHub Actions](https://github.com/features/actions) (non so quanto sia fattibile, ma volevo metterci mano prima o poi)
[^17]: Da quando ho iniziato a scrivere questo post c'è già stato un sorpasso nella classifica delle cucine: la cucina tedesca ha sorpassato quella giapponese, passando al secondo posto, in seguito ad un massiccio ampliamento della voce sulla [cucina tedesca in russo](https://ru.wikipedia.org/wiki/%D0%9D%D0%B5%D0%BC%D0%B5%D1%86%D0%BA%D0%B0%D1%8F_%D0%BA%D1%83%D1%85%D0%BD%D1%8F) a fine settembre
[^18]: Anche se le edizioni di Wikipedia nei vari dialetti sono abbastanza scarne, non penso abbiano moltissime informazioni sulle cucine delle altre regioni