---
layout: article
title: "AI ovunque, hype, pigrizia e stupidità umana"
lang: it
ref: ai-hype-laziness-stupidity
date: 2026-04-15
---

## Introduzione e prefazione

Questo post è stato decisamente difficile da strutturare e scrivere. È stato rifinito poco alla volta, partendo da una bozza iniziale molto più corta. Un'anteprima su uno dei punti su cui mi focalizzerò dopo - ed una provocazione - è l'osservazione che qualcuno potrebbe fare: *"sarebbe stato molto più semplice scrivere questo articolo con ChatGPT o qualche altro strumento AI!"*. Questo pensiero, e la tentazione offerta, dimostra immediatamente che noi esseri umani siamo davvero efficienti ad essere pigri, di natura. Fare qualcosa richiede energia. E tempo.

(Questo post è totalmente *organico*, scritto da un umano. Se mi conoscete sapete già che è così, se non lo sapevate, buona lettura!)

Un'altra cosa da menzionare è la scelta della prospettiva utilizzata per trattare l'argomento. Ho deciso che questo **non** sarà un articolo tecnico. Non voglio entrare in dettagli di questo tipo, ma rimanere più ad alto livello. Ci sarà una sezione con qualche esempio specifico sull'ingegneria software, ma sono solo un paio e non sono legati al funzionamento di [modelli LLM](https://it.wikipedia.org/wiki/Modello_linguistico_di_grandi_dimensioni)[^f].

Come *teaser*, per anticiparvi il punto principale che porterò più avanti:
{:refdef: style="text-align: center;"}
**chi usa quotidianamente strumenti AI sta diventando sempre ed inesorabilmente più stupido**
{: refdef}
<small>(Se il vostro *attention span* è stato distrutto dal mondo moderno, potete <A href="#sempre-più-gente-stupida">cliccare qui</A>. Ovviamente mi farebbe piacere se leggeste tutto)</small>


## AI ovunque, che gran rottura di palle

Dal **boom LLM/AI** degli ultimi anni (~2023, circa), mi sento sempre più frustrato, deluso, preoccupato e <u>stanco</u> nel vedere 'AI' ovunque. Un sacco di persone stanno usando questa tecnologia nel quotidiano per fare cose estremamente semplici e basilari, e le grosse aziende tech la stanno infilando ovunque, creando *hype* (inteso come clamore, entusiasmo) e spingendo sul fatto che essa sia "il futuro", la soluzione ad ogni problema, che tutti dovrebbero adorare ed utilizzare, per scrivere liste della spesa, pianificare una vacanza, scrivere mail o fare ricerche online. Per <u>tutto</u>.

Sono molto **preoccupato** per vari motivi, e sentivo il bisogno di sfogarmi un pochino[^a], scrivendo un post su questo momento storico così "interessante".

Sono sicuro di non essere l'unico ad avere pensieri simili, ma ho la sensazione che l'entusiasmo (sia questo autentico od artificiale) stia sovrastando le opinioni meno entusiaste e più ponderate.

Nella prossima sezione voglio brevemente parlare dell'*hype* che viene fomentato da alcune aziende, e di come questo sia legato a meccanismi di mercato. Questo non è direttamente collegato al punto centrale che presenterò in seguito, ma non me la sento di tralasciare come - per svariate ragioni, alcune un po' preoccupanti di altre - l'AI stia venendo messa dappertutto. Non c'è bisogno che dimostri la cosa, se avete gli occhi ve ne sarete sicuramente accorti.

### Aziende tech, FOMO ed il "powered by AI" ovunque

Una quantità folle di aziende stanno **infilando l'AI ovunque**. Se prendete a caso un'azienda tech ed aprite il loro sito web, vedrete che sono *"powered by AI"*, un'*"AI-first company"* o qualcosa del genere. La prima ragione (molto semplice è noiosa) si chiama **[FOMO](https://it.wikipedia.org/wiki/Fear_of_missing_out)**, un termine che significa letteralmente *"paura di perdersi qualcosa"*, in questo caso specifico paura di non essere abbastanza aggiornati ed innovativi, e di finire in secondo piano rispetto ai rivali[^n].

