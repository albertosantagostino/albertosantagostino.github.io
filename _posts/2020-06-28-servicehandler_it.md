---
layout: article
title: "Servicehandler: una libreria per ghermirli..."
lang: it
ref: servicehandler-introduction
date: 2020-06-28
---

Mi piacerebbe parlare di un altro progettino che mi ha tenuto occupato ultimamente (oltre ad [ITAQA]({{site.url | append: '/blog/2020/05/29/ITAQA_introduction_it'}}), su cui sto ancora lavorando!): lo sviluppo di una piccola libreria Python in grado di gestire ed orchestrare servizi (o *daemon*) in Linux.

## Bot fantastici e dove hostarli

Ultimamente ho sviluppato quattro **bot di Telegram** usando la stupenda libreria [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot).  
Per chi non sa cosa sia un bot di Telegram rimando a [questa pagina](https://core.telegram.org/bots) (in inglese). Brevemente, in questo contesto un bot è un'applicazione in grado di interagire con utenti/gruppi direttamente su Telegram, rispondendo a messaggi ed accettando comandi.

Alcuni di questi bot saranno probabilmente oggetto di post futuri, per ora però voglio parlare del loro hosting e della loro gestione.

### Hardware

Un bot è un'applicazione come un'altra (in questo caso specifico, uno script Python). Per poter interagire con essa in qualunque momento, occorre che sia costantemente in esecuzione. Due sono le soluzioni possibili:

* **Hosting su servizi esterni**  
  Servizi come [Microsoft Azure](https://azure.microsoft.com/en-us/), [Heroku](https://www.heroku.com/), [OpenShift](https://www.openshift.com/), [Amazon AWS](https://aws.amazon.com/) mettono a disposizione macchine virtuali (VMs) per diversi scopi, nelle quali è possibile eseguire applicazioni in modo continuato. Quest'alternativa è indubbiamente la più semplice (la macchina è accessibile ovunque, sempre attiva, con quasi nessuna necessità di manutenzione), ma è anche soggetta a limitazioni quali performance ridotte, un tetto massimo di applicazioni eseguibili in contemporanea, tempi di risposta limitati.
  Sebbene quasi tutti i servizi elencati propongano piani gratuiti per progetti non commerciali, ottenere una macchina con performance migliori significa investire una piccola cifra mensile (nell'ordine di ~10€<sub>/mese</sub>).
* **Self hosting su hardware personale**  
  L'alternativa casalinga è utilizzare dell'hardware personale per l'hosting. Ciò è possibile tenendo un computer costantemente acceso (abbastanza scomodo) oppure utilizzando per una piattaforma hardware low-cost e di dimensioni ridotte.

Per diversi motivi[^1] ho optato per la seconda soluzione: hosting su [**Raspberry PI Zero W**](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). Con 512MB di RAM ed una CPU single core da 1GHz, non è esattamente un computer da [TOP500](https://it.wikipedia.org/wiki/TOP500), ma considerando le poche risorse di cui necessitano i miei bot, è abbastanza. I punti forti dello Zero sono l'ingombro minimo, il modulo WiFi integrato e la possibilità di alimentarlo tramite Micro-USB (utilizzando un semplice caricatore da cellulare).

{: style="text-align: center; padding: 0 15%;"}
<img src="{{site.url | append: '/media/20200628/raspberrypizero.jpg'}}" title="Raspberry PI Zero W, pasta for scale" class="responsive" onclick="window.open(this.src)">

### Software

Scelto l'hardware ed installata una distro Linux come Raspberry Pi OS (conosciuto in passato come *Raspbian*) occorre configurare i vari bot in modo che vengano eseguiti automaticamente all'avvio del sistema.

Il modo più semplice per avviare applicazioni automaticamente è creare dei servizi ad-hoc. Per far ciò si può sfruttare **systemd**, suite di configurazione/amministrazione nativa di ogni sistema Linux. Per ogni nuovo servizio uno **unit file** va scritto e posizionato in `/usr/lib/systemd/user/`:

{: .codeblock}

```ini
[Unit]
Description=Il mio bot

[Service]
ExecStart=/usr/bin/python3 /home/user/bot/main.py
Environment=PATH=/bin:/usr/bin:/usr/local/bin
WorkingDirectory=/home/user/bot/

[Install]
WantedBy=multi-user.target
```
Finalmente, è sufficiente indicare quali servizi vanno avviati automaticamente utilizzando il comando `systemctl --user enable MyBot.service`.

Tutto fatto. Basta avviare il Raspberry, dimenticarsene, ed avere tutto funzionante alla perfezione per sempre.

Fantastico.

{: style="text-align: center; padding: 0 20%;"}
<img src="{{site.url | append: '/media/20200628/jobdone.jpg'}}" title="Tutto fatto, andiamo a casa" class="responsive" onclick="window.open(this.src)">

Non fosse per un piccolo dettaglio: spesso[^2] le cose non vanno come previsto, quindi potrebbe essere utile dover riavviare i bot, controllare i loro log, terminarli forzatamente se necessario, e così via. Tutte cose facili da effettuare quando connessi alla stessa rete del Raspberry, più complesse da remoto.[^3]

Sarebbe fantastico poter effettuare queste operazioni in modo semplice da qualsiasi posto, magari... creando un altro bot...

Sarà un umile gestore di altri bot, con un nome modesto ed un'immagine profilo sobria. Non vorrei creare un malvagio sovrano indiscusso.

{: style="text-align: center; padding: 0 20%;"}
<img src="{{site.url | append: '/media/20200628/lordofthebots.jpg'}}" title="Un bot umile e per nulla prepotente" class="responsive" onclick="window.open(this.src)">

_Mh._

## Una libreria per ghermirli e nel buio incatenarli

Un ~~malvagio bot con brame di potere~~ bot controllore[^4] non può fare nulla se non è in grado di interagire e controllare servizi `systemd`. Ciò che serve è una libreria in grado di wrappare `systemctl`.

Chi ha già usato Python sa perfettamente che esiste una libreria per qualsiasi cosa.[^5]
Ho cercato in giro qualcosa che facesse al caso mio. Non avendo trovato nulla che corrispondesse a ciò che mi serviva, ho deciso quindi di crearne una.

## systemd-servicehandler

La libreria si chiama systemd-servicehandler, o più semplicemente **servicehandler**.[^6]

{: style="text-align: center; padding: 0 15%;"}
<img src="{{site.url | append: '/media/20200628/servicehandler_banner.png'}}" title="Lo stupendo banner di servicehandler" class="responsive" onclick="window.open(this.src)">

(Sono molto orgoglioso del banner)

**Stato attuale**

*servicehandler* è in fase sperimentale, non è nulla di superlativo ma attualmente funziona. Vanno indubbiamente ancora implementate alcune funzionalità, aggiunti test ed effettuati alcuni miglioramenti.

Non esistendo ancora una libreria simile ho deciso di impacchettarla e distribuirla su **PyPI** ([servicehandler su PyPI](https://pypi.org/project/servicehandler/)), in modo che possa essere utilizzata da altri sviluppatori tramite pip (`pip install servicehandler`).

Attualmente le funzionalità di base (astrazione di servizi e metodi per il controllo[^7]) sono implementate, rendendo possibile controllare un bot (o un qualsiasi servizio) in questo modo:

{: .codeblock}
```python
import servicehandler as sh

# Crea un oggetto ServiceHandler che rappresenta il servizio del bot
my_bot = sh.ServiceHandler('Bot','MyBot.service')

# Controlla lo stato del bot
my_bot.state()
<ServiceState.STOPPED: 2>

# Avvia un bot
my_bot.start()
Bot changed state to ServiceState.STOPPED
<Response.OK: 1>
    
# Ferma il bot
my_bot.stop()
Bot changed state to ServiceState.RUNNING
<Response.OK: 1>
```

### Prossimamente

Alcune cose da implementare in futuro:

* Possibilità di includere/monitorare log o file rilevanti nel contesto di un oggetto ServiceHandler
* Creazione di una "classe watchdog" in grado di monitorare più oggetti ServiceHandler e di reagire automaticamente secondo regole definite dall'utente
* Esplorazione del controllo di servizi di sistema (necessari diritti di root)

Come gli altri progetti di cui parlo in questo blog, anche *servicehandler* è completamente open-source e consultabile su GitHub: **[servicehandler](https://github.com/albertosantagostino/systemd-servicehandler)**.

A presto, al prossimo articolo!

<br>


[^1]: So che una qualsiasi macchina virtuale della fascia gratuita sarebbe bastata. Tuttavia cerco di massimizzare il "fai-da-te" nei miei progetti. Inoltre ho scelto di riesumare il povero RPi Zero da un paio di anni vede solamente l'interno di un cassetto. Si sarà annoiato, povero
[^2]: Sempre
[^3]: È ovviamente possibile configurare port-forwarding od utilizzare VNC, sono entrambe soluzioni valide 
[^4]: Chi controllerà i controllori? Ovviamente LordOfTheBot deve essere controllato manualmente (per esempio tramite SSH). Deve avere un design robusto, che lo renda il più possibile affidabile e stabile
[^5]: <a href="https://xkcd.com/353/">xkcd: Python</a>
[^6]: Mi rendo conto di aver perso l'occasione di chiamare la libreria `systemd-onering` o qualcosa di simile, ma un barlume di serietà mi è rimasto (_risate di sottofondo_)
[^7]: Sono disponibili metodi per avviare, fermare, abilitare, disabilitare, killare, ottenere lo stato

