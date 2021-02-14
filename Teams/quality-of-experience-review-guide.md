---
title: Usare CQD per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Informazioni su come analizzare e gestire le prestazioni dei supporti multimediali in tempo reale in Microsoft Teams utilizzando Call Quality Dashboard (CQD).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: f4221b08742d27b4dbe360dfd345142795640588
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581187"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usare CQD per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams 

Questo articolo consente all'amministratore o al supporto e tecnico helpdesk di Teams di sviluppare un processo per il monitoraggio e la gestione della qualità delle chiamate e delle riunioni per l'organizzazione utilizzando Microsoft Teams Call Quality Dashboard (CQD). La nostra guida enfatizza gli scenari di qualità audio perché qualsiasi miglioramento della rete apportato per migliorare l'esperienza audio si tradurrà in miglioramenti nel video e nella condivisione.

Ecco i due modelli [di CQD](https://aka.ms/QERtemplates) curati: è consigliabile scaricarli prima di procedere con le indicazioni fornite in questo articolo.

Questo articolo presuppone che [CQD](turning-on-and-using-call-quality-dashboard.md)sia già stato configurato.


## <a name="categories-to-monitor-and-maintain"></a>Categorie da monitorare e gestire

Dopo l'implementazione di riunioni e voce in Teams, è necessario un piano per il monitoraggio e la manutenzione continui. In questo modo si garantisce che Teams sia sempre in esecuzione in modo ottimale. Questo piano deve includere le aree principali elencate di seguito. È anche consigliabile stabilire gli obiettivi per metriche di qualità e un piano per la risoluzione dei problemi e isolare quando si verificano.

<table>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Qualità delle chiamate</strong></td>
<td>
<p>Suddividere le metriche per chiamate interne (all'interno dell'organizzazione, ad esempio VPN, WiFi, cablate) o chiamate esterne</p>
<p>Suddividere le metriche tramite la creazione o la rete</p>
<p>Chiamate VPN</p>
<p>Chiamate tramite TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Affidabilità delle chiamate</strong></td>
<td><p>Identificare e correggere eventuali problemi di rete o del firewall</p>
<p>Ottenere informazioni approfondite sulle percentuali di errori di impostazione delle chiamate e di eliminazione</p>
<p>Scopri dove si verifica la maggior parte degli errori di impostazione e di eliminazione delle chiamate</p>
</td>
</tr>
<tr class="odd">
<td><strong>Sondaggio utente</strong></td>
<td>
<p>Usare Valuta la chiamata per conoscere l'esperienza effettiva degli utenti</p>
<p>Dove si verificano le esperienze di scarsa qualità?</p>
<p>Mettere in correlazione la scarsa esperienza con la qualità delle chiamate, l'affidabilità e i dispositivi</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivi</strong></td>
<td><p>Scopri quali microfoni e altoparlanti sono usati più comunemente e il loro impatto sulla qualità delle chiamate</p>
<p>Le patch dei driver audio, video, USB e WiFi di supporto vengono regolarmente corretti?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Client</strong></td>
<td>
<p>Scopri quali tipi di client e versioni sono in uso e il loro impatto sulla qualità e l'affidabilità delle chiamate  </p>
</ol></td>
</tr>
</tbody>
</table>

Valutando e correndo continuamente le aree descritte in questo articolo, è possibile ridurre il rischio di influire negativamente sugli utenti. La maggior parte dei problemi degli utenti può essere raggruppata nelle categorie seguenti:

-   Configurazione incompleta del firewall o del proxy
-   Copertura Wi-Fi scarsa
-   Larghezza di banda insufficiente
-   VPN
-   Versioni client e driver non coerenti o obsoleti
-   Dispositivi audio non supportati o incorporati
-   Subnet o dispositivi di rete problematici

Attraverso una pianificazione e una progettazione appropriate prima di distribuire Teams o Skype for Business online, è possibile ridurre l'impegno necessario per mantenere esperienze di alta qualità.

Questo articolo riguarda l'uso di Call Quality Dashboard (CQD) Online come strumento principale per la segnalazione e l'analisi di ogni area, con particolare enfasi sull'audio per ottimizzare l'adozione e l'impatto. Tutti i miglioramenti apportati alla rete per migliorare l'esperienza audio verranno anche tradotti direttamente nella condivisione di video e desktop.

Per accelerare la valutazione, sono disponibili due modelli [di CQD](https://aka.ms/qertemplates) curati: uno è per la gestione di tutte le reti e l'altro è filtrato solo per reti gestite (interne). Anche se i report del modello Tutte le reti sono configurati per visualizzare informazioni relative all'edificio e alla rete, possono comunque essere usati durante la raccolta e il caricamento di informazioni sull'edificio. Il caricamento delle informazioni relative all'edificio in CQD consente al servizio di migliorare la creazione di report aggiungendo allo stesso tempo informazioni personalizzate su edifici, reti e posizione, differenziando al contempo le informazioni interne da subnet esterne. Per altre informazioni, vedere [Mapping dell'edificio.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Destinatari previsto

Questo articolo è destinato a essere usato da stakeholder di partner e clienti con ruoli come Partner Lead/Architect, Consulente, Esperto gestione modifiche/adozione, Supporto/Help Desk Lead, Lead di rete, Cliente potenziale desktop e Amministratore IT.

Questo articolo è destinato anche all'uso da parte del campione di qualità designato. Per altre informazioni, vedere [il ruolo di campione della qualità.](4-envision-plan-my-service-management.md#the-quality-champion-role)


## <a name="what-is-quality"></a>Che cos'è la qualità?

In questo contesto, la qualità è una combinazione di metriche di servizio ed esperienza utente.


### <a name="service-metrics"></a>Metriche di servizio

Le metriche di servizio sono costituite da metriche specifiche basate sul client. Durante ogni chiamata, il client raccoglie la telemetria per la chiamata e invia un report al termine di ogni chiamata, accessibile [in](set-up-call-analytics.md)un secondo momento in Call Call Analytics per utente. Queste metriche includono (ma non sono limitate a):

-   Flusso scadente (in arrivo e in uscita)
-   Tasso di errori di configurazione
-   Drop Failure Rate


#### <a name="poor-stream-rate"></a>Scarsa velocità di flusso

La percentuale di flussi scarsa (PSR, Poor Stream Rate) rappresenta la percentuale complessiva dei flussi che hanno qualità scarsa nell'organizzazione. Questa metrica è pensata per evidenziare le aree in cui l'organizzazione può concentrarsi per [](#managed-versus-unmanaged-networks) avere l'impatto più forte per ridurre questo valore e migliorare l'esperienza utente, motivo per cui le reti gestite sono lo stato attivo principale quando si esamina il servizio di gestione del servizio di gestione del servizio (PSR). Anche gli utenti esterni sono importanti, ma l'indagine varia a seconda dell'organizzazione. È consigliabile offrire procedure consigliate per gli utenti esterni ed esaminare le chiamate esterne in modo indipendente rispetto all'intera organizzazione.

La misura effettiva in CQD varia in base al carico di lavoro, ma ai fini di questo articolo ci concentriamo principalmente sulla misurazione della percentuale di audio _scadente._ PSR è costituito delle cinque medie metriche di rete descritte nella tabella seguente. Per classificare un flusso come scadente, solo una metrica deve superare la soglia definita. CQD fornisce il valore "Poor Due To..." misurazioni per comprendere meglio la condizione che ha causato la classificazione di scarso flusso. Per altre informazioni, leggere [La classificazione di stream in CQD.](stream-classification-in-call-quality-dashboard.md)

> [!Note]
> CQD fornisce il valore "Scarso a causa di..." misurazioni per comprendere meglio la condizione che ha causato la classificazione di scarso flusso.


##### <a name="audio-poor-quality-metrics"></a>Metriche audio di qualità scarsa

| Media metrica     | Descrizione     | Esperienza utente |
|-------------|-----------------|-----------------|
| Jitter \> 30 ms        | Si tratta della variazione media del ritardo tra pacchetti successivi. Teams e Skype for Business possono adattarsi ad alcuni livelli di instabilità attraverso il buffering. È solo quando il jitter supera il buffering che un partecipante nota gli effetti di instabilità.      | I pacchetti che arrivano a diverse velocità causano la voce di un altoparlante che sembra robot.   |
| Tasso di perdita pacchetti \> 10% o 0,1        | Spesso viene definita come percentuale di pacchetti che vengono persi. La perdita di pacchetti influisce direttamente sulla qualità audio, ad esempio singoli pacchetti di piccole dimensioni che non hanno quasi nessun impatto sulle perdite "back-to-back" che causano il completamente del cut out dell'audio.     | I pacchetti eliminati e non in arrivo nella destinazione prevista causano lacune nel contenuto multimediale, con conseguente perdita di sillabe e parole, video e condivisione sopportabili. |
| Tempo di round trip \> 500 ms        | È il tempo necessario per ottenere un pacchetto IP dal punto A al punto B e tornare al punto A. Questo ritardo di propagazione di rete è collegato alla distanza fisica tra i due punti e alla velocità della luce e include un ulteriore sovraccarico dei vari dispositivi nel percorso di rete.      | I pacchetti che stanno prendendo troppo tempo per arrivare a destinazione causano un effetto walkie-talkie.   |
| NMOS degradation average \> 1.0         | Degradazione [media del mean opinion score (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) della rete per lo stream. Rappresenta l'influenza della perdita e dell'instabilità di rete sulla qualità dell'audio ricevuto che ha causato il rilascio di NMOS di più di un punto. | Si tratta di una combinazione di instabilità, perdita di pacchetti e, in misura minore, aumento del tempo di round trip. L'utente potrebbe aver riscontrato una combinazione di questi sintomi.   |
| Rapporto medio dei campioni nascosti \> 7% o 0,07 | Rapporto medio del numero di frame audio con campioni nascosti generati dalla perdita di pacchetti e dal numero totale di frame audio. Un campione di audio nascosto è una tecnica usata per eliminare la transizione abrupt che in genere sarebbe causata da pacchetti di rete eliminati.      | I valori alti indicano che sono stati applicati livelli significativi di perdita di maschera e hanno comportato la distortità o la perdita di audio.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Perché preferiamo usare i flussi invece delle chiamate?

I flussi ci consentono di sapere quale parte della chiamata era scadente: in uscita o in entrata. Quando stai esaminando l'analisi delle chiamate per una chiamata scadente, determinare se la chiamata scadente era dovuta al flusso del chiamante (in uscita) o al flusso del chiamato (in entrata). Determinare quale flusso influisce sulla qualità della chiamata è ancora più importante per le conferenze. Se stai esaminando solo i dati delle chiamate, vedrai il numero di conferenze a cui partecipa una persona, ma non vedrai quali persone sono relatori attivi, eseguendo la maggior parte della condivisione dello schermo.

I dati delle chiamate ti danno metriche sull'utilizzo, ma non ti porteranno necessariamente alla causa principale della scarsa qualità delle chiamate. Esaminando la direzione del flusso, è possibile identificare fattori come una chiamata non in una rete gestita, una chiamata da un non dipendente (ad esempio un fornitore o un utente di una rete diversa). In questi casi, se la connessione di rete dell'altra persona era scadente, l'intera chiamata verrà contrassegnata come scadente. Non è possibile eseguire alcun operazione su fattori esterni, quindi questi dati non sono utili.

La direzione di flusso può anche aiutare a identificare i dispositivi o i client problematici.

 - Ad esempio, se hai un budget limitato per i dispositivi e vuoi fornire dispositivi solo per utenti audio pesanti, usa il report Di utilizzo audio (VoIP) e filtra i flussi in uscita e le conferenze. Cercare utenti audio ad alto volume che parlano in microfoni incorporati, che potrebbero essere correlati a una qualità delle chiamate più scarsa (e si potrebbe voler fornire dispositivi audio a queste persone). Per maggiore chiarezza, è possibile filtrare l'utilizzo dei pacchetti, in modo da consentire l'uso di utenti audio particolarmente voluminosi. 

  - Un altro esempio riguarda la condivisione dello schermo. Se un cliente usa un client teams precedente, le prestazioni di condivisione dello schermo potrebbero risultare interessate. È possibile risolvere il problema assegnando priorità all'aggiornamento dei client per le persone che ese verificano una grande quantità di condivisione dello schermo.

 - Identificando la direzione di un flusso che causa una bassa qualità delle chiamate, puoi determinare se hai un problema QoS o di larghezza di banda. Se la QoS non è stata completamente implementata o se si contrassegnano solo i pacchetti sul client e non sul flusso in ingresso, la qualità delle chiamate potrebbe risultare più scarsa. Esaminando la direzione dello stream, è possibile ottenere una visualizzazione più granulare di perdita di pacchetti, latenza o instabilità in una direzione specifica. 

   - Ad esempio, si supponga che un utente si lamenta dell'audio metallico quando è su una connessione cablata (jitter). Esaminando lo stream e la direzione, è possibile stabilire che il problema si verifica sullo stream in ingresso, solo per un set specifico di subnet. Dopo aver dato queste informazioni al team di rete, possono tenerne traccia con un acceleratore WAN non configurato correttamente che non bypassava il traffico multimediale. Quando il team di rete riconfigura l'acceleratore WAN, il jitter scompare e la qualità della chiamata migliora. 


#### <a name="setup-failure-rate"></a>Tasso di errori di configurazione

La velocità di errore di  configurazione, altrimenti nota come misura percentuale di errore di impostazione chiamata totale in CQD, è il numero di flussi in cui non è stato possibile stabilire il percorso del supporto tra gli endpoint all'inizio della chiamata.

Rappresenta qualsiasi flusso multimediale che non è stato possibile stabilire. Considerato il livello di gravità dell'impatto di questo problema sull'esperienza utente, l'obiettivo è ridurre questo valore il più vicino possibile allo zero. Un valore elevato per questa metrica è più comune nelle nuove distribuzioni con regole del firewall incomplete rispetto a una distribuzione per adulti, ma è comunque importante controllare regolarmente.

Questa metrica viene calcolata calcolando il numero totale di flussi che non è stato possibile configurare per il numero totale di flussi che ha inviato un record dettagli chiamata (CDR) riuscito:

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count / Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Drop Failure Rate

La percentuale di errore di rilascio, altrimenti nota come misura _Percentuale_ di errore totale chiamata interrotta in CQD, è la percentuale di flussi già stabiliti in cui il percorso del supporto si è chiuso normalmente.

Rappresenta qualsiasi flusso multimediale terminato in modo imprevisto. Anche se l'impatto di questa operazione non è così grave come un flusso che non è stato configurato, ciò influisce comunque negativamente sull'esperienza utente. Improvvise gocce improvvise e frequenti dei supporti multimediali non solo possono avere un impatto grave sull'esperienza utente, ma anche l'esigenza di riconnettersi, con conseguente perdita di produttività (per non menzionare la frustrazione).

La metrica viene calcolata suddividendo il numero totale di flussi eliminati per il numero totale di flussi configurato correttamente:

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definire le metriche di destinazione

Questa sezione descrive alcune delle metriche di base per i servizi usate per valutare l'integrità dei servizi. Valutando e valutando continuamente gli sforzi per mantenere queste metriche al di sotto dei target definiti, garantirai agli utenti una qualità delle chiamate coerente e affidabile. Come punto di partenza, usare gli obiettivi suggeriti nella tabella seguente. Modificare gli obiettivi in base alle esigenze per raggiungere gli obiettivi aziendali.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo di rete</th><th rowspan="1">Obiettivi di qualità</th><th colspan="2">Obiettivi di affidabilità</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Tasso di errori di configurazione</th><th>Drop Failure Rate</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Generale</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferenze</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Cablata interna</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 5 GHz interne</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interna da 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Generale</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Cablata/Wi-Fi interna da 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Cablata/Wi-Fi a 5 GHz in generale</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Generale</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Esperienza utente

L'analisi dell'esperienza utente è più un'arte che una scienza, perché le metriche raccolte qui non sempre indicano che esiste un problema con la rete o il servizio, ma semplicemente indicano che l'utente percepisce un problema. CQD include un meccanismo di sondaggio incorporato, che consente di valutare l'esperienza utente complessiva. RMC offre informazioni approfondite sulle domande seguenti dal punto di vista degli utenti:

-   Come si può usare la soluzione?
-   La soluzione è facile da usare e intuitiva e supporta le esigenze di comunicazione quotidiane?
-   La soluzione mi consente di completare il mio lavoro?
-   Qual è la qualità complessiva della soluzione?
-   È possibile usare la soluzione in qualsiasi momento, indipendentemente da dove ci si trova?
-   È possibile configurare e gestire una chiamata?

#### <a name="rate-my-call"></a>Valuta la mia chiamata 

Valuta la mia chiamata (RMC) è integrato in Teams e Skype for Business. Viene visualizzato automaticamente dopo una chiamata ogni 10 chiamate, il 10%. Questo breve sondaggio chiede all'utente di valutare la chiamata e fornire un contesto che spiega perché la qualità della chiamata poteva risultare scadente. Una o due valutazioni sono considerate scadente, da tre a quattro sono buone e cinque sono eccellenti. Anche se si tratta di un indicatore di ritardo, si tratta di una metrica utile per individuare i problemi che le metriche di servizio possono perdere.

> [!Note]
> Il fattore umano: spesso gli utenti ignorano il sondaggio quando la qualità delle chiamate è buona e lo compilano quando la qualità delle chiamate è bassa. Di conseguenza, i report RMC potrebbero essere astrali sul lato scadente anche se le metriche di servizio sono buone.

È possibile usare CQD per creare report sulle risposte degli utenti di RMC e report di esempio sono inclusi nel modello CQD. Non vengono però discusse in dettaglio in questo articolo. 

#### <a name="client-and-device-readiness"></a>Conformità di client e dispositivi

È necessaria una solida strategia per client e dispositivi per garantire agli utenti un'esperienza utente coerente e positiva. Alcuni principi chiave sono alla base di ogni strategia di conformità.

##### <a name="client-readiness"></a>Conformità dei client

Mantenere aggiornato il client Teams assicura che gli utenti osercitino sempre l'esperienza migliore possibile. Microsoft rilascia aggiornamenti [frequenti al client Teams](teams-client-update.md) (l'aggiornamento viene installato in background a meno che non sia stata disattivata questa funzionalità, che non è consigliabile). È anche importante ricordare di applicare patch ai driver di rete, video, USB e audio, perché sono spesso trascurati e possono influire sulla qualità delle chiamate e delle riunioni. È consigliabile aggiungere driver di rete, Wi-Fi, video, USB e audio al processo di gestione delle patch corrente.


##### <a name="device-readiness"></a>Conformità dei dispositivi

Nessuna strategia può influire sull'esperienza utente oltre alla strategia di conformità dei dispositivi. Ad esempio, gli utenti che si affidano agli altoparlanti e al microfono del proprio portatile riceveranno molto rumore di fondo nelle chiamate e nelle riunioni. Teams è progettato per funzionare con quasi tutti i dispositivi, ma in caso di problemi relativi al dispositivo, consulta [Telefono per Teams.](phones-for-teams.md)


### <a name="categories-of-quality"></a>Categorie di qualità

Operativamente un insieme di procedure di gestione della qualità: in questo modo si hanno le migliori probabilità di avere una buona qualità per le chiamate e le riunioni. Un piano di gestione della qualità buona si rivolge a queste categorie:

-   **Rete:** Qualità audio incentrata sulla metrica Poor Stream Ratio (PSR), utilizzo TCP, subnet cablate e wireless e identificazione dell'uso di proxy HTTP e VPN

-   **Endpoint:** Dispositivi audio e client aggiornati

-   **Gestione dei servizi:** Questa categoria comprende due sezioni:

    -   Prima di tutto è responsabilità di Microsoft gestire e gestire i servizi Teams e Skype for Business Online.

    -   In secondo piano sono le attività gestite dall'organizzazione per garantire un accesso affidabile al servizio, ad esempio l'aggiornamento delle informazioni dell'edificio e la gestione dei firewall per i nuovi indirizzi IP di Office 365 quando viene aggiunta l'infrastruttura al servizio.

![Grafico delle categorie di qualità in un'organizzazione](media/qerguide-image-categories.png "Categorie di qualità in un'organizzazione: gestione del servizio, endpoint e rete.")

Esaminare l'elenco seguente di attività consigliate per mantenere la qualità. È consigliabile eseguire queste attività regolarmente, ad esempio ogni settimana.

#### <a name="service-management-tasks"></a>Attività di gestione dei servizi

Queste attività vanno dalla verifica della larghezza di banda sufficiente per raggiungere il servizio senza saturare i collegamenti Internet, dalla convalida della qualità del servizio (QoS) in tutte le aree di rete gestite e dalla capacità di mantenere il controllo degli intervalli IP di [Office 365](https://aka.ms/o365ips)nei firewall.

#### <a name="network-tasks"></a>Attività di rete

Sono disponibili due categorie di attività di rete: affidabilità e qualità. L'affidabilità è incentrata su come misurare la capacità dell'utente di effettuare correttamente le chiamate e rimanere connesso. La qualità è incentrata sulla telemetria aggregata inviata a Teams e Skype for Business online dal client dell'utente durante la chiamata e dopo che è terminata. 

Considerato l'impatto critico dell'affidabilità sull'esperienza utente, è consigliabile valutare ed esaminare le metriche di affidabilità prima di approfondire la qualità. 

#### <a name="endpoints-tasks"></a>Attività degli endpoint

L'attività principale in questa categoria è rimuovere eventuali ostacoli ai normali aggiornamenti [dei client di Teams.](teams-client-update.md) Per impostazione predefinita, Teams si aggiorna automaticamente regolarmente ,a meno che non si disaccerti di questa impostazione, che non è consigliabile. 

È anche consigliabile monitorare i dispositivi e fornire aggiornamenti ogni volta che si identificano i problemi correlati a un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Utilizzare Call Quality Quality Call per gestire la qualità delle chiamate

Dopo aver configurato [Call](turning-on-and-using-call-quality-dashboard.md)Quality, puoi iniziare a usarlo per gestire la qualità delle chiamate e delle riunioni per la tua organizzazione.

La maggior parte dei problemi relativi alle prestazioni di Teams rientrano nelle categorie seguenti:

-   Configurazione incompleta del firewall o del proxy
-   Copertura Wi-Fi scarsa
-   Larghezza di banda insufficiente
-   VPN
-   Versioni client e driver non coerenti o obsoleti
-   Dispositivi audio non supportati o incorporati
-   Subnet o dispositivi di rete problematici

Se si prende il tempo prima di implementare Teams per valutare queste aree e correggere eventuali mancanze, si ridurrà l'impegno necessario per mantenere un'esperienza di alta qualità di Teams per tutti gli utenti. Per una valutazione della rete in preparazione all'implementazione di Teams, leggere [Advisor per Teams](use-advisor-teams-roll-out.md) e Preparare la rete per [Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Aspettative con CQD

Usa Call Quality Dashboard (CQD) per ottenere informazioni approfondite sulla qualità delle chiamate effettuate utilizzando Teams e i servizi di Skype for Business. CQD è progettato per aiutare gli amministratori di Teams e Skype for Business e i tecnici di rete a ottimizzare la rete e tenere sotto controllo qualità, affidabilità e esperienza utente. CQD esamina la telemetria aggregata per un'intera organizzazione, in cui possono verificarsi modelli generali; in modo da eseguire valutazioni informate e pianificare le correzioni. CQD fornisce report delle metriche che forniscono informazioni approfondite sulla qualità generale, l'affidabilità e l'esperienza utente.

CQD, anche se utile per analizzare tendenze e subnet, non sempre fornisce una causa specifica per uno specifico scenario. È importante comprendere questo aspetto e impostare le aspettative quando si usa CQD:

-   CQD non fornisce la causa principale di ogni scenario
-   CQD non contiene stream di Sistema telefonico o Audioconferenza
-   Call Call Call call out areas for further investigation based on trends

### <a name="cqd-reports-overview"></a>Panoramica dei report di CQD

Usare il menu a discesa nella parte superiore dello schermo per aprire un report. Per un elenco dei dati disponibili in ogni report, leggere i dati disponibili nei report [di CQD.](CQD-data-and-reports.md#data-available-in-cqd-reports)

Novità di gennaio 2020: scaricare i modelli di query di [Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di CQD.


### <a name="teams-vs-skype-for-business"></a>Confronto tra Teams e Skype for Business

CQD può creare report sia su Teams che su Skype for Business. A volte però può essere necessario sviluppare un report per esaminare la telemetria di Teams separatamente da Skype for Business.

#### <a name="summary-reports"></a>Report di riepilogo

Per modificare la pagina dei report di riepilogo in  modo da visualizzare solo Teams o Skype for Business, selezionare il menu a discesa Filtro prodotti nella parte superiore dello schermo e quindi selezionare il prodotto desiderato.

![Screenshot del menu a discesa con le opzioni di filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Report dettagliati

Per filtrare tutti i report dettagliati, aggiungere quanto segue alla fine dell'URL nella barra del browser:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Esempio:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Per altre informazioni sui filtri URL, vedere Report [sui filtri](CQD-data-and-reports.md#report-filters) più avanti in questa sezione.

Per filtrare un singolo report dettagliato, aggiungere il ``Is Teams`` filtro al report e impostarlo su True o False.

![Screenshot della pagina Aggiungi filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Reti gestite e non gestite

Per impostazione predefinita, tutti gli endpoint in CQD vengono classificati come esterni. Non appena viene introdotto un file di edificio, è possibile iniziare a esaminare i dati degli endpoint gestiti. Come accennato in precedenza, le reti in CQD sono definite come:

-   Una _rete gestita,_ spesso definita interna o interna, può essere influenzata e controllata dall'organizzazione. Ciò include la LAN interna, la WAN remota e la VPN.
-   Una _rete non gestita,_ spesso definita esterna o esterna, non può essere influenzata né controllata dall'organizzazione. Un esempio di rete non gestita è una rete di hotel o aeroporto.

### <a name="dimensions-measures-and-filters"></a>Dimensioni, misure e filtri

Una query di domande e risposte ben formata contiene tutti e tre i parametri seguenti:

-   **Dimensione:** Come eseguire il pivot dei dati.

-   **Misura:** Cosa voglio segnalare.

-   **Filtro:** Come si vuole ridurre il set di dati restituiti dalla query.

Un altro modo di osservare è che una dimensione  è la funzione di raggruppamento,  una misura è i dati a cui sono interessato e un filtro consente di limitare i risultati a quelli rilevanti per la query. 

Un esempio di query ben formata è **Show me Poor Streams [Measure] by Subnet [Dimension] for Building 6 [Filter]**. Per altre informazioni, vedere [Dimensioni e misure disponibili in CQD.](https://aka.ms/cqd-dm)

### <a name="first-vs-second"></a>Primo vs. secondo 

Molte delle dimensioni e misure in CQD sono classificate per prime o secondi. Call Called non usa campi chiamante/chiamato, perché  sono  stati rinominati per primo e secondo perché ci sono passaggi intervenendo tra il chiamante e il chiamato. La logica seguente determina quale endpoint coinvolto viene etichettato come primo:

-   **Il** primo endpoint sarà sempre un endpoint server (Conference Server, Mediation Server e così via) se un server è coinvolto nello stream o nella chiamata.

-   **Il** secondo endpoint sarà sempre un endpoint client, a meno che lo stream non sia tra due endpoint server.

-   Se entrambi gli endpoint sono dello stesso tipo, la scelta del primo si basa sull'ordinamento interno della categoria agente utente. Ciò assicura che l'ordinamento sia coerente.

Per altre informazioni su come determinare il primo o il secondo endpoint quando sono uguali, vedere Dimensioni e misure [disponibili in CQD.](https://aka.ms/cqd-dm)

### <a name="stream-vs-call"></a>Confronto tra flusso e chiamata

È necessario comprendere la differenza tra una chiamata e uno stream per scegliere correttamente le dimensioni o le misure da guardare in Call Call Call. Anche se lo stato attivo principale di CallQD è sui flussi, sono disponibili anche misurazioni basate su chiamata.

-   **Stream:** Uno _stream_ è presente solo tra due endpoint. Esiste un solo flusso per ogni direzione e sono necessari due flussi per la comunicazione. I flussi sono utili per indagare su edifici, reti o subnet. In alcuni casi, sia la chiamata che lo stream vengono utilizzati nel nome della misura (ad esempio, Call Setup Stream o Call Dropped Stream). Questi flussi sono ancora classificati come flussi.

-   **Chiama:** Una _chiamata_ è un raggruppamento di tutti i flussi di tutti i partecipanti. Una chiamata è costituita, come minimo, da due flussi. Una singola chiamata avrà almeno due endpoint, ognuno con un minimo di uno stream.

Per altre indicazioni sul fatto che la dimensione o la misura fa riferimento a una chiamata o a uno stream, vedere Dimensioni e misure [disponibili in Call Call](https://aka.ms/cqd-dm) Call

### <a name="good-poor-and-unclassified-calls"></a>Chiamate buone, di qualità scarsa e non classificate

Una chiamata è classificata come buona, scarsa o non classificata. Diamo un po' di tempo per parlarne in modo più dettagliato.

-   **Buono o scadente:** Una chiamata buona o scarsa è costituita da una chiamata che contiene un set completo di metriche di servizio, per cui è stato generato e ricevuto un report QoE completo dal servizio. Determinare se un flusso è buono o scadente è descritto [in precedenza in questo articolo.](#poor-stream-rate)

-   **Unclassified:** Un flusso non classificato non contiene un set completo di metriche di servizio. Si tratta di chiamate brevi, in genere inferiori a 60 secondi, in cui non è stato possibile calcolare le medie e non è stato generato un report QoE. Il motivo più comune per cui le chiamate non vengono classificate è che l'utilizzo dei pacchetti è stato poco o niente. Un esempio di ciò potrebbe essere un partecipante che partecipa a una riunione disattivando l'audio e non parla mai. Il partecipante riceve, ma non trasmette, elementi multimediali. Senza elementi multimediali trasmessi, non ci saranno metriche disponibili per CQD da usare per classificare lo stream multimediale in uscita dell'endpoint.

Per altre informazioni, leggere [La classificazione di stream in CQD.](stream-classification-in-call-quality-dashboard.md)

### <a name="common-subnets"></a>Subnet comuni

Le subnet comuni sono subnet private specifiche utilizzate da hotel, reti domestiche, hotspot e aree simili. Queste subnet sono difficili da valutare a causa del loro uso diffuso. Se l'organizzazione usa una di queste subnet comuni, è consigliabile spostare tale rete in un'altra subnet. In questo modo la creazione di report sarà più semplice in CQD. Se specificato, i report nel modello Tutte le reti sono stati configurati per escludere queste subnet per eliminarle come fonte di qualità scarsa. Le subnet comuni sono definite di seguito; il loro impatto varia in base all'organizzazione.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Quando si esamina una rete gestita che usa una subnet comune, è necessario usare la seconda dimensione ip locale riflesso per raggruppare le subnet. Questa dimensione contiene l'indirizzo IP pubblico dell'endpoint.


## <a name="reliability-investigations"></a>Indagini sull'affidabilità

Il primo passaggio per migliorare la qualità consiste nel valutare lo stato di affidabilità in tutta l'organizzazione. Dal momento che l'affidabilità è fondamentale per un'esperienza utente positiva, iniziamo con i due componenti che misurano l'affidabilità:

1.  **Errori di installazione:** Non è stato possibile stabilire la chiamata.

2.  **Errori di eliminazione:** La chiamata è stata stabilita e la chiamata è stata terminata in modo imprevisto.

In questa sezione verranno descritti i metodi per indagare su entrambe le aree.

> [!NOTE]
> In questo articolo non sono inclusi tutti i report inclusi nei modelli. Tuttavia, i metodi di indagine descritti di seguito sono ancora applicabili. Per altre informazioni, fare riferimento alla descrizione del singolo report.


### <a name="setup-failures"></a>Errori di installazione

Assegnare prima la priorità alla correzione degli errori di installazione in quest'area, perché questi errori hanno un impatto negativo significativo sull'esperienza utente.

Avviare l'indagine valutando la percentuale di errori di configurazione complessivi per l'organizzazione e quindi classificando in ordine di priorità le aree di indagine in base alla percentuale più elevata tramite edificio o rete. 

#### <a name="setup-failure-trend-analysis"></a>Configurare l'analisi della tendenza degli errori

Questo report mostra la quantità totale di flussi, gli errori di configurazione del flusso e la frequenza degli errori di configurazione dello stream. Posizionare il punto su una delle colonne per visualizzare i singoli valori. 

##### <a name="analysis"></a>Analisi

Con questo report è possibile rispondere alle domande seguenti e determinare le prossime azioni da eseguire:

-   Qual è la percentuale totale di errori di configurazione delle chiamate per il mese corrente?

-   La percentuale totale di errore di impostazione chiamata è inferiore o superiore alla metrica di destinazione definita?

-   La tendenza ai guasti è peggiore o migliore del mese precedente?

-   La tendenza a insuccesso è crescente, costante o decrescente?

Indipendentemente dalle risposte fornite a queste domande, prendi il tempo di approfondire l'analisi utilizzando i relativi report secondari per cercare singoli edifici o subnet che potrebbero richiedere correzioni. Anche se la percentuale di errori complessivi potrebbe essere inferiore alla metrica target, le percentuali di errore per uno o più edifici o reti potrebbero essere superiori alla metrica di destinazione ed è necessaria un'indagine.

#### <a name="setup-failure-investigations"></a>Analisi degli errori di configurazione 

Questo report di riepilogo viene usato per individuare e isolare gli edifici o le reti che potrebbero richiedere correzioni.

> [!NOTE]
> Assicurarsi di impostare il filtro del rapporto Mese anno sul mese corrente. Selezionare **Modifica** e modificare il filtro **rapporto Mese** anno per salvare il nuovo mese predefinito.

##### <a name="remediation"></a>Correzione 

Concentrare le prime azioni di correzione sugli edifici o le subnet con il più grande volume di guasti. Ciò inciderà al massimo sull'esperienza utente e aiuterà a ridurre rapidamente il numero di errori di impostazione delle chiamate dell'organizzazione. La tabella seguente elenca i due motivi per cui gli errori di configurazione sono riportati da CQD.

| Motivo errori di impostazione chiamata       | Causa tipica                    |
|----------------------------------|----------------------------------|
| Regola di esenzione del DP del FW mancante | Indica che l'apparecchiatura di rete lungo il percorso ha impedito la creazione del percorso del supporto a causa delle regole di ispezione profonda dei pacchetti (DMP). È probabile che le regole del firewall non siano configurate correttamente. In questo scenario l'handshake TCP è riuscito, ma non l'handshake SSL.      |
| Regola di eccezione del blocco IP del FW mancante      | Indica che l'apparecchiatura di rete lungo il percorso ha impedito la configurazione del percorso per il supporto verso la rete Microsoft 365 o Office 365. Il problema potrebbe essere dovuto al fatto che le regole del proxy o del firewall non sono configurate correttamente per consentire l'accesso agli indirizzi IP e alle porte usate per il traffico di Teams e Skype for Business. |

Quando si inizia la correzione, è possibile concentrare le attività su uno specifico edificio o subnet. Come illustrato nella tabella precedente, questi problemi sono dovuti alle configurazioni del firewall o del proxy. Esaminare le opzioni nella tabella seguente per le azioni correttive.

|      Correzione      |Linee guida  |
|-----------------------|----------|
| Configurare i firewall | Collaborare con il team di rete e verificare la configurazione dei firewall rispetto all'elenco di indirizzi [IP di Office 365.](https://aka.ms/o365ips)<br><br>Verificare che le [porte e le subnet dei](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) supporti multimediali siano incluse nelle regole del firewall. <br><br>Verificare che le [porte necessarie](prepare-network.md) siano aperte nel firewall. A UDP deve essere data priorità perché TCP è considerato un protocollo failback per la condivisione dello schermo basata su audio, video e video e il suo utilizzo influirà sulla qualità della chiamata. La condivisione di applicazioni RDP legacy usa solo TCP.|

### <a name="drop-failures"></a>Errori di eliminazione

A differenza dei codici di errore di installazione, CQD non include codice di errore di eliminazione per indicare il motivo degli errori di eliminazione, il che rende difficile isolare una causa radice specifica. Per migliorare gli errori di eliminazione della triage, usare un approccio dedotto. La correzione di eventuali aree di interesse per gli elementi multimediali, la distribuzione di patch a client e driver e l'utilizzo di dispositivi certificati per Teams e Skype for Business possono essere rifiutati.

#### <a name="drop-failure-trend-analysis"></a>Analisi della tendenza a drop failure

Questo report mostra la quantità totale di flussi audio, gli errori di rilascio totali e la frequenza di errore di rilascio. Posizionare il punto su una delle colonne per visualizzarne i valori. 


##### <a name="analysis"></a>Analisi

Usando questo tipo di report, è possibile rispondere alle domande seguenti:

-   Qual è la frequenza di errore di rilascio corrente?
-   Il tasso di errore di rilascio è inferiore alla metrica target definita?
-   La tendenza ai guasti è peggiore o migliore del mese precedente?
-   La tendenza a insuccesso è crescente, costante o decrescente?

Indipendentemente dalle risposte alle domande precedenti, prendi il tempo di esaminare i report secondari per cercare eventuali edifici o reti che potrebbero richiedere correzioni. Anche se il tasso di errore di rilascio complessivo potrebbe essere inferiore alla metrica di destinazione, il tasso di errore di rilascio per uno o più edifici o reti potrebbe essere superiore alla metrica di destinazione ed è necessaria un'indagine.

#### <a name="drop-failure-investigations"></a>Indagini su errori di eliminazione

Gli errori riportati qui indicano che la chiamata è stata interrotta in modo imprevisto e ha restituito un'esperienza utente negativa. A differenza dei report di tendenza, questi report forniscono informazioni aggiuntive su subnet specifiche che necessitano di ulteriori indagini.


##### <a name="remediation"></a>Correzione

Usando i report della tabella inclusa, è possibile isolare le aree interessate dalla rete in cui la percentuale di rilascio è superiore alla metrica di destinazione definita. Concentrare le prime azioni di correzione sugli edifici o le subnet con il numero totale di flussi più elevato, per ottenere il maggior impatto.

Cause comuni degli errori di chiamata:

-   Rete o uscita Internet di cui è in corso il provisioning
-   Nessuna QoS configurata su reti vincolate
-   Versioni client precedenti
-   Comportamento dell'utente

Dopo aver scoperto le aree problematiche, è possibile usare l'analisi delle chiamate [per](use-call-analytics-to-troubleshoot-poor-call-quality.md) utente per esaminare ulteriormente gli utenti dell'edificio per problemi specifici. L'analisi delle chiamate contiene altri dati dell'Unione Europea (EUII) e può essere utile per isolare ulteriormente i potenziali motivi degli errori di rilascio.

Indipendentemente dal passaggio successivo, è consigliabile informare il supporto help desk che è stato rilevato un problema con edifici o subnet specifiche. In questo modo l'help desk può rispondere rapidamente alle chiamate in arrivo e valuta gli utenti in modo più efficiente. Gli utenti contrassegnati possono quindi essere segnalati al team di progettazione per ulteriori indagini.

La tabella seguente elenca alcuni metodi comuni per gestire e correggere gli errori di eliminazione.

| Correzione                              | Linee guida                      |
|------------------------------------------|-------------------------------|
| **Rete/Internet**                         | **Congestione:** collaborare con il team di rete per monitorare la larghezza di banda a specifici edifici/subnet per verificare la vi sono problemi di sovrautilizzazione. Se confermi che c'è una congestione di rete, valuta l'aumento della larghezza di banda dell'edificio o l'applicazione della QoS. Usare i report di riepilogo sulla [qualità](#quality-investigations) scarsa dello stream inclusi per esaminare le subnet che causano problemi di instabilità, latenza e perdita dei pacchetti, perché precedono spesso uno stream interrotta.<br><br>**QoS:** se aumentare la larghezza di banda è impraticabile o a costi vietati, valutare l'implementazione della QoS. Questo strumento è molto efficace per gestire il traffico congestionato e può garantire che i pacchetti multimediali sulla rete gestita siano prioritari al di sopra del traffico non multimediale. In alternativa, se non esistono prove chiare che la causa sia la larghezza di banda, considerare queste soluzioni:<ul><li>[Indicazioni QoS di Microsoft Teams](qos-in-teams.md)</li></ul><br>**Eseguire una valutazione della conformità** della rete: una valutazione della rete fornisce dettagli sull'utilizzo previsto della larghezza di banda, su come affrontare i cambiamenti della larghezza di banda e della rete e sulle procedure di rete consigliate per Teams e Skype for Business. Usando la tabella precedente come origine, si dispone di un elenco di edifici o subnet eccellenti per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul> |
| **Client (solo Skype for Business online)** | Alcuni client Skype for Business meno recenti hanno conosciuto problemi documentati con l'affidabilità dei supporti multimediali. Esamina i report di Call Analytics di più utenti interessati oppure crea un report personalizzato della tabella Versione client in CQD filtrato in base a specifici edifici o subnet con la misura Total Call Dropped Failure%. Queste informazioni aiuteranno a capire se esiste una relazione tra l'eliminazione delle chiamate nell'edificio specifico e una versione specifica del client.     |
| **Dispositivi**                                  |Se la causa dei problemi di qualità delle chiamate è un dispositivo, è consigliabile aggiornare i dispositivi offensivi. Leggi [i telefoni per Teams](phones-for-teams.md) per saperne di più. |
| **Comportamento dell'utente**                            | Se non si ritiene che il problema non sia né la rete, né i dispositivi né i client, è consigliabile sviluppare una strategia di adozione per gli utenti per informare gli utenti su come partecipare e uscire al meglio da una riunione. Un utente di Teams e Skype for Business più intelligente produrrà un'esperienza utente migliore per tutti i partecipanti alla riunione. Ad esempio, un utente che mette il portatile in stato di sospensione (chiudendo il id) senza uscire dalla riunione verrà classificato come un drop di chiamata imprevisto.   |

## <a name="quality-investigations"></a>Indagini sulla qualità

Il passaggio successivo per valutare lo stato della qualità audio in tutta l'organizzazione consiste nell'analizzare la scarsa velocità di flusso (PSR), TCP e l'utilizzo del proxy. È importante ricordare che i dati di CQD non forniscono una causa radice specifica, ma forniscono le aree di problemi più probabili per avviare una conversazione collaborativa con i team appropriati per le attività di correzione. 

> [!NOTE]
> In questo articolo non sono inclusi tutti i report inclusi nei modelli; Tuttavia, i metodi di indagine descritti di seguito saranno ancora applicabili per questi report. Per altre informazioni, fare riferimento alla descrizione del singolo report. 

### <a name="quality"></a>Qualità

Le percentuali PSR vengono usate per indicare se l'organizzazione ha riunioni con obiettivi metrici definiti per una determinata area di interesse. È importante notare che anche se le percentuali di alto livello sono entro il target definito, le singole subnet o gli edifici potrebbero non soddisfare gli obiettivi definiti e, di conseguenza, necessitano di ulteriori indagini. Ad esempio, se la percentuale complessiva di PSR audio è del 2% ad aprile, che soddisfa il target campione, le singole edifici e subnet potrebbero comunque avere esperienze scadenti, a seconda della distribuzione complessiva di questo 2%. 

Per valutare la percentuale di flussi scarsi, usare i report sulla qualità. Per esaminare le metriche generali, le conferenze, le chiamate PSTN a due, le chiamate PSTN, le VPN e le sale riunioni vengono forniti diversi rapporti di qualità. Per agevolare questo processo vengono forniti report mensili, settimanali e giornalieri. I report settimanali e giornalieri sono limitati al modello Reti gestite per aumentarne l'efficacia e ridurre il rumore. 

#### <a name="quality-trend-analysis"></a>Analisi della tendenza della qualità

I report di tendenza visualizzano informazioni sulla qualità nel tempo e vengono usati per identificare e comprendere le tendenze qualitative in ogni area di interesse. Come accernato in precedenza, nei modelli per l'analisi della qualità sono inclusi alberi di report; conferenza, chiamate PSTN a due parti, VPN e sale riunioni. Ai fini dell'analisi della qualità, il processo di analisi è lo stesso. Tuttavia, è consigliabile iniziare con le conferenze, perché tutti i miglioramenti apportati alla qualità delle conferenze avranno un impatto positivo anche su tutte le altre aree. 

> [!Note]
> L'analisi delle chiamate PSTN a due parti e delle sale riunioni è simile a quella per indagare sui servizi di conferenza. L'obiettivo è isolare gli edifici o le subnet di qualità più bassa e identificare il motivo della qualità scarsa.

> [!Important]
> I report basati su VPN vengono filtrati usando la seconda dimensione VPN. Questa dimensione richiede che l'adattatore di rete VPN sia registrato correttamente come adattatore di accesso remoto. I fornitori di VPN non usano in modo affidabile questa bandierina e il chilometraggio varia in base al fornitore di VPN distribuito nell'organizzazione. Se [necessario, modificare i](CQD-upload-tenant-building-data.md#vpn) report VPN usando il nome dell'edificio o della rete.

##### <a name="investigation"></a>Indagine

Usando questi report, è possibile rispondere alle domande seguenti:

-   Qual è il psr totale per il mese corrente?
-   Il psr è sotto la metrica di destinazione definita?
-   La funzione PSR è peggiore o migliore del mese precedente?
-   La tendenza PSR è crescente, costante o decrescente?

Indipendentemente dalle risposte alle domande precedenti, prendi il tempo di esaminare i report secondari per cercare eventuali edifici o subnet che potrebbero richiedere indagini. Anche se il PSR generale potrebbe essere inferiore alla metrica di destinazione, spesso il PSR per uno o più edifici o reti è superiore alla metrica ed è necessario correggere.

#### <a name="quality-investigations"></a>Indagini sulla qualità

I report di riepilogo della qualità forniscono informazioni più approfondite su ciò che ha contribuito alla classificazione di scarsa qualità dei flussi e consente di isolare le aree interessate nella rete gestita.

Anche se le dimensioni usate potrebbero essere leggermente diverse tra i report, ogni report includerà le misure per i flussi totali, il totale dei flussi scarsi, IL PSR e la qualità scarsa a causa di questo. Sono stati creati report per ogni area di interesse: conferenze, conferenze a due parti, chiamate PSTN, VPN e sale riunioni. Il modello Rete gestita include altri report per sfruttare le informazioni sulla posizione caricate tramite il file dell'edificio.


> [!Note]
> Le subnet comuni sono difficili da valutare a causa del loro uso diffuso. È stato aggiunto un report separato che mostra l'IP pubblico del client (Second Reflexive Local IP) al modello Tutte le reti per facilitare la correzione degli uffici che usano reti comuni.


![Screenshot che mostra il riepilogo dei flussi audio scadenti](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Correzione

Concentrare le azioni di correzione sugli edifici o le subnet che hanno il più grande volume di flussi, perché ciò massimizza l'impatto e aiuta a migliorare rapidamente l'esperienza utente. Utilizza le misure di jitter, perdita di pacchetti e tempo di round trip (RTT) per capire cosa contribuisce alla qualità scarsa (è possibile che ci siano più problemi):

-   **Instabilità:** i pacchetti multimediali arrivano a diverse velocità, generando un suono acustico per un altoparlante.
-   **Perdita pacchetti:** i pacchetti multimediali vengono eliminati, il che crea l'effetto delle parole o delle sillabe mancanti.
-   **RTT:** i pacchetti multimediali stanno occupando molto tempo per raggiungere la destinazione, generando un effetto walkie-talkie.

Per agevolare l'indagine in caso di problemi di qualità, usare [l'analisi delle chiamate per utente.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Con Call Analytics, puoi esaminare una conferenza specifica o il rapporto chiamate dell'utente. Questa relazione conterrà i dati relativi alle informazioni personali dell'Unione Europea (EUII)e risulta utile per la ricerca della causa di un errore. Dopo aver sapere quale edificio è interessato, dovrebbe essere semplice trovare gli utenti all'interno dell'edificio. 

Non dimenticare di far sapere al supporto help desk che queste reti stanno riscontrando problemi di qualità, in modo che possano valutarlo rapidamente e rispondere alle chiamate in arrivo.

| Correzione                              | Linee guida                         |
|------------------------------------------|----------------------------------|
| **Reti**                                 | **Congestione:** una rete inutilizzate o sotto-provisioning può causare problemi con la qualità dei supporti multimediali. Collaborare con il team di rete per determinare se le connessioni di rete dall'utente al punto di uscita Internet hanno una larghezza di banda sufficiente per supportare i supporti multimediali. <br><br>**Eseguire una valutazione della conformità** della rete: una valutazione della rete fornisce dettagli sull'utilizzo previsto della larghezza di banda, su come affrontare i cambiamenti della larghezza di banda e della rete e sulle procedure di rete consigliate per Teams e Skype for Business. Usando la tabella precedente come origine, si dispone di un elenco di edifici o subnet eccellenti per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul>|
| **QoS (Quality of Service)**  | QoS è uno strumento comprovato che aiuta ad assegnare priorità ai pacchetti su una rete congestionata per assicurarsi che arrivino a destinazione intatti e in tempo. È consigliabile implementare la QoS all'interno dell'organizzazione per massimizzare la qualità dell'esperienza utente quando la larghezza di banda è limitata. La QoS consente di risolvere i problemi generalmente associati ad alti livelli di perdita di pacchetti e, in misura inferiore, al jitter e ai tempi di round trip.<ul><li>[Indicazioni QoS di Teams](qos-in-teams.md)</li></ul> |
| **#A0**               | Wi-Fi possono avere un impatto significativo sulla qualità delle chiamate. Wi-Fi distribuzione non prendono in genere in considerazione i requisiti di rete per i servizi VoIP e spesso sono fonte di qualità scarsa. Per altre informazioni su come ottimizzare l'infrastruttura Wi-Fi, vedere questo articolo sulla pianificazione Wi-Fi [distribuzione.](/skypeforbusiness/certification/plan-wifi)<br><br>**Driver wireless:** assicurarsi che i driver wireless siano aggiornati. Ciò consente di ridurre la scarsa esperienza utente relativa a un driver non aggiornato. Molte organizzazioni non includono driver wireless nei cicli delle patch e questi driver possono non essere corretti per anni. Molti problemi wireless vengono risolti verificando che i driver wireless siano aggiornati.<br><br>**WMM**: Wireless Multimedia Extensions (WMM), noto anche come Wi-Fi Multimedia, fornisce funzionalità QoS di base alle reti wireless. Le reti wireless moderne devono supportare molti dispositivi. Questi dispositivi competono per la larghezza di banda e possono portare a problemi di qualità per i servizi VoIP, in cui velocità e latenza sono essenziali. Consulta il tuo fornitore di dispositivi wireless per informazioni specifiche e prendi in considerazione l'implementazione di WMM sulla tua rete wireless per dare priorità ai contenuti multimediali di Skype for Business e Teams.<br><br>**Densità dei punti di** accesso: i punti di accesso potrebbero essere troppo distanti o meno in una posizione ideale. Per ridurre al minimo eventuali interferenze, inserire punti di accesso aggiuntivi nelle sale riunioni e in posizioni non ostruito da muri o altri oggetti in cui il segnale Wi-Fi è debole.<br><br>**Da 2,4 GHz a 5 GHz:** 5 GHz fornisce meno interferenze dello sfondo e velocità più elevate e deve essere prioritario durante la distribuzione di VoIP tramite Wi-Fi. Tuttavia, i 5 GHz non sono più forti di 2,4 GHz e non distorsi in modo così semplice. Esaminare il layout dell'edificio per determinare la frequenza di connessione ottimale. |
|**Dispositivo di rete** | Le organizzazioni più grandi potrebbero avere centinaia di dispositivi distribuiti in tutta la rete. Collaborare con il team di rete per assicurarsi che i dispositivi di rete dall'utente a Internet siano mantenuti e aggiornati. |
| **VPN**  | Le appliance VPN non sono sempre progettate per gestire i carichi di lavoro multimediali in tempo reale. Alcune configurazioni vpn impediscono l'uso di UDP (che è il protocollo preferito per gli elementi multimediali) e si basano solo su TCP. Considerare l'implementazione di una soluzione VPN split tunnel per ridurre la rete VPN come fonte di qualità scarsa. |
| **Client** <br>(solo Skype for Business online) | Assicurarsi che tutti i client vengano aggiornati regolarmente. |
| **Dispositivi** | Se la causa dei problemi di qualità delle chiamate è un dispositivo, è consigliabile aggiornare i dispositivi offensivi. Leggi [i telefoni per Teams](phones-for-teams.md) per saperne di più. |
| **Driver** | La strategia di gestione delle patch dovrebbe far parte della strategia di gestione delle patch di rete (Ethernet e Wi-Fi), audio, video e USB. Molti problemi di qualità vengono risolti aggiornando i driver. |
| **Sale riunioni tramite Wi-Fi** | È altamente consigliabile che i dispositivi delle sale riunioni siano connessi alla rete usando almeno una connessione Ethernet da 1 Gbps. I dispositivi delle sale riunioni in genere includono più flussi audio e video, insieme ai contenuti delle riunioni, ad esempio la condivisione dello schermo, e hanno requisiti di rete più elevati rispetto ad altri endpoint di Teams o Skype for Business. Le sale riunioni sono, per definizione, dispositivi Wi-Fi che possono usufruire di un vantaggio solo durante l'installazione.<br><br>Le sale riunioni devono essere trattate con maggiore attenzione e attenzione per garantire che l'esperienza con questi dispositivi sia in grado di soddisfare o superare le aspettative. I problemi di qualità relativi alle sale riunioni vengono in genere inoltrati rapidamente, perché vengono spesso utilizzati dal personale di livello superiore.<br><br>Tutte le funzioni sono uguali, oltre alla praticità, Wi-Fi prestazioni sono spesso inferiori a quelle di una connessione cablata. Con l'aumento delle politiche di "portare il tuo dispositivo personalizzato" e la proliferazione di portatili, i punti di accesso Wi-Fi sono spesso sovra utilizzati. I supporti multimediali in tempo reale potrebbero non essere classificati in ordine di priorità Wi-Fi di rete, il che può causare problemi di qualità durante i momenti di picco dell'uso. Questo utilizzo elevato può coincidere con una riunione in cui la partecipazione di una decina di persone, ognuna con il proprio portatile e smartphone, è connessa allo stesso punto di accesso Wi-Fi del dispositivo della sala riunioni.<br><br>Wi-Fi deve essere considerata solo come soluzione temporanea, per un'installazione per dispositivi mobili o quando è stato eseguito correttamente il provisioning di Wi-Fi per supportare elementi multimediali di livello aziendale in tempo reale. |


### <a name="tcp"></a>TCP 

Transmission Control Protocol (TCP) è considerato un trasporto failback e non il trasporto principale desiderato per i supporti multimediali in tempo reale. Il motivo per cui si tratta di un trasporto failback è dovuto alla natura con stato di TCP. Ad esempio, se una chiamata viene effettuata su una rete latente e i pacchetti multimediali vengono ritardati, i pacchetti di pochi secondi fa, che non sono più utili, competono per ottenere larghezza di banda per raggiungere il destinatario, cosa che può peggiorare la situazione. Questo rende l'audio più grande e allunga l'audio, con il risultato di artefatti udibili, spesso sotto forma di instabilità.

I report di questa sezione non fanno distinzione tra flussi buoni e scarsi. Dato che UDP è preferito, i report ricercano l'uso di TCP per la condivisione dello schermo basata su audio, video e video (VBSS). Vengono fornite tariffe di flusso scarse per confrontare la qualità UDP con quella TCP, in modo da poter concentrare le iniziative nei casi in cui l'impatto è massimo. L'utilizzo di TCP è causato principalmente da regole del firewall incomplete. Per ulteriori informazioni sulle regole del firewall per Teams e Skype for Business online, vedi URL e intervalli di indirizzi IP per [Microsoft 365 e Office 365.](https://aka.ms/o365ips)

> [!Note]
> Audio, video e VBSS preferiscono tutti UDP come trasporto principale. Il carico di lavoro legacy di Condivisione applicazioni RDP usa solo TCP.

#### <a name="tcp-usage"></a>Utilizzo TCP

I report TCP indicano l'utilizzo complessivo di TCP negli ultimi sette mesi. Tutti gli altri report in questa sezione saranno incentrati sul restringere specifici edifici e subnet in cui TCP è usato più comunemente. Sono disponibili report separati sia per le conferenze che per i flussi a due parti.

![Grafico che mostra la percentuale di flussi audio che usano TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Indagine

Con questo report è possibile rispondere alle domande seguenti:

-   Qual è il volume totale dei flussi TCP per il mese corrente?
-   È peggiore o migliore del mese precedente?
-   La tendenza all'utilizzo di TCP è crescente, costante o decrescente?
-   Tcp PSR è uguale al PSR generale?

Se si nota che la tendenza di utilizzo TCP è in aumento o superiore al normale utilizzo mensile, è consigliabile analizzare i report secondari per cercare eventuali edifici o reti che potrebbero richiedere correzioni. Idealmente, sono richieste il numero massimo possibile di sessioni audio basate su TCP nella rete gestita.

#### <a name="tcp-vs-udp"></a>CONFRONTO tra TCP e UDP

Questo report identifica il volume di report sull'utilizzo di TCP e UDP nell'ultimo mese per la condivisione dello schermo basata su audio, video e video (VBSS). 

![Report che mostra il volume dei flussi che usano TCP e UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analisi

Anche se si vuole che l'utilizzo TCP sia il più basso possibile, è possibile che venga visualizzato un po' di utilizzo TCP in una distribuzione altrimenti integra. TCP di per sé non contribuisce a una chiamata di scarsa qualità, quindi vengono fornite tariffe di flusso che aiutano a identificare se l'utilizzo di TCP contribuisce alla qualità scarsa. 

#### <a name="tcp-investigations"></a>Indagini TCP

Nei modelli di CQD disponibili passare ai report dei flussi TCP per edificio e subnet usando il modello Reti gestite o Tutte le reti. A scopo di analisi dell'utilizzo di TCP, il processo è lo stesso, quindi la discussione è incentrata sulle conferenze.


##### <a name="remediation"></a>Correzione

Questo report identifica gli edifici e le subnet specifici che contribuiscono al volume di utilizzo TCP. È anche incluso un report aggiuntivo per identificare l'IP di Microsoft Relay usato nella chiamata per isolare le regole del firewall mancanti. Concentrare le azioni di correzione sugli edifici che hanno il volume più elevato di flussi TCP per massimizzare l'impatto.

La causa più comune dell'utilizzo di TCP è l'mancanza di regole di eccezione nei firewall o proxy. Nella prossima sezione verranno trattati i proxy, quindi per il momento è necessario concentrarsi sui firewall. Usando l'edificio o la subnet specificata, è possibile determinare quale firewall deve essere aggiornato.

| Correzione        | Linee guida     |
|--------------------|--------------------------------------|
| Configurare il firewall | Verificare che le porte e gli indirizzi IP di [Microsoft 365 o Office 365](https://aka.ms/o365ips) siano esclusi dal firewall. Per i problemi TCP relativi ai supporti multimediali, concentrare le iniziative iniziali su quanto segue:<ul><li>Verificare che le subnet dei supporti multimediali del client 13.107.64.0/18 e 52.112.0.0/14 siano presenti nelle regole del firewall.</li><li>Le porte UDP 3478-3481 sono le porte dei supporti richieste e devono essere aperte, altrimenti il client non riuscirà a ottenere la porta TCP 443.</li></ul> |
| Verifica             | Usare lo [strumento di](https://www.microsoft.com/download/details.aspx?id=53885) valutazione della rete Microsoft per verificare la presenza di problemi di connettività a specifici indirizzi IP di Microsoft 365 o Office 365 e porte dall'edificio o dalla subnet interessata.    |

### <a name="http-proxy"></a>Proxy HTTP

I proxy HTTP non sono il percorso preferito per stabilire sessioni multimediali, per molti motivi. Molti contengono funzionalità di ispezione profonda dei pacchetti che possono impedire il completamento delle connessioni al servizio e introdurre interruzioni. Inoltre, quasi tutti i proxy forzano TCP anziché consentire UDP, che è consigliato per una qualità audio ottimale.

È sempre consigliabile configurare il client in modo da connettersi direttamente ai servizi di Teams e Skype for Business. Questo è particolarmente importante per il traffico basato su elementi multimediali.


> [!IMPORTANT]
> È consigliabile caricare un [file di edificio](CQD-upload-tenant-building-data.md) valido in modo da poter distinguere tra flussi audio esterni durante l'analisi dell'utilizzo del proxy. 


#### <a name="http-proxy-usage"></a>Utilizzo proxy HTTP

Il report sul flusso del proxy HTTP in questa sezione del modello è molto simile ai report TCP. Non verifica se le chiamate sono di qualità scarsa o buona, ma se la chiamata è connessa tramite HTTP.

![Screenshot del report di flussi audio che usano HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analisi

Si desidera visualizzare il numero massimo possibile di flussi multimediali HTTP. Se sono presenti flussi che attraversano il proxy, consultare il team di rete per assicurarsi che siano presenti le esclusioni appropriate in modo che i client siano instradamento diretto alle subnet multimediali di Teams o Skype for Business Online.

Se l'organizzazione ha un solo proxy Internet, verificare le esclusioni corrette di URL e intervalli di indirizzi IP per [Microsoft 365 o Office 365.](https://aka.ms/o365ips) Se nell'organizzazione sono configurati più proxy Internet, usare il sotto-report HTTP per isolare l'edificio o la subnet interessata.

Per le organizzazioni che non possono bypassare il proxy, assicurati che il client Skype for Business sia configurato per l'accesso corretto quando è situato dietro un proxy, come indicato nell'articolo [Skype for Business](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)deve utilizzare il server proxy per accedere invece di provare la connessione diretta. 


#### <a name="http-proxy-investigations"></a>Indagini sul proxy HTTP

Questo report identifica gli edifici e le subnet specifici che contribuiscono all'utilizzo di HTTP.


##### <a name="remediation"></a>Correzione

Ti [consigliamo](proxy-servers-for-skype-for-business-online.md) di bypassare sempre i proxy per Skype for Business e Teams, in particolare per il traffico multimediale. I proxy non rendono Skype for Business più sicuro, perché il suo traffico è già crittografato. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi causano un'esperienza negativa con audio, video e condivisione dello schermo, in cui i flussi in tempo reale sono essenziali.

La causa più comune dell'utilizzo di HTTP è l'mancanza di regole di eccezione nei proxy. Usando l'edificio o la subnet disponibile, è possibile determinare rapidamente quale proxy deve essere configurato per il bypass multimediale.

Verificare che gli FQDN necessari per [Microsoft 365 o Office 365](https://aka.ms/o365ips) siano presenti nell'elenco degli indirizzi vuoti nel proxy.

## <a name="endpoint-investigations"></a>Indagini degli endpoint

Questa sezione è incentrata sulle attività per la creazione di report sulle versioni client e sull'uso di dispositivi certificati. Sono disponibili report per delineare l'utilizzo per le versioni client, il tipo di client, i dispositivi di acquisizione e i driver (microfono), i dispositivi di acquisizione video e Wi-Fi fornitore e driver.

> [!NOTE]
> In questo articolo non sono inclusi tutti i report inclusi nei modelli; Tuttavia, i metodi di indagine descritti di seguito sono ancora applicabili. Per altre informazioni, fare riferimento alla descrizione del singolo report.

### <a name="client-versions"></a>Versioni client

Questi report sono incentrati sull'identificazione delle versioni client di Skype for Business in uso e sul volume relativo nell'ambiente.

> [!IMPORTANT]
> Attualmente i client di Teams vengono distribuiti e aggiornati automaticamente tramite la rete per la distribuzione di contenuti di Azure e verranno mantenuti aggiornati dal servizio. Di conseguenza, non è necessario monitorare le versioni client di Teams (a meno che non si disvola l'aggiornamento automatico, scelta non consigliata).

A meno che non si escludono i dati dei partecipanti federati, questi report includeranno la telemetria del client da endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per il secondo ID tenant impostato [all'ID tenant dell'organizzazione.](CQD-data-and-reports.md#how-to-find-your-tenant-id) In alternativa, è possibile usare un filtro [url per](CQD-data-and-reports.md#url-filters) escludere la telemetria dei partecipanti federati.



#### <a name="remediation"></a>Correzione

Uno dei principali obiettivi di un'esperienza utente di alta qualità è garantire che i client gestiti siano in esecuzione versioni aggiornate di Skype for Business, oltre a garantire che i driver audio, video, di rete e USB di supporto siano aggiornati. Ciò offre diversi vantaggi, tra cui: 

-   È più facile gestire alcune versioni rispetto a molte.
-   Offre un livello di coerenza dell'esperienza utente.
-   Semplifica la risoluzione dei problemi relativi alla qualità e all'usabilità delle chiamate.
-   Microsoft apporta continuamente miglioramenti generali e ottimizzazioni in tutto il prodotto. La ricezione di questi aggiornamenti da parte degli utenti riduce il rischio di insod0>un problema già risolto.

Limitare la distribuzione alle versioni client meno di sei mesi fa consente di migliorare l'esperienza utente complessiva e la gestibilità riducendo il numero di versioni che devono essere supportate.

Se si usa solo Office a portata di clic, si verrà automaticamente entro la finestra dei sei mesi. Non sono necessarie altre azioni.

Se si ha una combinazione di pacchetti A scelta e programma di installazione (MSI), è possibile usare il report per verificare che i client MSI vengano aggiornati regolarmente. Se si nota che i clienti sono in ritardo, collaborare con il team responsabile della gestione degli aggiornamenti di Office e assicurarsi che approvino e distribuiscano regolarmente le patch dei client.

È anche importante considerare e verificare che vengano corretti anche i driver di rete, video, USB e audio. Questi driver possono essere facilmente trascurati e non includerli nella strategia di gestione delle patch.

I numeri di versione di Skype for Business sono disponibili tramite i collegamenti seguenti:

-   [Informazioni sulla versione per gli aggiornamenti a Microsoft 365 Apps](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Cronologia degli aggiornamenti per Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Download e aggiornamenti per Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivi

Per usare il report sul microfono, è necessario comprendere il concetto di Mean Opinion Score (MOS). MOS è la misura standard gold per misurare la qualità audio percepita. È rappresentato come un valore intero compreso tra 0 e 5.

La base di tutte le misure della qualità vocale è il modo in cui una persona percepisce la qualità del discorso. Dal momento che è influenzata da una vita umana, è intrinsecamente soggettiva. Esistono diverse metodologie per i test soggettivi. La maggior parte delle misure di qualità vocale si basa su una scala ACR (Absolute Categorization Rating).

In un test soggettivo ACR, un numero statisticamente significativo di persone valuta la loro qualità dell'esperienza su una scala da 1 (bassa) a 5 (eccellente). La media dei punteggi è il MOS. Il MOS risultante dipende dalla gamma di esperienze esposte al gruppo e dal tipo di esperienza valutata.

Poiché non è possibile eseguire test soggettivi della qualità vocale per un sistema di comunicazione in tempo reale, Microsoft Teams e Skype for Business generano valori MOS utilizzando algoritmi avanzati per prevedere obiettivomente i risultati di un test soggettivo.

Il set disponibile di MOS e metriche associate fornisce una visione d'insieme della qualità dell'esperienza che viene consegnata agli utenti da un dispositivo audio. 

Fornendo agli utenti dispositivi certificati per Teams e Skype for Business, riduci la probabilità di riscontrare esperienze negative a causa del dispositivo stesso (che è più probabile, ad esempio, con altoparlanti e microfoni integrati nel portatile). Per altre informazioni, vedere questi articoli sul programma [di certificazione](/SkypeForBusiness/certification/overview) e sul catalogo di [soluzioni partner.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

I report sui dispositivi vengono usati per valutare l'utilizzo dei dispositivi in base al volume e al punteggio MOS (solo audio) e sono disponibili nei modelli di accompagnamento in Client & dispositivi. 

> [!IMPORTANT]
> A meno che non si escludono i dati dei partecipanti federati, questi report includeranno la telemetria del client da endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per il secondo **ID tenant** impostato all'ID tenant [dell'organizzazione.](CQD-data-and-reports.md#how-to-find-your-tenant-id) ALternatively, è possibile usare un filtro [URL](CQD-data-and-reports.md#url-filters) per escludere la telemetria dei partecipanti federati.


> [!Note]
> Quando visualizzi questo report, potresti notare che lo stesso dispositivo è stato segnalato più volte. Ciò è dovuto al modo in cui il dispositivo viene segnalato a CQD. Le differenze nell'hardware e nelle impostazioni locali del sistema operativo causano differenze nella modalità di registrazione dei dati dei dispositivi.

##### <a name="remediation"></a>Correzione

In genere, è necessario individuare e sostituire gradualmente i dispositivi non certificati e sostituirli con dispositivi certificati. Di seguito sono riportate alcune considerazioni da tenere in considerazione quando si esaminano i report sui dispositivi:

-   I dispositivi in uso sono certificati per Teams e Skype for Business? 
-   Puoi identificare gli utenti di un dispositivo specifico utilizzando [l'analisi delle chiamate per utente.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Verificare che siano installati i driver di dispositivo più recenti e che il dispositivo non sia connesso tramite un hub USB o un alloggiamento di espansione. 
-   Quante versioni diverse di vari driver sono in uso? Vengono regolarmente patchate? Assicurarsi che i driver audio, video e Wi-Fi vengano regolarmente corretti consente di eliminare questi problemi come fonte di problemi di qualità e rendere l'esperienza utente più prevedibile e coerente.

##### <a name="audio"></a>Audio

L'attività successiva è determinare l'utilizzo complessivo dei [dispositivi audio certificati.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) È consigliabile che almeno l'80% di tutti i flussi audio usi un dispositivo audio certificato. Per ottenere risultati ottimali, esportare il report sui dispositivi con microfono in Excel per calcolare l'utilizzo di dispositivi certificati o approvati. Le organizzazioni in genere mantengono un elenco di tutti i dispositivi approvati, quindi filtrare e ordinare i dati devono essere semplici.

##### <a name="video"></a>Video

Anche i driver video sono importanti per essere aggiornati. Assicurarsi che le schede video vengano regolarmente corretti consente di escludere i driver video come fonte di qualità scarsa per i flussi video. [L'uso di dispositivi video](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) certificati garantisce un'esperienza utente uniforme e di alta qualità. Sono preferiti i dispositivi video che supportano la codifica nativa H.264, per ridurre l'utilizzo della CPU durante le videoconferenze.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi anche i driver devono essere corretti regolarmente e devono essere inclusi nella strategia di gestione delle patch. Molti problemi di qualità possono essere corretti mantenendo i driver di Wi-Fi aggiornati. Per altre informazioni su come ottimizzare l'infrastruttura Wi-Fi, vedere questo articolo sulla pianificazione Wi-Fi [distribuzione.](/skypeforbusiness/certification/networking-wifi)


## <a name="related-topics"></a>Argomenti correlati

[Usare Advisor per Teams](use-advisor-teams-roll-out.md)

[Preparare la rete per Teams](prepare-network.md)

[Principi della connettività di rete di Office 365](https://aka.ms/pnc)

[Analisi e creazione di report di Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gestire i dispositivi in Teams](device-management.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)