🗣 <<Se X, Y e Z stanno mettendo l'AI nel loro prodotto, dobbiamo farlo anche noi, altrimenti nessuno ci sceglierà! Sembreremo vecchissimi!>><br>
👤 <<Ma Franco, siamo una pizzeria... 🍕>><br>
🗣 <<**Chissenefrega**! Generiamo il menù usando l'AI! Mettiamo un chatbot sul nostro sito per aiutare la gente a scegliere la pizza! Che idea geniale! Fichissimo!>>

Credo che questo esempio (un po' semplificato) sia chiaro. Una delle ragioni principali per cui siamo circondati dall'AI è semplicemente... **marketing**. Ci dà la risposta a molte domande come:

- Perché in WhatsApp/Instagram/Telegram è comparso un bottone per chattare con un chatbot?
- Perché quando cerco su Google il primo risultato è un'"AI overview" che spesso sembra sotto l'effetto di droghe pesanti?
- Perché Outlook vuole "riassumere" una mail che ho ricevuto? Non sono più in grado di farlo da solo? Leggere sta diventando così fuori moda?
- Perché ogni sito ha da qualche parte un bottone scintillante con scritto 'AI', sempre con lo stesso layout e design con le stelline (✨)?

Ma le aziende tech non sono le uniche che stanno sbroccando. La mia sensazione è che la quantità di persone genuinamente estasiate da tutto ciò (includendo i *"[vibe coders](https://en.wikipedia.org/wiki/Vibe_coding)"* e gli *[AI bros](https://www.urbandictionary.com/define.php?term=AI+Bro)*) siano più delle persone caute e dubbiose. Un'occhiata rapida a LinkedIn (che diciamocelo, è sempre stato una discarica di persone che si congratulano a vicenda del nulla cosmico) vi mostrerà tutti super in fissa e gasatissimi! L'AI è il futuro! Fantastico! Guadagneremo miliardi![^d] [^r]

Ovviamente, le persone entusiaste fanno sempre più rumore di chi non si unisce a questo *hype train*, quindi spero la mia sia solo una sensazione. In ogni caso mi ritengo preoccupato dall'intera situazione.

### Altre possibili (e più preoccupanti) risposte

Se il marketing è la prima motivazione per cui ogni azienda spinge così tanto sull'AI, possiamo speculare per ore su cosa passi nel cervello di miliardari, CEO e chiunque sia convinto che **rimpiazzare i lavoratori con l'AI** ed altri strumenti analoghi sia un'idea fantastica.

Ci sono moltissime digressioni e tangenti che potremmo iniziare, ma anche assumendo che tutto ciò sia realistico, ovvero che ogni lavoro "da ufficio" sia delegabile completamente all'AI (enorme supposizione), in questo *fantastico* futuro che stiamo descrivendo, ci sarebbero alcuni *piiiccoli* problemi. Per menzionarne solo alcuni:
- Se qualcosa venisse completamente creato e gestito dall'AI, significherebbe che in caso di malfunzionamenti o problemi, nessun'altro sarebbe in grado di debuggarlo, aggiustarlo o rifarlo da capo, effettivamente facendo perdere a noi esseri umani alcune conoscenze tecniche di base[^e]
- La disoccupazione legata ad impieghi tecnici sarebbe talmente alta che moltissime persone non sarebbero in grado di spendere, incidendo sull'economia in modi inconoscibili. O forse crediamo in un futuro idilliaco in cui i robot fanno tutti i lavori noiosi e ripetitivi e tutti noi siamo felici, gli utili sono distribuiti dalle grandi aziende a tutti, in modo da avere più tempo libero per hobby/arte ed altre attività analoghe? Ha!
- *Quis custodiet ipsos custodes?* è una frase latina dalle [Satire](https://it.wikipedia.org/wiki/Satire_(Giovenale)) che significa *"chi sorveglierà i sorveglianti stessi?"*. In quest'ottica, possiamo chiederci chi sarà la persona o l'ente "in carica" in questo futuro AI-centrico? Che pesi e contrappesi verranno applicati? Da chi? Molto inquietante ed estremamente attuale, considerando anche il contesto geopolitico recente

Ok. Ora, mettiamo da parte tutte queste potenziali digressioni ed immaginiamo che tutto questo sia un trend, una moda, che ad un certo punto passerà. Le aziende inizieranno a realizzare che infilare ovunque l'AI [non è così redditizio](https://fortune.com/2025/11/12/openai-cash-burn-rate-annual-losses-2028-profitable-2030-financial-documents/), la [bolla](https://en.wikipedia.org/wiki/AI_bubble) scoppierà (speriamo!). Andiamo oltre.

Se stiamo accantonando anche questo discorso, qual è allora il mio problema principale con l'utilizzo quotidiano dell'AI da parte di singoli individui?

## Paletti e presupposti finali

Devo fare un bel po' di *disclaimers*! L'argomento è così vasto che devo mettere dei **paletti** per definire meglio il mio discorso, e poi fare qualche **supposizione**, prima di andare al punto.

- Come avrete notato, ho ceduto anche io. Sto chiamando 'AI' - come la maggior parte delle persone oggigiorno fa - tutti i chatbot, tool, agenti, applicazioni che usano LLM per generare testo/codice. Sono ancora convinto che **'AI' sia un termine estremamente improprio**, ma non voglio aprire il vaso di Pandora sul *"che cos'è la coscienza"* o divergere verso altre questioni filosofiche. Questo allungherebbe ancora di più questo post, con considerazioni che non sono il mio focus al momento. Mettiamo da parte la cosa, e concordiamo sul fatto che per questa discussione l'AI è un generico strumento software[^g].
- Mi concentrerò su **modelli LLM che producono testo**, sia questo un messaggio, del codice, un articolo, una ricetta, una presentazione, una procedura, un report, qualsiasi cosa testuale. Ci sono altri tipi di AI generativa, fra i più noti quelli che producono immagini o video (DALL·E, Sora, Stable Diffusion, Nano Banana, per citarne alcuni). Ho opinioni anche su questi strumenti (lavori artistici rimpiazzati, deepfakes, disinformazione...), ma non è rilevante per questo post[^b].

Infine, per ridurre e semplificare il più possibile la discussione, assumerò alcune ipotesi di partenza (che sono totalmente false) ma che dirotterebbero in un'altra direzione il discorso. Di seguito, una lista di fatti sull'AI attuale, che **ignorerò volutamente** e dimenticherò per il resto del post.

- Ignorerò l'enorme problema del **[consumo di energia ed acqua](https://en.wikipedia.org/wiki/Environmental_impact_of_artificial_intelligence)** di tutti questi strumenti, e dell'**[approvvigionamento di chips](https://en.wikipedia.org/wiki/2024%E2%80%93present_global_memory_supply_shortage)** che sta colpendo il mercato globale. Facciamo finta che i modelli LLM attuali siano super efficienti e che possano funzionare senza consumare un sacco di risorse, tale da richiedere [data centers dedicati](https://en.wikipedia.org/wiki/AI_data_center)
- Ignorerò il fatto che tutti i più famosi chatbot (ChatGPT, Gemini, Claude,...) sono sviluppati dalle "solite" **megacorporations** che nel migliore dei casi se ne fregano della privacy degli utenti, e nel peggiore dei casi sono malvagie aziende iper-capitaliste e tecno-fasciste, interessate esclusivamente ad una cosa: gli utili. Sembra che un sacco di gente oggigiorno stia usando i chatbot come amici o confidenti, senza pensare due volte a quanti dati personali stanno condividendo. Umanizzare questi strumenti e renderli accessibili in applicazioni "di chat" è una chiara strategia per presentare l'AI con un messaggio come: *"hey, stai chattando con un amico, puoi dirgli qualsiasi cosa su di te, sono qua per ascoltarti! Non farti problemi a condividere tutto!"*. La mia sensazione è che stia funzionando molto bene e che le persone ci stiano cascando[^i]. Sto divagando troppo. Siamo nella sezione dei presupposti. Per questo punto, ignoriamo chi c'è dietro le quinte, ed immaginiamo che tutti i tool AI non condividano dati con nessuno, e che vengano eseguiti in locale. Nessun rischio legato alla privacy.
- Parzialmente legato al punto precedente, ignorerò anche il grande discorso del **training data**, punto che viene discusso raramente fra persone non tecniche. I dati utilizzati per fare il training di un modello riflettono le "conoscenza" che esso ha e le risposte che può dare. Siamo davvero sicuri che è nell'interesse di ogni azienda fare in modo che i dati di training siano i più "democratici" e "super partes" possibili, senza avere alcun bias? Ne dubito fortemente. Ma anche qua, ipotizziamo che un dataset imparziale, perfetto, che include in esso tutta la conoscenza umana esista e sia usato in tutti questi modelli. Fantastico!
- Infine, e forse l'ipotesi più esagerata di tutte, ignorerò il fatto che tutti questi modelli hanno ancora spessissimo quelle che in gergo vengono definite **[allucinazioni](https://it.wikipedia.org/wiki/Allucinazione_(intelligenza_artificiale))**, ovvero risposte false e sbagliate, che vengono presentate come vere e corrette. Sia i modelli "di base" (come "Google AI Overview") che quelli più avanzati sono ancora interessati dalla cosa. Magari col tempo la cosa migliorerà, ma al momento è ancora un problema concreto. Di nuovo, per il resto di questo post, ignorerò la cosa, fingendo che tutti questi modelli sono perfetti, e che rispondono sempre in modo accurato e senza sbagliare, in modo infallibile.

Finiti finalmente tutti i *disclaimers*, tuffiamoci nel cuore del post (*e nel punto più controverso, immagino*).

## Sempre più gente stupida[^s]

**Sono davvero stanco delle persone che usano l'AI quotidianamente**, senza pensarci due volte. In generale. Per tutto, siano esse cose semplici che richiedono solo un piccolo sforzo[^c], che attività più complesse, che richiedono molti più "neuroni" e creatività.

Possibile controargomentazione: *"ma Alberto, l'AI è uno strumento, dipende da come lo usi, ha un sacco di potenzialità se usato nel modo giusto!"*

Risponderò in dettaglio dopo, e sono *parzialmente* d'accordo. In ogni caso, il mio pensiero rimane:
{:refdef: style="text-align: center;"}
<strong><u>le persone che usano spesso l'AI</u> per produrre qualcosa,<br><u>stanno diventando</u> ogni giorno inesorabilmente <u>più stupide</u></strong> 
{: refdef}

*"Wow, calmo! Che opinione esagerata, come sempre!"*

Certo, assolutamente, ho scritto questo post per lamentarmi di come vedo utilizzare l'AI e dell'*hype* che si sta formando intorno ad essa. Non sto perdendo tempo a scrivere un'opinione moderata e pacata.

Sono inoltre convinto che **l'utilizzo attuale dell'AI porterà solo cose negative sul lungo termine**, in maggior misura rispetto ad altre "tecnologie innovative" degli ultimi anni che erano state pubblicizzate anch'esse come "il futuro" e che non hanno portato nulla di utile (blockchain, IoT, domotica[^h], NFT...)

Per entrare più nel dettaglio della potenziale controargomentazione di prima: trattare l'AI come un tool, adottando il giusto atteggiamento, con un occhio critico, dovrebbe risolvere il problema, no? Sono più o meno d'accordo, posso ovviamente vedere l'utilità, ma la mia paura è: anche una persona che la usa con moderazione e con le giuste accortezze, sul lungo andare potrebbe abituarsi troppo (diventandone assuefatta) e finire per usarla per fare ogni cosa, ogni giorno.

Detto ciò, la prossima sezione riporta alcuni esempi di utilizzo in cui posso vedere dei benefici, sempre se fatto con cura.


## "È uno strumento, dipende da come lo usi"

Inizierò subito con una controargomentazione. Credo ci siano casi concreti nei quali alcuni **strumenti AI possano risultare utili**, con alcuni accorgimenti. Farò alcuni esempi concreti, tutti collegati con la programmazione ed il software[^j].

- **Leggere ed esplorare documentazione estesa** può essere difficile. Avere la possibilità di "chattare" con un documento può essere molto utile, specialmente mentre si lavora con *frameworks* complessi. Usare un chatbot per ottenere una prima risposta, o per fare un po' di *brainstorming*, può aver senso. Ovviamente lo step successivo fondamentale è andare direttamente alla fonte per controllare cosa c'è scritto nel documento originale. Ovviamente anche senza AI è possibile cercare nei documenti, ma può essere un modo utile per "cercare in modo interattivo", se fatto con criterio.
- Avere un tool per **cercare e sostituire 'intelligente'** può essere molto utile. Ad esempio, adattare molti *unit tests* può essere difficile. Poter scrivere un prompt per richiedere un cambiamento di massa[^q] è qualcosa in cui vedo del valore e che può poi essere verificato in un secondo tempo 
- Attività di **data transformation**, ovvero convertire dati da una rappresentazione ad un'altra, può essere fatto velocemente. Ad esempio, prendere 10 diverse tabelle (con schemi differenti) come input ed unirle tutte in una può essere fatto con uno script, ma sicuramente un tool per utenti non tecnici può essere utile
- Supportare uno sviluppatore nell'**esplorare codice mai visto in precedenza**, oppure nel processo di **revisione di codice**, sono altri casi d'uso che, se ben pensati ed implementati, possono velocizzare alcune attività

Ci sono sicuramente altri casi in cui questi strumenti possono aiutare, ma notate come sto ignorando l'elefante nella stanza: **scrivere codice o produrre qualcosa da zero**

## Dall'utilizzo sporadico al non essere più in grado di pensare

Ho scritto poco sopra che *"le persone stanno diventando sempre più stupide"*, ma poi ho presentato alcuni esempi di "usi sensati per l'AI". Mi sto contraddicendo? Non ho un'opinione un po' esagerata? No.

Arriviamo così al cuore del mio discorso: quando parliamo di **produrre** qualcosa in modo creativo, usare l'AI significa **delegare l'intero processo ed il ragionamento necessario** dal nostro cervello ad un tool, ed è qua che vedo grossissimi rischi.

Possiamo tutti concordare che **produrre qualcosa** (del codice, un libro, un post, un messaggio, una mail, una presentazione) sia **impegnativo**. Richiede concentrazione, ragionamento, pensiero critico, e l'abilità di rifinire qualcosa finché non si è soddisfatti con il risultato finale. **Lavorare su qualcosa ci insegna come farlo, migliorandoci**[^k].

Intendo questa cosa nel senso più ampio, il processo stesso di creare qualcosa, imparando da eventuali errori, rende le persone più intelligenti. Il modo di dire *"sbagliando si impara"* ha molto senso. Se rimuoviamo completamente il tempo necessario per rifinire qualcosa, capire perché non funziona, provare ad aggiustarlo ed infine perfezionarlo in modo autonomo, stiamo togliendo tutta la parte di apprendimento[^l].

Peccato per la **pigrizia umana**, il tratto ci ha fatto fare grandi passi avanti come specie, ma che ha anche un sacco di lati negativi. Siamo tutti *molto bravi* ad essere pigri. Il progresso umano è spesso giustificato da *"questa cosa ci farà spendere in qualche modo meno energia"*. Non è una cosa negativa, è progresso. Non dobbiamo più cacciare, possiamo far crescere il cibo vicino al nostro villaggio, viviamo in un mondo derivante dall'automazione industriale, e così via. Potremmo fare mille esempi.

Ma ora, ho la sensazione che ci stiamo lanciando in una nuova preoccupante stagione di "riduciamo anche **quanto dobbiamo pensare**, dopotutto richiede un sacco di energia!"[^o]

*"Ma aspetta, aspetta! Calcolatrici, computer, smartphone, ci sono così tanti esempi di oggetti che ci fanno pensare 'meno' e che oggigiorno sono normalissimi strumenti! Sei veramente un anziano, Alberto, ti stai lamentando del progresso stesso!"* 👴🏻

Forse. Ovviamente è una critica sensata. Ed è al contempo vero che non dover più fare operazioni "a mano", così come non scrivere più con carta e penna, ci sta rendendo meno abili in queste cose, ci sono aree dedicate del cervello che non vengono più attivate spesso come prima. E non fraintendetemi, sono il primo a dire che non è una cosa negativa, in quanto ci rende la vita più semplice.

Ma, se risolvere un'operazione con una calcolatrice ci fa risparmiare tempo, che possiamo usare per pensare di più, avere l'intero ragionamento fatto da strumenti AI significa delegare ad essi un sacco di fasi che sono legate al sapere produrre un buon risultato. Essere in grado di esprimere bene le proprie idee, rifinirle, usare l'introspezione e l'autocritica prima di presentare un prodotto finale viene completamente **annullato dall'utilizzo dell'AI**, mentre in contemporanea ci viene anche *rubata* l'intera esperienza formativa.

Scrivi un prompt, controlla l'output a grandi linee, scrivi un altro prompt, controlla ancora, riscrivi il prompt, e così via. Il risultato del tuo lavoro non è più veramente "tuo". Il tuo ruolo è semplicemente tirare leve e premere bottoni per convincere un qualcosa a vomitare fuori un risultato che sembra abbastanza decente e che puoi poi spacciare per tuo

Vogliamo veramente **delegare la nostra abilità di pensare e scrivere** ad un tool? Stiamo già perdendo un sacco di *skills* in svariati ambiti. Siamo viziati dalla tecnologia, che non è una cosa malvagia *per se*, ma il compromesso è: spendere meno energia facendo tutto più facilmente in cambio di essere meno autonomi ed indipendenti, in generale.

La distopia sulla navicella spaziale in [Wall-E](https://it.wikipedia.org/wiki/WALL-E) faceva molto ridere all'epoca, sembrava divertente e molto lontana: umani incapaci di camminare, coccolati da un'AI, intrattenuti costantemente, incapaci a vivere. Oggi [mi fa ridere un pochino meno](https://www.youtube.com/watch?v=v2hTFoNnmNg). 

### A non tutti piace pensare troppo

Il mio lavoro consiste nel pensare e **scrivere**. Scrivo task per altre persone, scrivo documentazione, scrivo ad altre persone per comunicare in maniera chiara e puntuale. Richiede tempo ed energia, ma non mi pesa. **Non rinuncerei a tutto ciò** solo perché un tool AI è più veloce di me. Non vedo alcun progresso in tutto ciò, ma solo un modo orribile per diventare tutti più stupidi, mentre un'azienda giustifica il cambiamento nel nome di una maggiore efficienza o di maggiori profitti, come al solito[^p].

Le cose che ho scritto in questo post non suoneranno "giuste" a tutti voi. A molte persone non piace il proprio lavoro o semplicemente **non interessa** come si arriva ad un risultato. Se il tempo usato per pensare può essere annullato o ridotto - usando quindi meno energia - perché no? Perché sentirsi in colpa nel fare ciò? Se questa è la vostra opinione, non posso fare nulla per cambiarla. Sto semplicemente presentando la mia prospettiva, e posso solo sperare che il futuro tetro che sto ipotizzando, dove tutti noi non siamo più in grado di pensare e passiamo la nostra giornata a scrivere prompt per l'AI, sia davvero molto molto lontano. 

## Ed ora? Il senso di questo post?

Non mi aspetto di aggiustare il mondo con un post, ma la situazione corrente, con aziende che spingono per l'utilizzo dell'AI ovunque ed alcune persone super entusiaste è veramente.

Personalmente, non uso l'AI. Il mio suggerimento per voi è di fare lo stesso.

Se non per il mio "punto principale" (diventare stupidi), potete rileggere la <A href="#paletti-e-presupposti-finali">sezione sui presupposti</A>. Tutti gli *"ignorerò..."* che ho ipotizzato sono in realtà **problemi reali**, sufficientemente convincenti per rivalutare l'utilizzo di tutti questi strumenti che ci vengono propinati.

Non penso che cambierò la mia opinione su tutto ciò a breve. Mi piace scrivere e pensare, in generale. L'idea di avere una *scorciatoia magica per fare tutto* è una forte tentazione, ma sono convinto che il processo di creare qualcosa ci renda migliori ed è **una delle cose più importanti che ci rende umani**.

Grazie per l'attenzione.

[^a]: In realtà, devo sfogarmi un bel po'. Volevo scrivere qualcosa sulla situazione da un paio di anni. Di recente, vedendo l'hype generale sempre presente e la bolla AI non ancora scoppiata (per ora), ho deciso che era il momento. La mia riluttanza a scrivere online (cosa che non faccio più) è anche legata all'idea che questo post verrà fagocitato da diversi *crawlers* per fare training di modelli AI. Questo succederà di sicuro, e anche se non mi fa impazzire l'idea, non ci posso fare nulla, chissà cosa vomiterà fuori un qualche modello AI prendendo spunto da tutto ciò. *What a time to be alive!* 
[^b]: Come potete immaginare, queste opinioni sono negative. Che sorpresa. Lasciatemi solo dire una cosa ovvia e tristemente vera: quando in passato qualcuno diceva: "l'AI rimpiazzerà il lavoro", nessuno avrebbe scommesso che i primi lavori ad essere sostituiti sarebbero stati quelli artistici (disegnatori, fotografi, artisti visuali...)
[^c]: Ad esempio per scrivere in una mail una serie di step da fare, per i quali era cruciale l'autore avesse pensato bene a tutto, risultando invece più prolissa e più vaga
[^e]: Una storia breve consigliata è [Nove volte sette](https://it.wikipedia.org/wiki/Nove_volte_sette) di Asimov, del 1986. Trama: *in un lontano futuro, gli umani vivono in una società mantenuta dai computer e hanno dimenticato le basi della matematica, compresa la capacità di contare...*
[^g]: Personalmente non credo che i modelli LLM e i tool che abbiamo oggigiorno abbiano alcun tipo di coscienza, ma potremmo aprire una lunga ed interessante discussione sulla domanda *cosa siamo noi allora?* e parlare di [stanza cinesi](https://it.wikipedia.org/wiki/Stanza_cinese), [pappagalli stocastici](https://it.wikipedia.org/wiki/Pappagallo_stocastico) e così via per ore intere
[^h]: La domotica esiste ancora, ma non nella forma in cui veniva pubblicizzata all'inizio. Inoltre, se lo consideriamo progresso, un sacco di gente ha dispositivi *"smart"* Amazon o Google in casa (Echo, Alexa), con microfoni sempre accesi, utilissimi per dirvi che tempo farà domani e farvi risparmiare quei 10 secondi che sarebbero serviti per prendere un telefono e cercare - ma hey, almeno avrete più tempo per fare *doomscrolling* su Instagram o TikTok per ore! Ottimo per la vostra salute mentale!
[^d]: Su questo clima generale di entusiasmo, è veramente facile oggi usare strumenti AI per creare un sacco di account fasulli che postano commenti/articoli su quanto l'AI sia fighissima e sia il futuro. Questa non è una novità, esiste una teoria del 2016 che si chiama [teoria di Internet morto](https://it.wikipedia.org/wiki/Teoria_di_Internet_morto). Oggi, con chatbots sempre più accessibili, incappare in ricette, articoli, commenti generati da AI è praticamente una certezza. Notate come su Wikipedia sia definita una "teoria del complotto". ma c'è una [discussione attiva](https://en.wikipedia.org/wiki/Talk:Dead_Internet_theory#%22Conspiracy_theory%22) se rimuovere questa dicitura. Molti di noi sono in grado di capire quando qualcosa non è scritto da un umano, ma se lo stile di scrittura delle AI "migliorerà" fino a diventare indistinguibile, siamo veramente contenti dell'idea di girare su un Internet pieno di notizie farlocche e "persone" finte?
[^i]: E qua mi chiedo per cosa usino tutti questi dati queste aziende così buone. Semplicemente vendere i dati ad aziende pubblicitarie? Oppure, mettendo un *tinfoil hat*: è davvero uno sforzo di immaginazione pensare che alcune aziende possano usare l'AI per "polarizzare" alcune persone, convincendole di qualcosa, magari estremizzando alcune loro idee? Suona come una "teoria del complotto" ma sarebbe davvero facile da implementare oggigiorno usando questi strumenti
[^j]: È il mio lavoro e conosco bene l'ambito, ma ci sono sicuramente altri casi in cui l'AI può "rendere più facile" il lavoro di qualcuno, non ho dubbi
[^k]: Vedi anche [costruttivismo (psicologia)](https://it.wikipedia.org/wiki/Costruttivismo_(psicologia)): *“[...] chi apprende si trova di fronte ad una sorta di perdita di equilibrio con la propria comprensione precedente, ciò richiede un cambiamento nella struttura cognitiva. Questo cambiamento combina efficacemente le informazioni precedenti e quelle nuove per formare uno schema cognitivo migliorato”*
[^l]: Un'altra storia da ingegnere software. Quando ho iniziato a lavorare, ~10 anni fa, i primi mesi sono stati un continuo di provare a far cose, debuggare, sbagliare, correggere codice, leggere errori, debuggare, capire gli errori, frustrazione, altri errori, e così via, finché l'errore non viene finalmente identificato e risolto. Questo processo è sicuramente frustrante ed impegnativo, ma è essenziale per costruire una *forma mentis*, imparare come affrontare un certo tipo di problema. Un ingegnere software junior/sviluppatore nel mondo di oggi potrebbe banalmente usare ChatGPT (o Copilot od un altro strumento AI) per risolvere il problema senza nessun bisogno di capire come qualcosa funziona, in questo modo:

    {: style="text-align: center; padding: 0 20%;"}
    <img src="{{site.url | append: '/media/20260499/dev_box_ita.png'}}" title="Dev in the loop" class="responsive" onclick="window.open(this.src)">
    {: }
Potete vedere come il ruolo dello sviluppatore sia essere una "mano stupida". È una parte meccanica, scrive un prompt, riceve una risposta, copia-incolla qualcosa in un terminale, guarda se ci sono errori, e ripete il processo finché "qualcosa funziona". Se vi piace quest'idea e pensiate che sia una figata di processo, non penso che io possa farvi cambiare idea, siamo persone diametralmente opposte

[^m]: Sono il primo che se deve andare in un posto nuovo immediatamente usa Google Maps/Waze senza nemmeno provare ad arrivarci in modo autonomo. Anche questo, navigare senza usare un'applicazione GPS, è una cosa che stiamo perdendo, magari meno "essenziale", ma funziona come esempio
[^n]: Detto ciò, quanto un'azienda utilizza strumenti AI varia molto da caso in caso. Sono pronto a scommettere che una grossa parte di aziende che si vantano di essere *"AI first"* semplicemente pagano un sacco di soldi ad OpenAI o qualcosa di analogo per usare le loro API e far vedere ai clienti quanto è figo il loro chatbot che interagisce con loro sul sito
[^o]: Su questo punto, sono sicuro che eravamo già lanciati in questa direzione da un po' di anni. Social networks, dipendenza da smartphone, sempre meno libri letti, non devo aggiungere altro. Sono comunque preoccupato che l'AI sia la pietra tombale 
[^p]: Inoltre, un'altra potenziale ragione per cui le aziende spingono ad usare l'AI è per fare training dei vari modelli e potenzialmente in futuro rimpiazzare i lavoratori con AI *agents*. Dopotutto le *buzzwords* e cose su cui le aziende spingono sono sempre le stesse: efficienza, velocità, taglio dei costi... Penso comunque che tutto ciò non funzionerebbe concretamente, ma nulla fermerà le idee fomentate dai soliti vecchi meccanismi aziendali ignoranti
[^q]: Le regex esistono già per questi casi, ma questo esempio degli unit tests è concreto, basato su feedback di un collega. Fare un gran numero di cambiamenti in sezioni diverse, in modi leggermente diversi a seconda del caso, diventa semplice da fare con un prompt ben scritto e definito
[^f]: Entrando velocemente nei dettagli, i modelli LLM (dire "modelli LLM" è un acronimo ricorsivo/sbagliato - ma in questo post lo faccio comunque perchè suona meglio) sono la famiglia di modelli linguistici attualmente alla base dei chatbot odierni (GPT, PaLM, Gemini, LLaMA), che comunemente vengono tutti inglobati dal termine ombrello 'AI' ('IA' in italiano)
[^r]: Shhh! Non chiedete mai "sì, ma come guadagneremo questi miliardi?" a tutte queste aziende, non è una domanda carina da fare! La risposta è ovvio, no? Con l'AI! Step 1: AI - Step 2: ??? - Step 3: SOLDI!
[^s]: Non fraintendetemi, la stupidità esiste da quando esistono gli umani! Avevamo un sacco di gente stupida prima dell'AI, e ne avremo per sempre finchè l'ultima persona sulla terra morirà. La mia preoccupazione è come stanno degenerando le cose ed il fatto che stumenti come questi possano <u>velocizzare</u> di molto quanto le persone si rincoglioniscono
