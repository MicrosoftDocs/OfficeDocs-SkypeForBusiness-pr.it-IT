---
title: Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Informazioni su come analizzare e gestire le prestazioni dei supporti multimediali in tempo reale in Microsoft Teams tramite Call Quality Dashboard (CQD).
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 45a52e438fb74286a571cd81461e3de174f9a38f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675058"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams 

Questo articolo aiuta l'amministratore Teams o il supporto tecnico e tecnico a sviluppare un processo per il monitoraggio e la gestione della qualità delle chiamate e delle riunioni per l'organizzazione tramite Microsoft Teams Call Quality Dashboard (CQD). Le nostre linee guida evidenziano scenari di qualità audio perché qualsiasi miglioramento della rete apportata per migliorare l'esperienza audio si tradurrà in miglioramenti in video e condivisione.

La chiave di questa guida sono i due [modelli di Call Quality Dashboard curati](https://aka.ms/QERtemplates) . È consigliabile scaricarli prima di seguire le indicazioni in questo articolo.

Questo articolo presuppone che [CQD](turning-on-and-using-call-quality-dashboard.md) sia già stato configurato.


## <a name="categories-to-monitor-and-maintain"></a>Categorie da monitorare e gestire

Dopo aver distribuito riunioni e comandi vocali in Teams, è necessario un piano per il monitoraggio e la manutenzione continui. In questo modo, Teams funzionerà sempre in modo ottimale. Questo piano deve includere le aree principali elencate di seguito. È inoltre consigliabile stabilire obiettivi per le metriche di qualità e un piano per la risoluzione e l'isolamento dei problemi quando si verificano.

<table>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Qualità chiamata</strong></td>
<td>
<p>Suddividono le metriche per chiamate interne (all'interno dell'organizzazione, ad esempio VPN, WiFi, cablate) o chiamate esterne</p>
<p>Suddividere le metriche creando o utilizzando la rete</p>
<p>Chiamate VPN</p>
<p>Chiamate tramite TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Affidabilità delle chiamate</strong></td>
<td><p>Identificare e correggere eventuali problemi di rete o del firewall</p>
<p>Ottenere informazioni approfondite sulle percentuali di configurazione delle chiamate e eliminare gli errori</p>
<p>Informazioni su dove si verifica la maggior parte degli errori di configurazione e di rilascio delle chiamate</p>
</td>
</tr>
<tr class="odd">
<td><strong>Sondaggio dell'utente</strong></td>
<td>
<p>Usare i dati di Valuta la mia chiamata per informazioni sull'esperienza effettiva degli utenti</p>
<p>Dove si verificano le esperienze povere?</p>
<p>Correlare la scarsa esperienza con la qualità delle chiamate, l'affidabilità e i dispositivi</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivi</strong></td>
<td><p>Scopri quali microfoni e altoparlanti sono usati più comunemente e il loro impatto sulla qualità delle chiamate</p>
<p>I driver audio, video, USB e WiFi di supporto vengono regolarmente patchati?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Client</strong></td>
<td>
<p>Scopri quali tipi e versioni di client vengono utilizzati e il loro impatto sulla qualità e sull'affidabilità delle chiamate  </p>
</ol></td>
</tr>
</tbody>
</table>

Valutando e rimediando continuamente le aree descritte in questo articolo, è possibile ridurre il loro potenziale per influire negativamente sugli utenti. La maggior parte dei problemi degli utenti può essere raggruppata nelle categorie seguenti:

-   Configurazione proxy o firewall incompleta
-   Scarsa copertura Wi-Fi
-   Larghezza di banda insufficiente
-   VPN
-   Driver e versioni client non coerenti o obsolete
-   Dispositivi audio non ottimizzati o incorporati
-   Subnet o dispositivi di rete problematici

Attraverso una pianificazione e una progettazione appropriate prima di distribuire Teams o Skype for Business Online, è possibile ridurre la quantità di risorse necessarie per mantenere esperienze di alta qualità.

Questo articolo è incentrato sull'uso di Call Quality Dashboard (CQD) Online come strumento principale per segnalare e analizzare ogni area, con una particolare enfasi sull'audio per massimizzare l'adozione e l'impatto. Tutti i miglioramenti apportati alla rete per migliorare l'esperienza audio si tradurranno direttamente in miglioramenti nella condivisione di video e desktop.

Per accelerare la valutazione, vengono forniti [due modelli di Call Quality Dashboard curati](https://aka.ms/qertemplates) : uno è per la gestione di tutte le reti e l'altro è filtrato solo per le reti gestite (interne). Anche se i report del modello Tutte le reti sono configurati per visualizzare informazioni sulla costruzione e sulla rete, possono comunque essere usati mentre si lavora alla raccolta e al caricamento di informazioni sull'edificio. Il caricamento delle informazioni sull'edificio in Call Quality Dashboard consente al servizio di migliorare i report aggiungendo informazioni personalizzate sull'edificio, la rete e la posizione, distinguendo al contempo le subnet interne da esterne. Per altre informazioni, vedere [Creazione di mapping](CQD-building-mapping.md).

### <a name="intended-audience"></a>Destinatari

Questo articolo è stato progettato per essere usato dagli stakeholder di partner e clienti con ruoli come Lead/Architetto collaborazione, Consulente, Responsabile gestione modifiche/Adozione, Responsabile supporto/Help Desk, Responsabile rete, Responsabile desktop e Amministrazione IT.

Questo articolo è destinato anche all'uso da parte dei campioni di qualità designati. Per altre informazioni, vedere [Il ruolo di Quality Champion](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Che cos'è la qualità?

In questo contesto, la qualità è una combinazione di metriche di servizio ed esperienza utente.


### <a name="service-metrics"></a>Metriche del servizio

Le metriche del servizio sono costituite da metriche basate su client specifiche. Durante ogni chiamata, il client raccoglie la telemetria per la chiamata e invia un report alla fine di ogni chiamata, accessibile successivamente in Call Quality Dashboard o [nell'analisi delle chiamate per utente](set-up-call-analytics.md). Queste metriche includono, ma non sono limitate a:

-   Flusso scadente (in ingresso e in uscita)
-   Setup Failure Rate
-   Drop Failure Rate


#### <a name="poor-stream-rate"></a>Stream rate scadente

La scarsa frequenza di trasmissione (PSR) rappresenta la percentuale complessiva di flussi di scarsa qualità dell'organizzazione. Questa metrica è progettata per evidenziare le aree in cui l'organizzazione può concentrare gli sforzi per ottenere il maggiore impatto sulla riduzione di questo valore e migliorare l'esperienza utente, motivo per cui le [reti gestite](#managed-versus-unmanaged-networks) sono l'obiettivo principale quando si esamina psr. Anche gli utenti esterni sono importanti, ma l'analisi è diversa a seconda dell'organizzazione. È consigliabile fornire procedure consigliate per gli utenti esterni ed esaminare le chiamate esterne in modo indipendente dall'intera organizzazione.

La misurazione effettiva in Call Quality Dashboard varia in base al carico di lavoro, ma ai fini di questo articolo ci concentriamo principalmente sulla misurazione della _percentuale di qualità scarsa audio_ . PSR è costituito dalle cinque medie metriche di rete descritte nella tabella seguente. Per classificare un flusso come scadente, è necessario che una sola metrica superi la soglia definita. Call Quality Dashboard fornisce il messaggio "Poor Due To..." misura per comprendere meglio la condizione che ha causato la classificazione del flusso come scadente. Per altre informazioni, vedere [Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> Call Quality Dashboard fornisce il messaggio "Poor due to..." misura per comprendere meglio la condizione che ha causato la classificazione del flusso come scadente.


##### <a name="audio-poor-quality-metrics"></a>Metriche di qualità scarsa audio

| Media metrica     | Descrizione     | Esperienza utente |
|-------------|-----------------|-----------------|
| Jitter \>30 ms        | Si tratta della variazione media del ritardo tra pacchetti successivi. Teams e Skype for Business possono adattarsi ad alcuni livelli di instabilità tramite buffering. Solo quando l'instabilità supera il buffering, un partecipante nota gli effetti dell'instabilità.      | I pacchetti che arrivano a velocità diverse fanno sembrare robotica la voce di un altoparlante.   |
| Tasso di perdita \>pacchetti 10% o 0,1        | Spesso viene definita come percentuale di pacchetti persi. La perdita di pacchetti influisce direttamente sulla qualità audio, da piccoli pacchetti singoli persi che non hanno quasi alcun impatto sulle perdite burst back-to-back che causano il taglio completo dell'audio.     | I pacchetti eliminati e che non arrivano alla destinazione prevista causano lacune nei supporti, con conseguente sillabe e parole perse e video e condivisione discontinui. |
| Tempo di andata e ritorno \>500 ms        | Questo è il tempo necessario per ottenere un pacchetto IP dal punto A al punto B e di nuovo al punto A. Questo ritardo di propagazione della rete è legato alla distanza fisica tra i due punti e alla velocità della luce e include un sovraccarico aggiuntivo da parte dei vari dispositivi nel percorso di rete.      | I pacchetti che impiegano troppo tempo per arrivare a destinazione causano un effetto walkie-talkie.   |


##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Perché preferiamo usare i flussi invece delle chiamate?

Flussi facci sapere quale parte della chiamata era scadente, in uscita o in arrivo. Quando si esaminano i dati di analisi delle chiamate per una chiamata scadente, determinare se la chiamata è stata scadente dovuta al flusso del chiamante (in uscita) o al flusso del destinatario della chiamata (in ingresso). Determinare quale flusso influisce sulla qualità delle chiamate è ancora più importante per le conferenze. Se si esaminano solo i dati delle chiamate, si vedrà il numero di conferenze a cui partecipa una persona, ma non si vedranno quali persone sono altoparlanti attivi, eseguendo la maggior parte della condivisione dello schermo.

I dati delle chiamate consentono di ottenere metriche di utilizzo, ma non necessariamente causano la causa principale della scarsa qualità delle chiamate. Osservando la direzione del flusso, è possibile identificare fattori come una chiamata che non fa parte di una rete gestita, una chiamata di un non dipendente (ad esempio un fornitore o un utente di un'altra rete). In questi casi, se la connessione di rete dell'altra persona era scadente, l'intera chiamata verrà contrassegnata come scadente. Non è possibile eseguire alcuna operazione sui fattori esterni, quindi questi dati non sono utili.

La direzione del flusso può anche aiutarti a identificare i dispositivi o i client problematici.

 - Ad esempio, se hai un budget limitato per i dispositivi e vuoi fornire i dispositivi solo per gli utenti audio pesanti, usa il report sull'utilizzo dell'audio (VoIP) e filtra i flussi in uscita e le conferenze. Cerca utenti audio ad alto volume che parlano con microfoni incorporati, che potrebbero essere correlati a una qualità delle chiamate più scarsa (e potresti voler fornire dispositivi audio a queste persone). Per maggiore chiarezza, è possibile filtrare in base all'utilizzo dei pacchetti, per consentire agli utenti audio con volumi particolarmente elevati di prendere di mira. 

  - Un altro esempio riguarda la condivisione dello schermo. Se un cliente usa un vecchio client Teams, potrebbero esserci ripercussioni sulle prestazioni di condivisione dello schermo. È possibile risolvere questo problema assegnando la priorità agli aggiornamenti del client per le persone che effettuano molte condivisioni dello schermo.

 - Identificando la direzione di un flusso che causa una bassa qualità delle chiamate, è possibile determinare se si è verificato un problema di QoS o relativo alla larghezza di banda. Se la QoS non è stata completamente implementata o se si contrassegna solo i pacchetti nel client e non nel flusso in ingresso, la qualità delle chiamate potrebbe risultare più scarsa. Osservando la direzione del flusso, è possibile ottenere una visualizzazione più granulare di perdita di pacchetti, latenza o instabilità in una direzione specifica. 

   - Si supponga ad esempio che un utente si lamenta dell'audio robotico su una connessione cablata (instabilità). Osservando il flusso e la direzione, è possibile determinare che il problema si verifica nel flusso in ingresso, solo per un set specifico di subnet. Dopo aver fornito queste informazioni al team di rete, il team potrà individuarle in un acceleratore WAN non configurato correttamente che non stava bypassando il traffico multimediale. Quando il team di rete riconfigura l'acceleratore WAN, l'instabilità scompare e la qualità delle chiamate migliora. 


#### <a name="setup-failure-rate"></a>Setup Failure Rate

Il tasso di errore di configurazione, altrimenti noto come total _call setup failure percentage_ in CQD, è il numero di flussi in cui non è stato possibile stabilire il percorso del supporto tra gli endpoint all'inizio della chiamata.

Rappresenta qualsiasi flusso multimediale che non è stato possibile stabilire. Data la gravità dell'impatto di questo problema sull'esperienza utente, l'obiettivo è quello di ridurre questo valore al più vicino allo zero possibile. Un valore elevato per questa metrica è più comune nelle nuove distribuzioni con regole del firewall incomplete rispetto a una distribuzione matura, ma è comunque importante guardarla regolarmente.

Questa metrica viene calcolata prendendo il numero totale di flussi che non sono stati configurati diviso per il numero totale di flussi che hanno inviato un record di dettaglio chiamata (CDR) riuscito:

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count / Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Drop Failure Rate

Il tasso di errore di rilascio, noto anche come misura _Total Call Dropped Failure Percentage_ in CQD, è la percentuale di flussi correttamente stabiliti in cui il percorso del supporto non è terminato normalmente.

Rappresenta qualsiasi flusso multimediale che è terminato in modo imprevisto. Anche se l'impatto non è così grave come un flusso che non è riuscito a configurare, influisce comunque negativamente sull'esperienza utente. Cadute improvvise e frequenti dei supporti non solo possono avere un grave impatto sull'esperienza utente, ma provocano la necessità per gli utenti di riconnettersi, con conseguente perdita di produttività (per non parlare della frustrazione).

La metrica viene calcolata prendendo il numero totale di flussi caduti diviso per il conteggio totale dei flussi che sono stati configurati correttamente:

-   **Drop Failure Rate** = Total Call Drop Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Definire le metriche di destinazione

In questa sezione vengono illustrate alcune delle metriche di base dei servizi utilizzate per valutare l'integrità dei servizi. Valutando e spingendo continuamente a mantenere queste metriche al di sotto dei relativi obiettivi definiti, sarà possibile garantire agli utenti un'esperienza di qualità delle chiamate coerente e affidabile. Come punto di partenza, usare le destinazioni suggerite nella tabella seguente. Modificare gli obiettivi in base alle esigenze per raggiungere gli obiettivi aziendali.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo di rete</th><th rowspan="1">Obiettivi di qualità</th><th colspan="2">Obiettivi di affidabilità</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Setup Failure Rate</th><th>Drop Failure Rate</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Nel complesso</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conferenze</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Cablata interna</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>interno Wi-Fi 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>interno Wi-Fi 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Nel complesso</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Cablata/Wi-Fi interna da 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Cablata/Wi-Fi 5 GHz complessiva</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Nel complesso</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Esperienza utente

Analizzare l'esperienza dell'utente è più arte che scienza, perché le metriche raccolte qui non sempre significano che c'è un problema con la rete o il servizio, ma piuttosto, semplicemente indicano che l'utente percepisce un problema. Call Quality Dashboard include un meccanismo di sondaggio integrato , Vota la mia chiamata (RMC) per valutare l'esperienza utente complessiva. RMC ti fornirà informazioni approfondite sulle seguenti domande dal punto di vista degli utenti:

-   So come usare la soluzione?
-   La soluzione è facile da usare e intuitiva e supporta le mie esigenze di comunicazione quotidiane?
-   La soluzione mi aiuta a svolgere il mio lavoro?
-   Qual è la mia percezione generale della soluzione?
-   Posso usare la soluzione in qualsiasi momento, indipendentemente da dove mi trovo?
-   È possibile configurare e gestire una chiamata?

#### <a name="rate-my-call"></a>Valuta la mia chiamata 

Rate My Call (RMC) è integrato in Teams e Skype for Business. Viene visualizzata automaticamente dopo una ogni 10 chiamate, o al 10%. Questo breve sondaggio chiede all'utente di valutare la chiamata e fornire un contesto per capire il motivo per cui la qualità della chiamata potrebbe essere scadente. Una valutazione uno o due è considerato scadente, tre a quattro è buono, e cinque è eccellente. Anche se si tratta di un indicatore di ritardo, questa è una metrica utile per scoprire i problemi che le metriche del servizio possono perdere.

> [!Note]
> Il fattore umano: gli utenti spesso ignorano il sondaggio quando la qualità della chiamata è buona e la compilano quando la qualità della chiamata è cattiva. Di conseguenza, i report RMC potrebbero essere obliqui verso il lato scarso anche se le metriche del servizio sono buone.

È possibile usare Call Quality Dashboard per creare report sulle risposte degli utenti di RMC e i report di esempio sono inclusi nel modello CQD. Tuttavia, non vengono discussi in dettaglio in questo articolo. 

#### <a name="client-and-device-readiness"></a>Conformità di client e dispositivi

È necessaria una solida strategia per client e dispositivi per garantire agli utenti un'esperienza utente coerente e positiva. Alcuni principi chiave guidano ogni strategia di conformità.

##### <a name="client-readiness"></a>Conformità dei clienti

Mantenere aggiornato il client Teams assicura agli utenti di ottenere sempre la migliore esperienza possibile. Microsoft rilascia [aggiornamenti frequenti al client Teams](teams-client-update.md) (l'aggiornamento viene installato automaticamente in background, a meno che questa funzionalità non sia stata disattivata, cosa che non è consigliabile). È anche importante ricordare di applicare patch a driver di rete, video, USB e audio, perché spesso vengono trascurati e possono influire sulla qualità delle chiamate e delle riunioni. Valutare l'aggiunta di driver di rete, Wi-Fi, video, USB e audio al processo di gestione delle patch corrente.


##### <a name="device-readiness"></a>Conformità dei dispositivi

Nessuna singola strategia può influire sull'esperienza utente più della strategia di preparazione del dispositivo. Ad esempio, gli utenti che si affidano agli altoparlanti e al microfono del portatile riscontreranno molti rumori di sottofondo nelle chiamate e nelle riunioni. Teams è progettato per funzionare con quasi tutti i dispositivi, ma se si verificano problemi relativi al dispositivo, vedi [Telefono per Teams](./devices/phones-for-teams.md).


### <a name="categories-of-quality"></a>Categorie di qualità

Rendere operativa una serie di procedure di gestione della qualità, che offre le migliori possibilità di una buona qualità delle chiamate e delle riunioni. Un piano di gestione di buona qualità riguarda queste categorie:

-   **Rete:** Qualità audio incentrata sulla metrica PSR (Poor Stream Ratio), sull'utilizzo TCP, sulle subnet cablate e wireless e sull'identificazione dell'uso di proxy HTTP e VPN

-   **Endpoint:** Dispositivi audio e client aggiornati

-   **Gestione dei servizi:** Questa categoria è composta da due sezioni:

    -   Prima di tutto, è responsabilità di Microsoft gestire e gestire i servizi online Teams e Skype for Business.

    -   In secondo luogo, le attività che l'organizzazione gestisce per garantire un accesso affidabile al servizio, ad esempio l'aggiornamento delle informazioni di creazione e la gestione dei firewall per i nuovi indirizzi IP Office 365 man mano che viene aggiunta l'infrastruttura al servizio.

![Graph delle categorie di qualità in un'organizzazione.](media/qerguide-image-categories.png "Le categorie di qualità in un'organizzazione: gestione dei servizi, endpoint e rete.")

Esaminare l'elenco seguente di attività consigliate per mantenere la qualità. È consigliabile eseguire queste attività regolarmente, ad esempio ogni settimana.

#### <a name="service-management-tasks"></a>Attività di gestione dei servizi

Queste attività vanno dal garantire che la larghezza di banda sia sufficiente per raggiungere il servizio senza saturare i collegamenti Internet, convalidare che la qualità del servizio (QoS) sia attiva in tutte le aree di rete gestite e rimanere aggiornati su [Office 365 intervalli IP sui firewall](/microsoft-365/enterprise/urls-and-ip-address-ranges).

#### <a name="network-tasks"></a>Attività di rete

Esistono due categorie di attività di rete: affidabilità e qualità. L'affidabilità è incentrata sulla misurazione della capacità dell'utente di effettuare chiamate con successo e rimanere connessi. La qualità è incentrata sulla telemetria aggregata inviata a Teams e Skype for Business Online dal client dell'utente durante la chiamata e dopo la sua fine. 

Considerato l'impatto critico che l'affidabilità ha sull'esperienza utente, è consigliabile valutare e analizzare le metriche di affidabilità prima di approfondire la qualità. 

#### <a name="endpoints-tasks"></a>Attività degli endpoint

L'attività principale in questa categoria rimuove tutti gli ostacoli agli [aggiornamenti regolari dei client Teams](teams-client-update.md). Per impostazione predefinita, Teams si aggiorna automaticamente regolarmente, a meno che non si disattivi tale impostazione, operazione non consigliata. 

È inoltre consigliabile monitorare i dispositivi e fornire aggiornamenti ogni volta che si identificano problemi relativi a un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usare Call Quality Dashboard per gestire la qualità delle chiamate

Dopo aver [configurato Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md), è possibile iniziare a usarlo per gestire la qualità delle chiamate e delle riunioni per l'organizzazione.

La maggior parte dei problemi relativi alle prestazioni di Teams rientrano nelle categorie seguenti:

-   Configurazione proxy o firewall incompleta
-   Scarsa copertura Wi-Fi
-   Larghezza di banda insufficiente
-   VPN
-   Driver e versioni client non coerenti o obsolete
-   Dispositivi audio non ottimizzati o incorporati
-   Subnet o dispositivi di rete problematici

Se si impiega del tempo prima di implementare Teams per valutare queste aree e correggere eventuali carenze, si ridurrà l'impegno necessario per mantenere un'esperienza di Teams di alta qualità per tutti gli utenti. Per valutare la rete in preparazione dell'implementazione di Teams, leggere [Assistente per Teams](use-advisor-teams-roll-out.md) e [Preparare la rete per Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Aspettative con CQD

Utilizzare call quality dashboard (CQD) per ottenere informazioni approfondite sulla qualità delle chiamate effettuate utilizzando Teams e servizi di Skype for Business. Call Quality Dashboard è progettato per aiutare Teams e Skype for Business amministratori e tecnici di rete a ottimizzare la rete e a tenere sotto controllo la qualità, l'affidabilità e l'esperienza utente. Call Quality Dashboard esamina la telemetria aggregata per un'intera organizzazione, in cui possono emergere modelli generali; in questo modo è possibile eseguire valutazioni informate e correggere i piani. Call Quality Dashboard fornisce report di metriche che forniscono informazioni approfondite sulla qualità complessiva, l'affidabilità e l'esperienza utente.

Call Quality Dashboard, sebbene utile per analizzare tendenze e subnet, non sempre fornisce una causa specifica per un determinato scenario. È importante comprenderlo e impostare l'aspettativa corretta quando si usa Call Quality Dashboard:

-   Call Quality Dashboard non fornirà la causa principale per ogni scenario
-   Call Quality Dashboard non conterrà flussi Sistema telefonico o Audioconferenza
-   Call Quality Dashboard indicherà le aree per un'ulteriore indagine sulla base delle tendenze

### <a name="cqd-reports-overview"></a>Panoramica dei report di Call Quality Dashboard

Usare il menu a discesa nella parte superiore dello schermo per aprire un report. Per un elenco dei dati forniti in ogni report, vedere [Dati disponibili nei report di Call Quality Dashboard](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novità di gennaio 2020: [Scaricare Power BI modelli di query per Call Quality Dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality Dashboard.


### <a name="teams-vs-skype-for-business"></a>confronto tra Teams e Skype for Business

Call Quality Dashboard può eseguire report su Teams e Skype for Business. In alcuni casi, tuttavia, può essere necessario sviluppare un report per esaminare Teams telemetria separatamente da Skype for Business.

#### <a name="summary-reports"></a>Report di riepilogo

Per modificare la pagina dei report di riepilogo in modo da visualizzare solo Teams o Skype for Business, selezionare il menu a discesa **Filtro prodotti** nella parte superiore dello schermo e quindi selezionare il prodotto desiderato.

![Screenshot del menu a discesa che mostra le opzioni di filtro.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Report dettagliati

Per filtrare tutti i report dettagliati, nella barra del browser aggiungere quanto segue alla fine dell'URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Esempio:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Per altre informazioni sui filtri URL, vedere [Report di filtro](CQD-data-and-reports.md#report-filters) più avanti in questa sezione.

Per filtrare un singolo report dettagliato, aggiungere il filtro ``Is Teams`` al report e impostarlo su Vero o Falso.

![Screenshot della pagina Aggiungi filtro.](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Reti gestite o non gestite

Per impostazione predefinita, tutti gli endpoint in Call Quality Dashboard vengono classificati come esterni. Non appena viene introdotto un file building, è possibile iniziare a esaminare i dati degli endpoint gestiti. Come descritto in precedenza, le reti in Call Quality Dashboard sono definite come:

-   Una _rete gestita_, spesso definita interna o interna, può essere influenzata e controllata dall'organizzazione. Sono incluse la LAN interna, la WAN remota e la VPN.
-   Una _rete non gestita_, spesso definita esterna o esterna, non può essere influenzata o controllata dall'organizzazione. Un esempio di rete non gestita è una rete alberghiera o aeroportuale.

### <a name="dimensions-measures-and-filters"></a>Dimensioni, misure e filtri

Una query CQD ben formata contiene tutti e tre i parametri seguenti:

-   **Dimensione:** Come si vogliono usare i dati come pivot.

-   **Misura:** Su cosa voglio riferire.

-   **Filtro:** Come si vuole ridurre il set di dati restituito dalla query.

Un altro modo per osservarlo è che una _dimensione_ è la funzione di raggruppamento, una _misura_ è i dati a cui sono interessato e un _filtro_ è il modo in cui si vogliono limitare i risultati a quelli rilevanti per la query.

Un esempio di query ben formata è **Show me Poor Flussi [Measure] by Subnet [Dimension] for Building 6 [Filter].An example of a well-formed query is Show me Poor Flussi [Measure] by Subnet [Dimension] for Building 6 [Filter]**. Per ulteriori informazioni, vedere [Dimensioni e misure disponibili in Call Quality Dashboard](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Primo contro secondo 

Molte delle dimensioni e misure in Call Quality Dashboard sono classificate come prime o secondi. Call Quality Dashboard non usa i campi chiamante/chiamato, che sono stati rinominati _per primi_ e _secondi_ perché sono in corso passaggi tra il chiamante e il destinatario della chiamata. La logica seguente determina quale endpoint coinvolto viene etichettato come primo:

-   **Il primo** endpoint sarà sempre un endpoint server (Conference Server, Mediation Server e così via) se un server è coinvolto nello stream o nella chiamata.

-   **Il secondo** endpoint sarà sempre un endpoint client, a meno che lo stream non sia tra due endpoint server.

-   Se entrambi gli endpoint sono dello stesso tipo, la prima scelta si basa sull'ordinamento interno della categoria agente utente. Ciò assicura che l'ordinamento sia coerente.

Per altre informazioni su come determinare il primo o il secondo endpoint quando sono entrambi uguali, vedere [Dimensioni e misure disponibili in Call Quality Dashboard](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="stream-vs-call"></a>Confronto tra stream e chiamata

È necessario comprendere la differenza tra una chiamata e un flusso per scegliere correttamente le dimensioni o le misure da esaminare in Call Quality Dashboard. Sebbene CQD sia incentrato principalmente sui flussi, sono disponibili anche misurazioni basate su chiamata.

-   **Flusso:** Uno _stream_ esiste solo tra due endpoint. Esiste un solo flusso per ogni direzione e per la comunicazione sono necessari due flussi. Flussi sono utili per indagare su edifici, reti o subnet. In alcuni casi, sia chiamata che flusso vengono usati nel nome della misura (ad esempio, Call Setup Stream o Call Dropped Stream). Questi sono ancora classificati come flussi.

-   **Chiamare:** Una _chiamata_ è un raggruppamento di tutti i flussi di tutti i partecipanti. Una chiamata è costituita, come minimo, da due flussi. Una singola chiamata avrà almeno due endpoint, ognuno con un minimo di un flusso.

Per ulteriori indicazioni su se la dimensione o la misura fa riferimento a una chiamata o a un flusso, vedere [Dimensioni e misure disponibili in CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Chiamate buone, povere e non classificate

Una chiamata viene categorizzata come buona, scarsa o non classificata. Prendiamoci un attimo per parlare di ognuno in modo più dettagliato.

-   **Bene o povero:** Una chiamata buona o scadente è costituita da una chiamata che contiene un set completo di metriche di servizio, per le quali è stato generato e ricevuto un report QoE completo dal servizio. Per determinare se uno stream è buono o scadente, è descritto [in precedenza in questo articolo](#poor-stream-rate).

-   **Non classificato:** Un flusso non classificato non contiene un set completo di metriche di servizio. Queste possono essere chiamate brevi, in genere inferiori a 60 secondi, in cui non è stato possibile calcolare le medie e non è stato generato un report QoE. Il motivo più comune per cui le chiamate non sono state classificate è che l'utilizzo dei pacchetti è stato scarso o assente. Un esempio potrebbe essere un partecipante che partecipa a una riunione con l'audio disattivato e che non parla mai. Il partecipante riceve, ma non trasmette, contenuti multimediali. Senza la trasmissione di elementi multimediali, non saranno disponibili metriche per Call Quality Dashboard da usare per classificare il flusso multimediale in uscita dell'endpoint.

Per altre informazioni, vedere [Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subnet comuni

Le subnet comuni sono subnet private specifiche utilizzate da alberghi, reti domestiche, hotspot e aree simili. Queste subnet sono difficili da valutare a causa del loro uso diffuso. Se l'organizzazione usa una di queste subnet comuni, è consigliabile spostare la rete in un'altra subnet. In questo modo la creazione di report sarà più semplice in Call Quality Dashboard. Quando indicato, i report nel modello Tutte le reti sono stati configurati per escludere queste subnet per eliminarle come origine di scarsa qualità. Le subnet comuni sono definite di seguito; il loro impatto varierà in base all'organizzazione.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Durante l'analisi di una rete gestita che usa una subnet comune, è necessario usare la dimensione SECOND Reflexive Local IP per raggruppare le subnet. Questa dimensione contiene l'indirizzo IP pubblico dell'endpoint.


## <a name="reliability-investigations"></a>Indagini di affidabilità

Il primo passo per migliorare la qualità consiste nel valutare lo stato di affidabilità in tutta l'organizzazione. Poiché l'affidabilità è fondamentale per un'esperienza utente positiva, partiamo dai due componenti che misurano l'affidabilità:

1.  **Errori di configurazione:** Non è stato possibile stabilire la chiamata.

2.  **Errori di rilascio:** La chiamata è stata stabilita e terminata in modo imprevisto.

In questa sezione verranno illustrati i metodi per analizzare entrambe le aree.

> [!NOTE]
> Non tutti i report inclusi nei modelli sono descritti in questo articolo. Tuttavia, i metodi di indagine descritti di seguito sono ancora applicabili. Per altre informazioni, fare riferimento alla descrizione del singolo report.


### <a name="setup-failures"></a>Errori di configurazione

Assegnare la priorità alla correzione degli errori di configurazione in questa area, perché questi errori hanno un impatto negativo significativo sull'esperienza utente.

Avviare l'indagine valutando la percentuale di errori di configurazione complessive per l'organizzazione e quindi assegnare la priorità alle aree di indagine in base alla percentuale più elevata per edificio o rete. 

#### <a name="setup-failure-trend-analysis"></a>Analisi delle tendenze degli errori di configurazione

Questo report mostra la quantità totale di flussi, gli errori di configurazione del flusso e il tasso di errore di configurazione del flusso. Posizionare il puntatore su una delle colonne per visualizzare i singoli valori. 

##### <a name="analysis"></a>Analisi

Usando questo report, è possibile rispondere alle domande seguenti e determinare la linea d'azione successiva:

-   Qual è la percentuale totale di errore di configurazione delle chiamate per il mese corrente?

-   La percentuale di errore di configurazione totale delle chiamate è inferiore o superiore alla metrica di destinazione definita?

-   La tendenza al fallimento è peggiore o migliore del mese precedente?

-   La tendenza al fallimento è in aumento, costante o decrescente?

Indipendentemente dalle risposte a queste domande, prenditi il tempo di indagare ulteriormente utilizzando i sotto-report complementari per cercare i singoli edifici o subnet che potrebbero richiedere correzioni. Anche se il tasso di errore complessivo potrebbe essere inferiore alla metrica di destinazione, i tassi di errore per uno o più edifici o reti potrebbero essere superiori alla metrica di destinazione e necessitano di un'indagine.

#### <a name="setup-failure-investigations"></a>Indagini sugli errori di configurazione 

Questo report di riepilogo viene usato per individuare e isolare gli edifici o le reti che potrebbero richiedere una correzione.

> [!NOTE]
> Assicurarsi di modificare il filtro del report Month Year in base al mese corrente. Selezionare **Modifica** e modificare il filtro del report **Anno mese** per salvare il nuovo mese predefinito.

##### <a name="remediation"></a>Bonifica 

Focalizzare le prime azioni correttive su edifici o subnet con il maggior volume di guasti. In questo modo si ottimizza l'impatto sull'esperienza utente e si riduce rapidamente la frequenza di errori di configurazione delle chiamate dell'organizzazione. La tabella seguente elenca i due motivi degli errori di configurazione segnalati da Call Quality Dashboard.

| Motivo errori di configurazione delle chiamate       | Causa tipica                    |
|----------------------------------|----------------------------------|
| Assenza della regola di esenzione dell'ispezione profonda dei pacchetti FW | Indica che l'apparecchiatura di rete lungo il percorso ha impedito la definizione del percorso del supporto a causa delle regole di ispezione profonda dei pacchetti. È probabile che le regole del firewall non siano configurate correttamente. In questo scenario, l'handshake TCP ha avuto esito positivo, ma l'handshake SSL non è riuscito.      |
| Regola eccezione blocco IP FW mancante      | Indica che l'apparecchiatura di rete lungo il percorso ha impedito di stabilire il percorso del supporto alla rete Microsoft 365 o Office 365. Il motivo potrebbe essere che le regole del proxy o del firewall non sono configurate correttamente per consentire l'accesso agli indirizzi IP e alle porte usate per Teams e Skype for Business traffico. |

Quando si inizia la correzione, è possibile concentrare gli sforzi su uno specifico edificio o subnet. Come illustrato nella tabella precedente, questi problemi sono dovuti a configurazioni del firewall o proxy. Esaminare le opzioni nella tabella seguente per le azioni correttive.

|      Bonifica      |Linee guida  |
|-----------------------|----------|
| Configurare i firewall | Collaborare con il team di rete e verificare la configurazione dei firewall rispetto [all'elenco Office 365 indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).<br><br>Verifica che le [subnet e le porte multimediali](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) siano incluse nelle regole del firewall. <br><br>Verificare che le [porte necessarie](prepare-network.md) siano aperte nel firewall. UDP deve avere la priorità perché TCP è considerato un protocollo failback per la condivisione dello schermo basata su audio, video e video e il suo utilizzo influirà sulla qualità della chiamata. La condivisione di applicazioni RDP legacy usa solo TCP.|

### <a name="drop-failures"></a>Errori di rilascio

A differenza dei codici di errore di configurazione, Call Quality Dashboard non include codice di errore di rilascio per indicare il motivo per cui si verificano errori di rilascio, il che rende difficile isolare una causa radice specifica. Per valutare meglio gli errori di caduta, usare un approccio dedotto. La correzione di eventuali aree di interesse per i supporti multimediali, l'applicazione di patch a client e driver e la correzione dell'uso di dispositivi certificati per Teams e Skype for Business, è prevedibile un calo degli errori.

#### <a name="drop-failure-trend-analysis"></a>Analisi delle tendenze degli errori di caduta

Questo report mostra la quantità totale di flussi audio, gli errori di caduta totali e il tasso di errore di rilascio. Posizionare il puntatore su una delle colonne per visualizzarne i valori. 


##### <a name="analysis"></a>Analisi

Usando questo tipo di report, è possibile rispondere alle domande seguenti:

-   Qual è il tasso di errore di rilascio corrente?
-   Il tasso di errore di rilascio è inferiore alla metrica di destinazione definita?
-   La tendenza al fallimento è peggiore o migliore del mese precedente?
-   La tendenza al fallimento è in aumento, costante o decrescente?

Indipendentemente dalle risposte alle domande precedenti, prenditi il tempo per indagare usando i report secondari per cercare edifici o reti che potrebbero richiedere correzioni. Anche se il tasso di errore totale potrebbe essere inferiore alla metrica di destinazione, il tasso di errore di rilascio per uno o più edifici o reti potrebbe essere superiore alla metrica di destinazione e deve essere esaminato.

#### <a name="drop-failure-investigations"></a>Indagini sugli errori di rilascio

Gli errori riportati qui indicano che la chiamata è stata interrotta in modo imprevisto e ha generato un'esperienza utente negativa. A differenza dei report di tendenza, questi report forniscono ulteriori informazioni su subnet specifiche che richiedono ulteriori indagini.


##### <a name="remediation"></a>Bonifica

Usando i report della tabella inclusi, è possibile isolare le aree problematiche nella rete in cui la velocità di rilascio è superiore alla metrica di destinazione definita. Focalizzare le prime azioni correttive su edifici o subnet che hanno il numero totale di flussi più alto, per ottenere il maggiore impatto.

Cause comuni dell'calo delle chiamate:

-   Sotto-provisioning della rete o uscita Internet
-   Nessuna QoS configurata sulle reti vincolate
-   Versioni client precedenti
-   Comportamento dell'utente

Dopo aver scoperto le aree problematiche, è possibile usare [l'analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md) per esaminare ulteriormente gli utenti in quell'edificio per problemi specifici. L'analisi delle chiamate contiene ulteriori dati EUII e può essere utile per isolare ulteriormente i potenziali motivi degli errori di caduta.

Indipendentemente dal passaggio successivo, è buona norma informare il supporto tecnico che è stato rilevato un problema con edifici o subnet specifici. In questo modo l'helpdesk può rispondere rapidamente alle chiamate in arrivo e valutare gli utenti in modo più efficiente. Gli utenti contrassegnati possono quindi essere segnalati al team di progettazione per ulteriori indagini.

La tabella seguente elenca alcuni metodi comuni per gestire e correggere gli errori di rilascio.

| Bonifica                              | Linee guida                      |
|------------------------------------------|-------------------------------|
| **Rete/Internet**                         | **Congestione**: collaborare con il team di rete per monitorare la larghezza di banda in edifici/subnet specifici per verificare che si siano verificati problemi di sovrautilizzazione. Se si verifica la congestione della rete, è consigliabile aumentare la larghezza di banda per quell'edificio o applicare la QoS. Usare i [report di riepilogo Quality Poor Stream](#quality-investigations) inclusi per esaminare le subnet con problemi di instabilità, latenza e perdita di pacchetti, perché spesso precedono uno stream eliminato.<br><br>**QoS**: se l'aumento della larghezza di banda non è pratico o conveniente, è consigliabile implementare la QoS. Questo strumento è molto efficace nella gestione del traffico congestionato e può garantire che i pacchetti multimediali nella rete gestita siano prioritari al di sopra del traffico non multimediale. In alternativa, se non ci sono prove chiare che la larghezza di banda sia la causa, considerare queste soluzioni:<ul><li>[linee guida QoS di Microsoft Teams](qos-in-teams.md)</li></ul><br>**Eseguire una valutazione della conformità alla rete**: una valutazione della rete fornisce dettagli sull'utilizzo previsto della larghezza di banda, su come gestire le modifiche di larghezza di banda e rete e sulle procedure di rete consigliate per Teams e Skype for Business. Usando la tabella precedente come origine, si dispone di un elenco di edifici o subnet eccellenti candidati per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul> |
| **Client (solo Skype for Business online)** | Alcuni client Skype for Business precedenti hanno noti e documentato problemi relativi all'affidabilità dei supporti. Esaminare i report di Call Analytics di più utenti interessati oppure creare un report personalizzato della tabella Versione client in Call Quality Dashboard filtrato in base a edifici o subnet specifici con la misura Total Call Dropped Failure % . Queste informazioni ti aiuteranno a capire se esiste una relazione tra l'insezione di una chiamata in uno specifico edificio e una versione specifica del client.     |
| **Dispositivi**                                  |Se i dispositivi sono responsabili di problemi di qualità delle chiamate, valuta l'aggiornamento dei dispositivi offensivi. Per altre informazioni, vedere [Telefoni per Teams](./devices/phones-for-teams.md). |
| **Comportamento dell'utente**                            | Se non si stabilisce che il problema non sia la rete, i dispositivi o i client, è consigliabile sviluppare una strategia di adozione degli utenti per informare gli utenti su come partecipare e uscire al meglio dalle riunioni. Un utente Teams e Skype for Business più intelligente produrrà un'esperienza utente migliore per tutti i partecipanti alla riunione. Ad esempio, un utente che mette il portatile in modalità sospensione (chiudendo il coperchio) senza uscire dalla riunione verrà classificato come interruzione imprevista della chiamata.   |

## <a name="quality-investigations"></a>Indagini sulla qualità

Il passaggio successivo per valutare lo stato della qualità audio in tutta l'organizzazione consiste nell'analizzare la scarsa frequenza di trasmissione (PSR), TCP e l'utilizzo del proxy. È importante ricordare che call quality dashboard non fornisce una causa radice specifica, ma fornisce invece le aree di problema più probabili per avviare una conversazione collaborativa con i team appropriati per le attività di correzione. 

> [!NOTE]
> Non tutte le relazioni incluse nei modelli sono descritte in questo articolo; tuttavia, i metodi di indagine descritti di seguito continueranno ad applicarsi a tali segnalazioni. Per altre informazioni, fare riferimento alla descrizione del singolo report. 

### <a name="quality"></a>Qualità

Le percentuali psr vengono usate per indicare se l'organizzazione sta soddisfando gli obiettivi metrici definiti per una determinata area di interesse. È importante notare che, anche se le percentuali di alto livello si trovano all'interno del target definito, le singole subnet o gli edifici potrebbero non soddisfare i target definiti e, di conseguenza, avere bisogno di ulteriori indagini. Ad esempio, se la percentuale complessiva di PSR audio è del 2% ad aprile, che soddisfa il target di esempio, i singoli edifici e subnet potrebbero comunque avere esperienze scadenti, a seconda della distribuzione complessiva di tale 2%. 

Per valutare la percentuale di flussi scadenti, usare i report di qualità. Sono disponibili vari report di qualità per esaminare le metriche generali, per le conferenze, le chiamate PSTN a due parti, la VPN e le sale riunioni. I report mensili, settimanali e giornalieri vengono forniti per facilitare questo processo. I report settimanali e giornalieri sono limitati al modello Reti gestite per aumentarne l'efficacia e ridurre il rumore. 

#### <a name="quality-trend-analysis"></a>Analisi delle tendenze di qualità

I report di tendenza visualizzano informazioni sulla qualità nel tempo e vengono usati per identificare e comprendere le tendenze di qualità all'interno di ogni area di interesse. Come indicato in precedenza, nei modelli sono inclusi alberi di report per indagare sulla qualità; conferenze, chiamate PSTN a due parti, VPN e sale riunioni. Ai fini dell'analisi della qualità, il processo investigativo è lo stesso. Tuttavia, ti consigliamo di iniziare con le conferenze, perché qualsiasi miglioramento della qualità delle conferenze avrà un impatto positivo anche su tutte le altre aree. 

> [!Note]
> Indagare su due parti, le chiamate PSTN e le sale riunioni sono simili all'analisi delle conferenze. L'obiettivo è isolare gli edifici o le subnet con la qualità peggiore e identificare il motivo della scarsa qualità.

> [!Important]
> I report basati su VPN sono filtrati utilizzando la seconda dimensione VPN. Questa dimensione richiede che la scheda di rete VPN sia registrata correttamente come scheda di accesso remoto. I fornitori di VPN non usano questo contrassegno in modo affidabile e il chilometraggio varia a seconda del fornitore di VPN distribuito nell'organizzazione. Se necessario, modifica i report [VPN](CQD-upload-tenant-building-data.md#vpn) usando il nome dell'edificio o della rete.

##### <a name="investigation"></a>Indagine

Usando questi report, è possibile rispondere alle domande seguenti:

-   Qual è il psr totale per il mese corrente?
-   Il PSR è sotto la metrica di destinazione definita?
-   Il PSR è peggiore o migliore del mese precedente?
-   La tendenza psr è in aumento, costante o in diminuzione?

Indipendentemente dalle risposte alle domande precedenti, prenditi il tempo per indagare usando i sottoreport per cercare edifici o subnet che potrebbero richiedere un'indagine. Anche se il PSR complessivo potrebbe essere inferiore alla metrica di destinazione, spesso il PSR per uno o più edifici o reti è superiore alla metrica e richiede una correzione.

#### <a name="quality-investigations"></a>Indagini sulla qualità

I report di riepilogo della qualità forniscono informazioni più approfondite su ciò che ha contribuito a classificare i flussi come scadenti e aiutano a isolare le aree problematiche nella rete gestita.

Anche se le dimensioni utilizzate potrebbero variare leggermente tra il report, ogni rapporto includerà misure per i flussi totali, i flussi totali poveri, PSR e la scarsa qualità dovuta. Sono stati creati report per ogni area di interesse: conferenze, chiamate PSTN a due parti, VPN e sale riunioni. Il modello Rete gestita include report aggiuntivi per sfruttare le informazioni sulla posizione caricate tramite il file di compilazione.


> [!Note]
> Le subnet comuni sono difficili da valutare a causa del loro uso diffuso. Al modello Tutte le reti è stato aggiunto un report separato che mostra l'IP pubblico del client (Second Reflexive Local IP) per facilitare la correzione degli uffici che usano le reti comuni.


![Screenshot che mostra il riepilogo del flusso audio scadente.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Bonifica

Focalizzare gli sforzi di correzione su edifici o subnet che hanno il maggior volume di flussi, perché in questo modo si massimizza l'impatto e si contribuisce a migliorare rapidamente l'esperienza utente. Usare le misure di instabilità, perdita di pacchetti e tempo di andata e ritorno (RTT) per capire cosa sta contribuendo alla scarsa qualità (è possibile che ci siano più problemi):

-   **Instabilità**: i pacchetti multimediali arrivano a velocità diverse, il che causa l'audio robotico di un altoparlante.
-   **Perdita di pacchetti**: i pacchetti multimediali vengono eliminati, creando l'effetto di parole o sillabe mancanti.
-   **RTT**: I pacchetti multimediali impiegano molto tempo per raggiungere la destinazione, creando un effetto walkie-talkie.

Per facilitare l'analisi dei problemi di qualità, usare [l'analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md). Con Call Analytics, è possibile esaminare uno specifico report di conferenza o chiamata dell'utente. Questo report conterrà dati EUII/PII ed è utile quando si cerca la causa di un errore. Dopo aver capito quale edificio è interessato, dovrebbe essere semplice tenere traccia degli utenti in quell'edificio. 

Non dimenticare di comunicare all'helpdesk che queste reti presentano problemi di qualità, in modo che possano valutare e rispondere rapidamente alle chiamate in arrivo.

| Bonifica                              | Linee guida                         |
|------------------------------------------|----------------------------------|
| **Reti**                                 | **Congestione**: una rete sovrautilcaricata o sotto-provisioning può causare problemi di qualità multimediale. Collaborare con il team di rete per determinare se le connessioni di rete dall'utente al punto di uscita Internet hanno larghezza di banda sufficiente per supportare i supporti. <br><br>**Eseguire una valutazione della conformità alla rete**: una valutazione della rete fornisce dettagli sull'utilizzo previsto della larghezza di banda, su come gestire le modifiche di larghezza di banda e rete e sulle procedure di rete consigliate per Teams e Skype for Business. Usando la tabella precedente come origine, si dispone di un elenco di edifici o subnet eccellenti candidati per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul>|
| **QoS (Quality of Service)**  | QoS è uno strumento comprovato che consente di assegnare priorità ai pacchetti in una rete congestionata per assicurarsi che arrivino a destinazione intatti e puntuali. È consigliabile implementare la QoS nell'intera organizzazione per massimizzare la qualità dell'esperienza utente in cui la larghezza di banda è limitata. QoS consente di risolvere i problemi tipicamente associati a alti livelli di perdita di pacchetti e, in misura minore, a tempi di instabilità e round trip.<ul><li>[Teams linee guida QoS](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi possono avere un impatto significativo sulla qualità delle chiamate. Wi-Fi distribuzioni in genere non tengono in considerazione i requisiti di rete per i servizi VoIP e spesso sono una fonte di scarsa qualità. Per altre informazioni sull'ottimizzazione dell'infrastruttura di Wi-Fi, vedere [questo articolo sulla pianificazione Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver wireless**: verifica che i driver wireless siano aggiornati. In questo modo si ridurrà l'esperienza utente scadente relativa a un driver obsoleto. Molte organizzazioni non includono driver wireless nei cicli di patch e questi driver possono essere scollegati per anni. Molti problemi wireless vengono risolti verificando che i driver wireless siano aggiornati.<br><br>**WMM**: Wireless Multimedia Extensions (WMM), noto anche come Wi-Fi Multimedia, fornisce funzionalità QoS di base alle reti wireless. Le moderne reti wireless devono supportare molti dispositivi. Questi dispositivi competono per la larghezza di banda e possono portare a problemi di qualità per i servizi VoIP, dove la velocità e la latenza sono essenziali. Consulta il tuo fornitore di servizi wireless per informazioni specifiche e valuta l'implementazione di WMM nella rete wireless per assegnare la priorità a Skype for Business e Teams supporti.<br><br>**Densità dei** punti di accesso: i punti di accesso potrebbero essere troppo distanti o non essere presenti in una posizione ideale. Per ridurre al minimo le potenziali interferenze, inserire punti di accesso aggiuntivi nelle sale riunioni e in luoghi che non sono ostruite da pareti o altri oggetti in cui il segnale Wi-Fi è debole.<br><br>**Da 2,4 GHz a 5 GHz**: 5 GHz fornisce meno interferenze sullo sfondo e velocità maggiori e deve essere assegnata una priorità durante la distribuzione VoIP tramite Wi-Fi. Tuttavia, 5 GHz non è così forte come 2,4 GHz e non penetra facilmente pareti. Rivedere il layout dell'edificio per determinare la frequenza su cui è possibile fare affidamento per la connessione ottimale. |
|**Dispositivo di rete** | Le organizzazioni di grandi dimensioni potrebbero avere centinaia di dispositivi distribuiti in tutta la rete. Collaborare con il team di rete per assicurarsi che i dispositivi di rete dall'utente a Internet siano mantenuti e aggiornati. |
| **VPN**  | Gli accessori VPN non sono tradizionalmente progettati per gestire carichi di lavoro multimediali in tempo reale. Alcune configurazioni VPN vietano l'uso di UDP (che è il protocollo preferito per i supporti) e si basano solo su TCP. Valuta l'implementazione di una soluzione split tunnel VPN per ridurre la VPN come fonte di scarsa qualità. |
| **Client** <br>(solo Skype for Business online) | Verificare che tutti i client vengano aggiornati regolarmente. |
| **Dispositivi** | Se i dispositivi sono responsabili di problemi di qualità delle chiamate, valuta l'aggiornamento dei dispositivi offensivi. Per altre informazioni, vedere [Telefoni per Teams](./devices/phones-for-teams.md). |
| **Driver** | Le patch di rete (Ethernet e Wi-Fi), audio, video e driver USB devono far parte della strategia di gestione delle patch complessiva. Molti problemi di qualità vengono risolti aggiornando i driver. |
| **Sale riunioni con Wi-Fi** | È consigliabile collegare alla rete i dispositivi delle sale riunioni utilizzando almeno una connessione Ethernet da 1 Gbps. I dispositivi delle sale riunioni in genere includono più flussi audio e video, insieme al contenuto della riunione, ad esempio la condivisione dello schermo, e hanno requisiti di rete più elevati rispetto ad altri endpoint di Teams o Skype for Business. Le sale riunioni sono, per definizione, dispositivi fissi in cui Wi-Fi offre un vantaggio solo durante l'installazione.<br><br>Le sale riunioni devono essere trattate con maggiore cura e attenzione per garantire che l'esperienza con questi dispositivi sia in grado di soddisfare o superare le aspettative. I problemi di qualità con le sale riunioni in genere vengono riassegnati rapidamente, perché vengono spesso usati dal personale di livello superiore.<br><br>Con tutte le cose uguali (a parte la comodità), Wi-Fi prestazioni è spesso inferiore a una connessione cablata. Con l'aumento delle politiche di "portare il tuo dispositivo" e la proliferazione dei portatili, Wi-Fi punti di accesso sono spesso sovrautilizzate. I file multimediali in tempo reale potrebbero non essere classificati in ordine di priorità nelle reti Wi-Fi, il che può causare problemi di qualità durante i momenti di picco di utilizzo. Questo utilizzo intensivo può coincidere con una riunione in cui potrebbero essere presenti decine di persone, ognuna con il proprio portatile e smartphone, tutte connesse allo stesso punto di accesso Wi-Fi del dispositivo della sala riunioni.<br><br>Wi-Fi deve essere considerato solo come soluzione temporanea, per un'installazione mobile o quando è stato eseguito correttamente il provisioning di Wi-Fi per supportare supporti multimediali di livello aziendale e in tempo reale. |


### <a name="tcp"></a>TCP 

Tcp (Transmission Control Protocol) è considerato un trasporto failback e non il trasporto primario desiderato per i supporti in tempo reale. Il motivo per cui si tratta di un trasporto failback è dovuto alla natura di stato di TCP. Ad esempio, se una chiamata viene effettuata su una rete latente e i pacchetti multimediali vengono ritardati, i pacchetti di pochi secondi fa, che non sono più utili, competono per ottenere larghezza di banda per raggiungere il ricevitore, il che può peggiorare la situazione. Questo rende l'audio punto guaritore e l'audio stretch, con conseguente artefatti udibili, spesso sotto forma di jitter.

I report di questa sezione non fanno distinzione tra flussi buoni e flussi scadenti. Dato che UDP è preferibile, i report cercano l'uso di TCP per la condivisione dello schermo basata su audio, video e video (VBSS). Vengono fornite tassi di flusso scadenti per confrontare la qualità UDP rispetto alla qualità TCP in modo da concentrare gli sforzi sui punti in cui l'impatto è maggiore. L'utilizzo del protocollo TCP è causato principalmente da regole del firewall incomplete. Per altre informazioni sulle regole del firewall per Teams e Skype for Business Online, vedere [URL e intervalli di indirizzi IP Microsoft 365 e Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).

> [!Note]
> Audio, video e VBSS preferiscono tutti UDP come principale trasporto. Il carico di lavoro legacy di condivisione applicazioni RDP usa solo TCP.

#### <a name="tcp-usage"></a>Utilizzo TCP

I report TCP indicano l'utilizzo complessivo di TCP negli ultimi sette mesi. Tutti gli altri report di questa sezione si concentreranno su come restringere edifici e subnet specifici in cui tcp è usato più comunemente. Sono disponibili report separati sia per i flussi di conferenza che per quelli di due parti.

![Grafico che mostra la percentuale di flussi audio che usano TCP.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Indagine

Usando questo report, è possibile rispondere alle domande seguenti:

-   Qual è il volume totale dei flussi TCP per il mese corrente?
-   È peggio o meglio del mese precedente?
-   La tendenza all'utilizzo del TCP è in aumento, costante o decrescente?
-   IL PSR TCP è uguale al psr complessivo?

Se si nota che la tendenza di utilizzo TCP è in aumento o superiore al normale utilizzo mensile, prendere il tempo per indagare utilizzando i report secondari per cercare gli edifici o le reti che potrebbero richiedere una correzione. Idealmente, si desidera il minor numero possibile di sessioni audio basate su TCP nella rete gestita.

#### <a name="tcp-vs-udp"></a>TCP e UDP

Questo report identifica il volume dei report sull'utilizzo TCP e UDP nell'ultimo mese per la condivisione dello schermo basata su audio, video e video (VBSS). 

![Report che mostra il volume dei flussi che usano TCP e UDP.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analisi

Anche se si vuole che l'utilizzo di TCP sia il più basso possibile, è possibile che venga visualizzato un po' di utilizzo TCP in una distribuzione altrimenti sana. Tcp di per sé non contribuirà a una chiamata scadente, quindi vengono fornite le tariffe dei flussi per aiutare a identificare se l'utilizzo TCP è un collaboratore di scarsa qualità. 

#### <a name="tcp-investigations"></a>Indagini TCP

Nei modelli CQD forniti passare al Flussi TCP tramite i report Building e Subnet usando il modello Reti gestite o Tutte le reti. Allo scopo di analizzare l'utilizzo del protocollo TCP, il processo è lo stesso, quindi concentreremo la discussione qui sulle conferenze.


##### <a name="remediation"></a>Bonifica

Questo report identifica edifici e subnet specifici che contribuiscono al volume di utilizzo TCP. È inoltre incluso un report aggiuntivo per identificare l'IP di Inoltro Microsoft usato nella chiamata per isolare le regole del firewall mancanti. Focalizzare le azioni correttive sugli edifici che hanno il volume più elevato di flussi TCP per massimizzare l'impatto.

La causa più comune dell'utilizzo di TCP è l'assenza di regole di eccezione nei firewall o nei proxy. Nella prossima sezione parleremo dei proxy, quindi per ora concentrati sui firewall. Usando l'edificio o la subnet fornita, è possibile determinare quale firewall deve essere aggiornato.

| Bonifica        | Linee guida     |
|--------------------|--------------------------------------|
| Configurare il firewall | Verificare che [le porte e gli indirizzi IP Microsoft 365 o Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) siano esclusi dal firewall. Per i problemi TCP correlati ai supporti, focalizzare l'impegno iniziale su quanto segue:<ul><li>Verificare che le subnet dei supporti client 13.107.64.0/18 e 52.112.0.0/14 siano presenti nelle regole del firewall.</li><li>Le porte UDP 3478-3481 sono le porte multimediali necessarie e devono essere aperte, altrimenti il client non riuscirà a tornare alla porta TCP 443.</li></ul> |
| Verificare             | Usare lo [strumento di valutazione della rete Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) per verificare la presenza di problemi di connettività a specifiche Microsoft 365 o porte IP Office 365 dall'edificio o dalla subnet interessata.    |

### <a name="http-proxy"></a>Proxy HTTP

Proxy HTTP non sono il percorso preferito per stabilire sessioni media, per una moltitudine di motivi. Molti includono funzionalità di ispezione profonda dei pacchetti che possono impedire il completamento delle connessioni al servizio e causare interruzioni. Inoltre, quasi tutti i proxy forzano TCP anziché consentire UDP, che è consigliabile per una qualità audio ottimale.

È sempre consigliabile configurare il client per la connessione diretta ai servizi di Teams e Skype for Business. Ciò è particolarmente importante per il traffico multimediale.


> [!IMPORTANT]
> È consigliabile caricare un [file di edificio valido](CQD-upload-tenant-building-data.md) per distinguere i flussi audio dall'esterno durante l'analisi dell'utilizzo del proxy. 


#### <a name="http-proxy-usage"></a>Utilizzo proxy HTTP

Il report flusso proxy HTTP in questa sezione del modello è molto simile ai report TCP. Non controlla se le chiamate sono scadenti o buone, ma se la chiamata è connessa tramite HTTP.

![Screenshot del report dei flussi audio che usano HTTP.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analisi

Si desidera visualizzare il minor numero possibile di flussi multimediali HTTP. Se sono presenti flussi che attraversano il proxy, consultare il team di rete per assicurarsi che siano presenti le esclusioni appropriate, in modo che i client vengano instradati direttamente a Teams o Skype for Business subnet multimediali online.

Se nell'organizzazione è presente un solo proxy Internet, verificare [l'Microsoft 365 appropriato o Office 365 GLI URL e le esclusioni dell'intervallo di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Se nell'organizzazione sono configurati più proxy Internet, usare il sottoreport HTTP per individuare l'edificio o la subnet interessata.

Per le organizzazioni che non possono ignorare il proxy, assicurarsi che il client Skype for Business sia configurato per eseguire correttamente l'accesso quando si trova dietro un proxy, come descritto nell'articolo [Skype for Business deve usare il server proxy per accedere invece di provare la connessione diretta](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Indagini sul proxy HTTP

Questo report identifica edifici e subnet specifici che contribuiscono all'utilizzo di HTTP.


##### <a name="remediation"></a>Bonifica

[È consigliabile](proxy-servers-for-skype-for-business-online.md) ignorare sempre i proxy per Skype for Business e Teams, in particolare il traffico multimediale. I proxy non rendono Skype for Business più sicuro, perché il suo traffico è già crittografato. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi produranno un'esperienza negativa con la condivisione di audio, video e schermo, in cui i flussi in tempo reale sono essenziali.

La causa più comune dell'utilizzo di HTTP sono le regole di eccezione mancanti nei proxy. Usando l'edificio o la subnet fornita, è possibile determinare rapidamente quale proxy deve essere configurato per il bypass multimediale.

Verificare che gli [FQDN Microsoft 365 o Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) necessari vengano aggiunti a un elenco di indirizzi consentiti nel proxy.

## <a name="endpoint-investigations"></a>Indagini degli endpoint

Questa sezione è incentrata sulle attività per la creazione di report sulle versioni client e sull'uso di dispositivi certificati. Sono disponibili report per delineare l'utilizzo per le versioni client, il tipo di client, i dispositivi e i driver di acquisizione (microfono), i dispositivi di acquisizione video e Wi-Fi versioni di fornitori e driver.

> [!NOTE]
> Non tutte le relazioni incluse nei modelli sono descritte in questo articolo; tuttavia, si applicano ancora i metodi di indagine descritti di seguito. Per altre informazioni, fare riferimento alla descrizione del singolo report.

### <a name="client-versions"></a>Versioni client

Questi report sono incentrati sull'identificazione di Skype for Business versioni client in uso e sul relativo volume nell'ambiente.

> [!IMPORTANT]
> Attualmente, Teams client vengono distribuiti e aggiornati automaticamente tramite la rete per la distribuzione di contenuti di Azure e verranno mantenuti aggiornati dal servizio. Di conseguenza, non è necessario monitorare Teams versioni client ( a meno che non si disattivi l'aggiornamento automatico, cosa che non è consigliabile).

A meno che non si escludono i dati dei partecipanti federati, questi report includeranno la telemetria client dagli endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per Second Tenant ID impostato per [l'ID tenant](CQD-data-and-reports.md#how-to-find-your-tenant-id) dell'organizzazione. In alternativa, è possibile usare un [filtro URL](CQD-data-and-reports.md#url-filters) per escludere la telemetria dei partecipanti federati.



#### <a name="remediation"></a>Bonifica

Una parte fondamentale del supporto di esperienze utente di alta qualità è garantire che i client gestiti eseguano versioni aggiornate di Skype for Business, oltre a garantire che i driver audio, video, di rete e USB di supporto siano aggiornati. Questo offre diversi vantaggi, tra cui: 

-   È più facile gestire alcune versioni rispetto a molte versioni.
-   Fornisce un livello di coerenza di esperienza.
-   Semplifica la risoluzione dei problemi relativi alla qualità e all'usabilità delle chiamate.
-   Microsoft apporta continuamente miglioramenti e ottimizzazioni generali in tutto il prodotto. Assicurarsi che gli utenti ricevano questi aggiornamenti riduce il rischio di riscontrare un problema già risolto.

Limitare la distribuzione a versioni client meno di sei mesi fa migliorerà l'esperienza utente complessiva e migliorerà la gestibilità riducendo il numero di versioni che devono essere supportate.

Se si usa solo Office A portata di clic, si passerà automaticamente alla finestra di sei mesi. Non sono necessarie altre azioni.

Se si dispone di una combinazione di pacchetti A portata di clic e di programma di installazione (MSI), è possibile usare il report per verificare che i client MSI vengano aggiornati regolarmente. Se noti che i clienti sono in ritardo, collabora con il team responsabile della gestione degli aggiornamenti di Office e assicurati che approvino e distribuiranno regolarmente le patch del client.

È anche importante considerare e assicurarsi che vengano installati patch anche per i driver di rete, video, USB e audio. Può essere facile ignorare questi driver e non includerli nella strategia di gestione delle patch.

I numeri di versione per Skype for Business sono disponibili tramite i collegamenti seguenti:

-   [Informazioni sulla versione per gli aggiornamenti di Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Cronologia degli aggiornamenti per Microsoft 365 Apps for enterprise](/officeupdates/update-history-office365-proplus-by-date)
-   [Download e aggiornamenti per Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivi

Per utilizzare il report del dispositivo microfono, è necessario comprendere il concetto del punteggio di opinione media (MOS). MOS è la misurazione gold standard per valutare la qualità audio percepita. È rappresentato come una valutazione intera da 0 a 5.

La base di tutte le misure di qualità della voce è come una persona percepisce la qualità del discorso. Perché è influenzata dalla percezione umana, è intrinsecamente soggettiva. Esistono diverse metodologie per i test soggettivi. La maggior parte delle misure di qualità vocale si basa su una scala ACR (Absolute Categorization Rating).

In un test soggettivo ACR, un numero statisticamente significativo di persone valuta la loro qualità dell'esperienza su una scala da 1 (cattiva) a 5 (eccellente). La media dei punteggi è il MOS. Il MOS risultante dipende dalla gamma di esperienze esposte al gruppo e dal tipo di esperienza valutata.

Poiché non è pratico condurre test soggettivi di qualità vocale per un sistema di comunicazione dal vivo, Microsoft Teams e Skype for Business generare valori MOS utilizzando algoritmi avanzati per prevedere oggettivamente i risultati di un test soggettivo.

Il set di MOS disponibile e le metriche associate forniscono una visione della qualità dell'esperienza fornita agli utenti da un dispositivo audio. 

Fornendo agli utenti dispositivi certificati per Teams e Skype for Business, si riducono le probabilità di riscontrare esperienze negative a causa del dispositivo stesso (che è più probabile, ad esempio, con altoparlanti e microfoni incorporati per laptop). Per altre informazioni, vedere questi articoli sul [programma di certificazione](/SkypeForBusiness/certification/overview) e sul [catalogo di soluzioni partner](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

I report sui dispositivi vengono utilizzati per valutare l'utilizzo del dispositivo in base al volume e al punteggio MOS (solo audio) e sono disponibili nei modelli associati in Client & Dispositivi. 

> [!IMPORTANT]
> A meno che non si escludono i dati dei partecipanti federati, questi report includeranno la telemetria client dagli endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per **Second Tenant ID** impostato per l'ID [tenant](CQD-data-and-reports.md#how-to-find-your-tenant-id) dell'organizzazione. ALternatively, è possibile usare un [filtro URL](CQD-data-and-reports.md#url-filters) per escludere la telemetria dei partecipanti federati.


> [!Note]
> Durante la visualizzazione di questo report potresti notare che più volte viene segnalato lo stesso dispositivo. Ciò è dovuto al modo in cui il dispositivo viene segnalato a Call Quality Dashboard. Le differenze nelle impostazioni locali hardware e del sistema operativo causano differenze nella segnalazione dei dati del dispositivo.

##### <a name="remediation"></a>Bonifica

In genere, dovrai individuare e eliminare gradualmente i dispositivi non certificati e sostituirli con dispositivi certificati. Quando si esaminano i report sui dispositivi, è necessario considerare quanto segue:

-   I dispositivi in uso sono certificati per Teams e Skype for Business? 
-   È possibile identificare gli utenti di un dispositivo specifico usando [l'analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md). Verifica che siano installati i driver di dispositivo più recenti e che il dispositivo non sia connesso tramite un hub USB o un alloggiamento di espansione. 
-   Quante versioni diverse di vari driver sono in uso? Vengono patchati regolarmente? Verificare che i driver audio, video e Wi-Fi vengano aggiornati regolarmente contribuirà a eliminarli come origine di problemi di qualità e a rendere l'esperienza utente più prevedibile e coerente.

##### <a name="audio"></a>Audio

Il prossimo compito consiste nel determinare l'utilizzo complessivo dei [dispositivi audio certificati](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). È consigliabile che almeno l'80% di tutti i flussi audio utilizzi un dispositivo audio certificato. Per ottenere questo risultato, è consigliabile esportare il report sui dispositivi microfono in Excel per calcolare l'uso di dispositivi certificati o approvati. Le organizzazioni in genere conservano un elenco di tutti i dispositivi approvati, quindi filtrare e ordinare i dati dovrebbe essere semplice.

##### <a name="video"></a>Video

Anche i driver video sono importanti per essere aggiornati. Verificare che le schede video vengano regolarmente patchate contribuirà a escludere i driver video come origine di scarsa qualità per i flussi video. L'uso di [dispositivi video certificati](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) garantisce un'esperienza utente fluida e di alta qualità. I dispositivi video che supportano la codifica nativa H.264 sono i preferiti, per ridurre l'utilizzo della CPU durante le videoconferenze.

##### <a name="wi-fi"></a>Wi-Fi

anche i driver di Wi-Fi devono essere patchati su una cadenza regolare e devono essere inclusi nella strategia di gestione delle patch. Molti problemi di qualità possono essere corretti mantenendo aggiornati Wi-Fi driver. Per altre informazioni sull'ottimizzazione dell'infrastruttura di Wi-Fi, vedere [questo articolo sulla pianificazione Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Argomenti correlati

[Usare Assistente per Teams](use-advisor-teams-roll-out.md)

[Preparare la rete per Teams](prepare-network.md)

[principi di connettività di rete di Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Analisi e creazione dei report di Teams](teams-analytics-and-reports/teams-reporting-reference.md).

[Gestire i dispositivi in Teams](./devices/device-management.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)
