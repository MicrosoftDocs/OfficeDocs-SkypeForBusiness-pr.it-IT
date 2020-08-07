---
title: Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Informazioni su come analizzare e gestire le prestazioni multimediali in tempo reale in Microsoft teams usando il dashboard qualità chiamata (Call Quality Dashboard).
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
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni in Microsoft Teams 

Questo articolo aiuta l'amministratore di teams o il supporto tecnico e l'helpdesk-a sviluppare un processo per il monitoraggio e la manutenzione della qualità delle chiamate e delle riunioni per l'organizzazione usando Microsoft teams Call Quality Dashboard (Call Quality Dashboard). Le nostre linee guida enfatizzano gli scenari di qualità audio, perché i miglioramenti apportati alla rete per migliorare l'esperienza audio si tradurranno in miglioramenti in video e condivisione.

Chiave per queste linee guida sono i due [modelli di Call Quality dashboard curati](https://aka.ms/QERtemplates) : ti consigliamo di scaricarli prima di procedere con le indicazioni in questo articolo.

Questo articolo presuppone che tu abbia già [configurato Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Categorie da monitorare e gestire

Dopo aver implementato le riunioni e la voce in teams, è necessario un piano per il monitoraggio e la manutenzione in corso. In questo modo si garantirà che i team siano sempre in esecuzione in maniera ottimale. Questo piano deve includere le aree principali elencate di seguito. È inoltre necessario stabilire le destinazioni per le metriche di qualità e un piano per la risoluzione dei problemi e per l'isolamento quando si verificano.

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
<p>Suddividere le metriche tramite chiamate interne (all'interno dell'organizzazione, ad esempio VPN, WiFi, Wired) o chiamate esterne</p>
<p>Suddividere le metriche in base all'edificio o alla rete</p>
<p>Chiamate VPN</p>
<p>Chiamate tramite TCP, UDP o proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Affidabilità delle chiamate</strong></td>
<td><p>Identificare e correggere eventuali problemi di rete o firewall</p>
<p>Acquisire informazioni sulle percentuali degli errori di configurazione e rilascio delle chiamate</p>
<p>Informazioni in cui si verifica la maggior parte degli errori di configurazione e rilascio delle chiamate</p>
</td>
</tr>
<tr class="odd">
<td><strong>Sondaggio degli utenti</strong></td>
<td>
<p>Usare valuta i dati delle chiamate per informazioni sull'esperienza effettiva degli utenti</p>
<p>Dove si verificano le cattive esperienze?</p>
<p>Correlare la scarsa esperienza con qualità delle chiamate, affidabilità e dispositivi</p>
</td>
</tr>
<tr class="even">
<td><strong>Dispositivi</strong></td>
<td><p>Informazioni sui microfoni e gli altoparlanti usati più comunemente e sul loro impatto sulla qualità delle chiamate</p>
<p>I driver audio, video, USB e WiFi di supporto sono regolarmente corretti?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Client</strong></td>
<td>
<p>Informazioni sui tipi di client e sulle versioni in uso e sul loro impatto sulla qualità e l'affidabilità delle chiamate  </p>
</ol></td>
</tr>
</tbody>
</table>

Valutando e rimediando continuamente le aree descritte in questo articolo, è possibile ridurne le potenzialità per influire negativamente sugli utenti. La maggior parte dei problemi degli utenti può essere raggruppata nelle categorie seguenti:

-   Firewall o configurazione proxy incompleta
-   Scarsa copertura Wi-Fi
-   Larghezza di banda insufficiente
-   VPN
-   Versioni e driver client non coerenti o obsoleti
-   Dispositivi audio non ottimizzati o incorporati
-   Subnet problematiche o dispositivi di rete

Attraverso una pianificazione e una progettazione adeguate prima di distribuire Team o Skype for business online, è possibile ridurre la quantità di risorse necessarie per mantenere le esperienze di alta qualità.

Questo articolo è incentrato sull'uso di Call Quality Dashboard (Call Quality Dashboard) online come strumento principale per segnalare e analizzare ogni area, con un'enfasi particolare sull'audio per massimizzare l'adozione e l'impatto. Gli eventuali miglioramenti apportati alla rete per migliorare l'esperienza audio verranno tradotti direttamente anche nei miglioramenti della condivisione di video e desktop.

Per accelerare la valutazione, vengono forniti [due modelli di Call Quality dashboard curati](https://aka.ms/qertemplates) : uno è per la gestione di tutte le reti e l'altro è filtrato solo per le reti gestite (interne). Anche se i report tutti i modelli di reti sono configurati per visualizzare informazioni su edifici e reti, è comunque possibile usarli mentre si lavora per raccogliere e caricare informazioni sulla creazione. Il caricamento di informazioni sulla creazione in Call Quality dashboard consente al servizio di migliorare la creazione di report aggiungendo informazioni personalizzate per la creazione, la rete e la posizione mentre si differenziano internamente dalle subnet esterne. Per altre informazioni, vedere [mapping delle costruzioni](CQD-building-mapping.md).

### <a name="intended-audience"></a>Destinatari previsti

Questo articolo è destinato a essere usato dalle parti interessate partner e clienti con ruoli come lead di collaborazione/architetto, consulente, specialista per la gestione/adozione dei cambiamenti, il supporto tecnico lead/help desk, Network lead, desktop lead e IT admin.

Questo articolo è destinato anche a essere usato dal campione o dai campioni di qualità designati. Per altre informazioni, Vedi [il ruolo campione di qualità](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Che cos'è la qualità?

In questo contesto, la qualità è una combinazione di metriche dei servizi e esperienza utente.


### <a name="service-metrics"></a>Metriche del servizio

Le metriche dei servizi sono costituite da specifiche metriche basate sul client. Durante ogni chiamata, il client raccoglie la telemetria per la chiamata e invia un report alla fine di ogni chiamata a cui è possibile accedere in seguito in Call Quality dashboard o in [analisi delle chiamate per utente](set-up-call-analytics.md). Queste metriche includono (ma non sono limitate a):

-   Flusso di scarsità (in entrata e in uscita)
-   Tasso di errore di configurazione
-   Calo tasso di errore


#### <a name="poor-stream-rate"></a>Tasso di flusso scadente

La bassa velocità di flusso (PSR) rappresenta la percentuale complessiva dell'organizzazione di flussi con qualità scadente. Questa metrica è destinata ad evidenziare le aree in cui l'organizzazione può concentrare lo sforzo per avere l'impatto più forte sulla riduzione di questo valore e sul miglioramento dell'esperienza utente, motivo per cui le [reti gestite](#managed-versus-unmanaged-networks) costituiscono lo stato di primaria importanza quando si esaminano i PSR. Anche gli utenti esterni sono importanti, ma le indagini variano in base a un'organizzazione. Valutare la possibilità di fornire le procedure consigliate per gli utenti esterni ed esaminare le chiamate esterne indipendentemente dall'organizzazione complessiva.

La misura effettiva in Call Quality dashboard varia in base al carico di lavoro, ma ai fini di questo articolo ci concentriamo principalmente sulla misurazione della _percentuale di scarsità audio_ . PSR è costituito dalle cinque medie metriche della rete descritte nella tabella seguente. Affinché un flusso venga classificato come scadente, solo una metrica deve superare la soglia definita. Call Quality dashboard fornisce il "povero a causa di..." misure per comprendere meglio quale condizione ha causato la classificazione del flusso come scadente. Per altre informazioni, leggere la [classificazione in Stream in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> Call Quality dashboard fornisce il "povero a causa di..." misure per comprendere meglio quale condizione ha causato la classificazione del flusso come scadente.


##### <a name="audio-poor-quality-metrics"></a>Metriche audio di qualità scadente

| Media metrica     | Descrizione     | Esperienza utente |
|-------------|-----------------|-----------------|
| Jitter \> 30 ms        | Questa è la variazione media di ritardo tra i pacchetti successivi. I team e Skype for business possono adattarsi ad alcuni livelli di jitter attraverso il buffering. Solo quando il jitter supera il buffering che un partecipante Nota gli effetti di jitter.      | I pacchetti che arrivano a velocità diverse causano la voce di un altoparlante a un suono robotico.   |
| Tasso di perdita di pacchetti \> 10% o 0,1        | Questa operazione viene spesso definita come percentuale di pacchetti persi. La perdita di pacchetti influenza direttamente la qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto sulle perdite di burst di back-to-back che causano il ritaglio completo dell'audio.     | I pacchetti che vengono eliminati e che non arrivano alla destinazione desiderata causano lacune nel supporto, con sillabe perse e parole e video e condivisione dispersivi. |
| Ora di andata e ritorno \> 500 ms        | Questo è il tempo necessario per ottenere un pacchetto IP dal punto a al punto B e viceversa al punto a. Questo ritardo di propagazione della rete è legato alla distanza fisica tra i due punti e alla velocità della luce e include un sovraccarico aggiuntivo adottato dai vari dispositivi nel percorso di rete.      | I pacchetti che impiegano troppo tempo per arrivare a destinazione causano un effetto walkie-talkie.   |
| NMOS degradazione media \> 1,0         | Media del Punteggio medio di [valutazione (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) per il flusso. Rappresenta la quantità di perdite di rete e jitter che ha influenzato la qualità dell'audio ricevuto che ha causato l'eliminazione di NMOS da più di un punto. | Si tratta di una combinazione di jitter, perdita di pacchetti e, in misura minore, maggiore tempo di andata e ritorno. L'utente potrebbe provare una combinazione di questi sintomi.   |
| Rapporto medio tra campioni nascosti \> 7% o 0,07 | Rapporto medio del numero di fotogrammi audio con campioni nascosti generati dalla perdita di pacchetti per la guarigione del numero totale di fotogrammi audio. Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati.      | I valori alti indicano che i livelli significativi di occultamento delle perdite sono stati applicati e hanno provocato l'audio distorto o perso.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Perché preferiamo usare i flussi anziché le chiamate?

I flussi consentono di sapere quale gamba particolare della chiamata è stata scadente-in uscita o in arrivo. Quando si guarda l'analisi delle chiamate per una chiamata scadente, determinare se la chiamata scadente è dovuta al flusso del chiamante (in uscita) o al flusso del chiamato (in ingresso). La determinazione del flusso che influenza la qualità delle chiamate è ancora più importante per le conferenze. Se si esaminano solo i dati delle chiamate, viene visualizzato il numero di conferenze a cui partecipa una persona, ma non è possibile vedere quali persone sono relatori attive, facendo la maggior parte della condivisione dello schermo.

I dati delle chiamate forniscono le metriche di utilizzo, ma non necessariamente condurrà alla causa radice per una qualità di chiamata scadente. Esaminando la direzione del flusso, puoi identificare fattori come una chiamata non presente in una rete gestita, una chiamata da un altro utente (ad esempio, un fornitore o un utente in una rete diversa). In questi casi, se la connessione di rete dell'altra persona è scadente, l'intera chiamata verrà contrassegnata come povera. Non è possibile eseguire operazioni su fattori esterni, quindi questi dati non sono utili.

La direzione del flusso può anche aiutare a identificare dispositivi o client problematici.

 - Ad esempio, se si ha un budget limitato per i dispositivi e si vogliono specificare solo i dispositivi per gli utenti di audio pesanti, usare il report sull'utilizzo audio (VoIP) e il filtro per i flussi in uscita e i servizi di conferenza. Cercare gli utenti di audio ad alto volume che parlano in microfoni incorporati, che potrebbero essere correlati alla qualità delle chiamate più scarsa (e si potrebbe voler inserire dispositivi audio per queste persone). Per maggiore chiarezza, potresti filtrare per l'utilizzo dei pacchetti, che ti permetterà di indirizzare in particolare gli utenti di audio ad alto volume. 

  - Un altro esempio riguarda la condivisione dello schermo. Se un cliente usa un client di Team obsoleti, le prestazioni di condivisione dello schermo potrebbero essere interessate. È possibile risolvere il problema privilegiando gli aggiornamenti del client per gli utenti che eseguono molto la condivisione dello schermo.

 - Identificando la direzione di un flusso che causa una qualità di chiamata scadente, puoi determinare se hai un problema relativo al QoS o alla larghezza di banda. Se il QoS non è stato completamente implementato o se si contrassegnano solo i pacchetti nel client e non nel flusso in ingresso, è possibile che venga visualizzato un livello di qualità delle chiamate più scadente. Esaminando la direzione del flusso, è possibile ottenere una visualizzazione più granulare di perdita di pacchetti, latenza o jitter in una direzione specifica. 

   - Supponiamo, ad esempio, che un utente si lamenti dell'audio robot durante una connessione cablata (jitter). Esaminando il flusso e la direzione, puoi determinare che il problema si verifica nel flusso in ingresso, solo per un set specifico di subnet. Dopo aver fornito queste informazioni al team di rete, è possibile rintracciarlo in un acceleratore WAN configurato in maniera non configurata che non bypassa il traffico multimediale. Dopo che il team di rete ha riconfigurato l'acceleratore WAN, il jitter scompare e la qualità delle chiamate migliora. 


#### <a name="setup-failure-rate"></a>Tasso di errore di configurazione

La frequenza di errore di configurazione, altrimenti nota come misura della _percentuale di errore di configurazione della chiamata totale_ in Call Quality dashboard, è il numero di flussi in cui non è stato possibile stabilire il percorso del supporto tra gli endpoint all'inizio della chiamata.

Rappresenta qualsiasi flusso multimediale che non è stato possibile stabilire. Considerata la gravità dell'impatto di questo problema sull'esperienza utente, l'obiettivo è quello di ridurre il valore al più vicino possibile allo zero. Un valore elevato per questa metrica è più comune nelle nuove distribuzioni con regole del firewall incomplete rispetto a una distribuzione matura, ma è comunque importante controllarle regolarmente.

Questa metrica viene calcolata prendendo il numero totale di flussi che non sono stati configurati in base al numero totale di flussi che hanno inviato un record di dettaglio delle chiamate (CDR) riuscito:

-   **Tasso di errore di configurazione** = Total call setup non riuscito numero di flusso/totale CDR disponibile Conteggio flusso

#### <a name="drop-failure-rate"></a>Calo tasso di errore

La percentuale di errore di rientro, altrimenti nota come misura della _percentuale di errore di chiamata totale rilasciata_ in Call Quality dashboard, è quella dei flussi definiti correttamente in cui il percorso del supporto non è stato interrotto normalmente.

Rappresenta qualsiasi flusso multimediale terminato in modo imprevisto. Anche se l'impatto di questa operazione non è così grave come un flusso che non è stato configurato, l'esperienza utente è ancora negativa. Le cadute di media improvvise e frequenti non solo possono avere un impatto grave sull'esperienza utente, ma determinano la necessità di riconnettersi agli utenti, con conseguente perdita di produttività (per non parlare della frustrazione).

La metrica viene calcolata prendendo il numero totale di flussi eliminati diviso per il conteggio totale dei flussi configurati correttamente:

-   **Drop failure rate** = Total Call Dropped count flusso/Total call setup numero di flusso riuscito

### <a name="define-your-target-metrics"></a>Definire le metriche di destinazione

In questa sezione vengono illustrate alcune delle metriche di servizio principali che vengono usate per valutare l'integrità dei servizi. Valutando e guidando continuamente gli sforzi per mantenere queste metriche al di sotto dei loro obiettivi definiti, ti aiuterai ad assicurarti che gli utenti verifichino una qualità di chiamata affidabile e coerente. Come punto di partenza, usare le Destinazioni suggerite nella tabella seguente. Modificare le destinazioni in base alle esigenze per soddisfare gli obiettivi aziendali.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Tipo di rete</th><th rowspan="1">Obiettivi di qualità</th><th colspan="2">Obiettivi di affidabilità</th></tr>
<tr><th>Tasso di flusso audio scadente</th><th>Tasso di errore di configurazione</th><th>Calo tasso di errore</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Generale</td><td>3,0%</td><td>1,0%</td><td>3,0%</td></tr>
<tr><td rowspan="5"><strong>Conferenze</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Interno cablato</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 5 GHz interno</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Generale</td><td>2,0%</td><td>0,5%</td><td>3,0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interno</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Cablato/Wi-Fi 5 GHz interno</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Cablato/Wi-Fi 5 GHz globale</td><td>2,0%</td><td>1,0%</td><td>1,0%</td></tr>
<tr><td>Generale</td><td>2,0%</td><td>1,0%</td><td>3,0%</td></tr>
</table>

### <a name="user-experience"></a>Esperienza utente

L'analisi dell'esperienza utente è più l'arte che la scienza, perché le metriche riunite qui non sempre significano che c'è un problema con la rete o il servizio, ma piuttosto, indicano semplicemente che l'utente percepisce un problema. Call Quality dashboard include un meccanismo di rilevamento incorporato, Rate My Call (RMC), che consente di valutare l'esperienza complessiva degli utenti. RMC fornirà informazioni sulle seguenti questioni dal punto di vista degli utenti:

-   Si sa come usare la soluzione?
-   La soluzione è facile da usare e intuitiva e supporta le esigenze di comunicazione quotidiane?
-   La soluzione aiuta a ottenere il lavoro?
-   Qual è la percezione complessiva della soluzione?
-   È possibile usare la soluzione in qualsiasi momento, indipendentemente dalla posizione in cui si trova?
-   È possibile configurare e gestire una chiamata?

#### <a name="rate-my-call"></a>Votare la chiamata 

Vota la mia chiamata (RMC) è integrata in teams e Skype for business. Si apre automaticamente dopo uno ogni 10 chiamate o il 10%. Questo breve sondaggio chiede all'utente di valutare la chiamata e di specificare un piccolo contesto per il motivo per cui la qualità delle chiamate potrebbe essere stata scadente. Una valutazione di uno o due è considerata scadente, da tre a quattro è buona e cinque è eccellente. Anche se è un po' un indicatore di ritardo, questa è una metrica utile per scoprire i problemi che le metriche dei servizi possono perdere.

> [!Note]
> Il fattore umano: spesso gli utenti ignorano il sondaggio quando la qualità delle chiamate è buona e la compilano quando la qualità della chiamata è negativa. Di conseguenza, i report RMC potrebbero essere sbilanciati verso il lato scadente anche quando le metriche dei servizi sono valide.

Puoi usare Call Quality dashboard per segnalare le risposte degli utenti RMC e i report di esempio sono inclusi nel modello Call Quality dashboard. Tuttavia, non vengono discussi in dettaglio in questo articolo. 

#### <a name="client-and-device-readiness"></a>Disponibilità di client e dispositivi

Per garantire agli utenti un'esperienza utente coerente e positiva, è necessaria una strategia di client e dispositivi solidi. Alcuni principi chiave guidano ogni strategia di preparazione.

##### <a name="client-readiness"></a>Disponibilità del client

Mantenere aggiornato il client teams garantisce che gli utenti abbiano sempre la migliore esperienza possibile. Microsoft rilascia [aggiornamenti frequenti per il client teams](teams-client-update.md) (l'aggiornamento si installa in background a meno che non si sia disattivata questa funzionalità, che non è consigliabile). È anche importante ricordarsi di patch di rete, video, USB e driver audio, perché spesso sono trascurati e possono influenzare la qualità delle chiamate e delle riunioni. Valutare l'aggiunta di driver di rete, Wi-Fi, video, USB e audio al processo di gestione delle patch corrente.


##### <a name="device-readiness"></a>Conformità del dispositivo

Nessuna strategia singola può influire sull'esperienza utente in più rispetto alla strategia di preparazione del dispositivo. Ad esempio, gli utenti che si affidano agli altoparlanti e al microfono del portatile sperimenteranno molto rumore di fondo nelle chiamate e nelle riunioni. Teams è progettato per funzionare con quasi tutti i dispositivi, ma se si verificano problemi relativi al dispositivo, vedere il [telefono per i team](phones-for-teams.md).


### <a name="categories-of-quality"></a>Categorie di qualità

Operazionalizzare è un set di procedure di gestione della qualità che offre le migliori possibilità di una buona qualità delle chiamate e delle riunioni. Un buon piano di gestione della qualità risolve queste categorie:

-   **Rete:** Qualità audio incentrata sull'utilizzo di metriche di flusso scarso (PSR), uso TCP, subnet cablata e wireless e identificazione dell'uso di proxy HTTP e VPN

-   **Endpoint:** Dispositivi audio e client aggiornati

-   **Gestione dei servizi:** Questa categoria comprende due sezioni:

    -   Per prima cosa, la responsabilità di Microsoft è gestire e mantenere i team e i servizi Skype for business online.

    -   In secondo luogo, le attività gestite dall'organizzazione per garantire un accesso affidabile al servizio, ad esempio l'aggiornamento delle informazioni sugli edifici e il mantenimento dei firewall per i nuovi indirizzi IP di Office 365 quando l'infrastruttura viene aggiunta al servizio.

![Grafico delle categorie di qualità in un'organizzazione](media/qerguide-image-categories.png "Categorie di qualità in un'organizzazione: gestione dei servizi, endpoint e rete.")

Esaminare l'elenco seguente di attività consigliate per mantenere la qualità. È consigliabile eseguire queste attività regolarmente, ad esempio settimanalmente.

#### <a name="service-management-tasks"></a>Attività di gestione dei servizi

Queste attività variano da garantire che la larghezza di banda sia sufficiente per raggiungere il servizio senza saturare i collegamenti Internet, convalidando la qualità del servizio (QoS) in tutte le aree di rete gestite e rimanendo in primo piano sugli [intervalli IP di Office 365 nei firewall](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Attività di rete

Esistono due categorie di attività di rete: affidabilità e qualità. L'affidabilità si basa sulla misurazione della capacità dell'utente di effettuare chiamate con successo e rimanere connessi. La qualità si basa sulla telemetria aggregata inviata ai team e Skype for business online dal client dell'utente durante la chiamata e dopo la fine. 

Considerato l'impatto critico che l'affidabilità ha sull'esperienza utente, ti consigliamo di valutare e analizzare le metriche di affidabilità prima di immergerti in qualità. 

#### <a name="endpoints-tasks"></a>Attività endpoint

L'attività principale in questa categoria rimuove gli eventuali ostacoli agli [aggiornamenti del client di Team](teams-client-update.md)regolari. Per impostazione predefinita, teams aggiorna automaticamente regolarmente (a meno che non si disattivi l'impostazione, che non è consigliabile). 

Dovresti anche monitorare i dispositivi e specificare gli aggiornamenti ogni volta che identifichi i problemi relativi a un dispositivo.

## <a name="use-cqd-to-manage-call-quality"></a>Usare Call Quality dashboard per gestire la qualità delle chiamate

Dopo aver [configurato Call Quality dashboard](turning-on-and-using-call-quality-dashboard.md), si è pronti per iniziare a usarlo per gestire la qualità delle chiamate e delle riunioni per l'organizzazione.

La maggior parte dei problemi relativi alle prestazioni del team rientrano nelle categorie seguenti:

-   Firewall o configurazione proxy incompleta
-   Scarsa copertura Wi-Fi
-   Larghezza di banda insufficiente
-   VPN
-   Versioni e driver client non coerenti o obsoleti
-   Dispositivi audio non ottimizzati o incorporati
-   Subnet problematiche o dispositivi di rete

Se si prende il tempo necessario prima di distribuire Team per valutare queste aree e correggere eventuali carenze, è possibile ridurre la quantità di sforzi necessarie per mantenere un'esperienza di team di alta qualità per tutti gli utenti. Per informazioni sulla valutazione della rete in preparazione dell'implementazione del team, leggere [Advisor per i team](use-advisor-teams-roll-out.md) e [preparare la rete per i team](prepare-network.md).

### <a name="expectations-using-cqd"></a>Aspettative con Call Quality dashboard

Usa il dashboard qualità chiamata (Call Quality Dashboard) per ottenere informazioni sulla qualità delle chiamate effettuate tramite Team e servizi Skype for business. Call Quality dashboard è progettato per aiutare i team e gli amministratori di Skype for business e gli ingegneri di rete a ottimizzare la rete e a tenere d'occhio la qualità, l'affidabilità e l'esperienza utente. Call Quality dashboard analizza la telemetria aggregata per un'intera organizzazione, dove i modelli generali possono diventare evidenti; in questo modo è possibile effettuare valutazioni informate e pianificare il risanamento. Call Quality dashboard fornisce report di metriche che offrono informazioni generali sulla qualità, l'affidabilità e l'esperienza utente.

Call Quality dashboard, anche se utile per analizzare le tendenze e le subnet, non sempre offre una causa specifica per un determinato scenario. È importante capire questo aspetto e impostare l'aspettativa corretta quando si usa call Quality Dashboard:

-   Call Quality Dashboard non offre la causa radice per ogni scenario
-   Call Quality Dashboard non conterrà flussi di sistema telefonico o di audioconferenza
-   Call Quality dashboard definirà aree per ulteriori indagini in base alle tendenze

### <a name="cqd-reports-overview"></a>Panoramica sui report di Call Quality dashboard

Usare il menu a discesa nella parte superiore della schermata per aprire un report. Per un elenco dei dati forniti in ogni report, leggere [i dati disponibili nei report di Call Quality dashboard](CQD-data-and-reports.md#data-available-in-cqd-reports).

Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.


### <a name="teams-vs-skype-for-business"></a>Teams vs Skype for business

Call Quality dashboard può segnalare sia in team che in Skype for business. Tuttavia, potrebbero esserci momenti in cui vuoi sviluppare un report per guardare la telemetria di teams separata da Skype for business.

#### <a name="summary-reports"></a>Report di riepilogo

Per modificare la pagina dei report di riepilogo per visualizzare solo i team o Skype for business, selezionare il menu a discesa **filtro prodotto** nella parte superiore dello schermo e quindi selezionare il prodotto desiderato.

![Screenshot del menu a discesa che mostra le opzioni di filtro](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Report dettagliati

Per filtrare tutti i report dettagliati, nella barra del browser accodare il codice seguente alla fine dell'URL:

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Esempio**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Per altre informazioni sui filtri URL, vedere [filtrare i report](CQD-data-and-reports.md#report-filters) più avanti in questa sezione.

Per filtrare un singolo report dettagliato, aggiungere il filtro ``Is Teams`` al report e impostarlo su true o false.

![Screenshot della pagina Aggiungi filtro](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Gestite rispetto alle reti non gestite

Per impostazione predefinita, tutti gli endpoint in Call Quality dashboard sono classificati come esterni. Non appena viene introdotto un file di costruzione, possiamo iniziare a esaminare i dati degli endpoint gestiti. Come descritto in precedenza, le reti in Call Quality dashboard sono definite come segue:

-   Una _rete gestita_, spesso definita internamente o all'interno, può essere influenzata e controllata dall'organizzazione. Questo include la LAN interna, la WAN remota e la rete VPN.
-   L'organizzazione non può essere influenzata o controllata da una _rete non gestita_, spesso definita esternamente o all'esterno. Un esempio di rete non gestita è una rete alberghiera o aeroportuale.

### <a name="dimensions-measures-and-filters"></a>Dimensioni, misure e filtri

Una query Call Quality dashboard ben formata contiene tutti e tre i parametri seguenti:

-   **Dimensione:** Come si vuole eseguire il pivot sui dati.

-   **Misura:** Cosa voglio segnalare.

-   **Filtro:** Come si vuole ridurre il DataSet restituito dalla query.

Un altro modo per vedere la _dimensione_ è la funzione di raggruppamento, una _misura_ sono i dati che mi interessano e un _filtro_ è il modo in cui voglio limitare i risultati a quelli rilevanti per la query.

Un esempio di query ben formata è **Mostra i flussi poveri [measure] per subnet [Dimension] per l'edificio 6 [Filter]**. Per altre informazioni, vedere [dimensioni e misure disponibili in Call Quality dashboard](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Primo contro secondo 

Molte delle dimensioni e delle misure in Call Quality dashboard sono classificate come First o Second. Call Quality Dashboard non usa campi chiamante/chiamato, che sono stati rinominati _prima_ e _seconda_ perché sono presenti passaggi intermedi tra il chiamante e il chiamato. La logica seguente determina quale endpoint in questione è etichettato come primo:

-   **Prima di tutto** sarà sempre un endpoint server (Conference Server, Mediation Server e così via) se un server è coinvolto nel flusso o nella chiamata.

-   Il **secondo** sarà sempre un endpoint client, a meno che lo Stream non si trovi tra due endpoint server.

-   Se entrambi gli endpoint sono dello stesso tipo, la scelta della prima si basa sull'ordinamento interno della categoria agente utente. Ciò assicura che l'ordinamento sia coerente.

Per altre informazioni su come determinare il primo o il secondo endpoint quando sono uguali, vedere [dimensioni e misure disponibili in Call Quality dashboard](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Stream vs. chiamata

È necessario comprendere la differenza tra una chiamata e uno Stream per scegliere correttamente le dimensioni o le misure da esaminare in Call Quality dashboard. Anche se lo stato attivo principale di Call Quality dashboard è sui flussi, sono disponibili anche le misurazioni basate su chiamata.

-   **Stream:** Un _flusso_ esiste tra due solo endpoint. È disponibile un solo flusso per ogni direzione e sono necessari due flussi per la comunicazione. I flussi sono utili per analizzare edifici, reti o sottoreti. In alcuni casi, sia la chiamata che il flusso vengono usati nel nome della misura (ad esempio, chiama Stream setup o chiama Stream). Questi sono ancora classificati come flussi.

-   **Chiamata:** Una _chiamata_ è un raggruppamento di tutti i flussi di tutti i partecipanti. Una chiamata è costituita da-almeno due flussi. Una singola chiamata avrà almeno due endpoint, ognuno con un minimo di un flusso.

Per altre informazioni sul fatto che la dimensione o la misura faccia riferimento a una chiamata o a un flusso, vedere [dimensioni e misure disponibili in Call Quality dashboard](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Chiamate valide, scadenti e non classificate

Una chiamata viene categorizzata come valida, scadente o non classificata. Prendiamo un momento per parlare di ognuno in modo più dettagliato.

-   **Buona o povera:** Una chiamata buona o povera è costituita da una chiamata che contiene un set completo di metriche del servizio, per cui è stato generato e ricevuto un report QoE completo dal servizio. [In questo articolo](#poor-stream-rate)viene descritto come determinare se un flusso è buono o scadente.

-   Non **Classificato:** Un flusso non classificato non contiene un set completo di metriche dei servizi. Queste possono essere chiamate brevi, in genere inferiori a 60 secondi, in cui non è stato possibile calcolare la media e non è stato generato un report QoE. Il motivo più comune per cui le chiamate non sono classificate è che l'utilizzo di pacchetti non è minimo. Un esempio di questo è un partecipante che partecipa a una riunione in sordina e non parla mai. Il partecipante riceve, ma non trasmette, elementi multimediali. Senza la trasmissione di elementi multimediali, non saranno disponibili metriche per Call Quality dashboard da usare per classificare il flusso multimediale in uscita dell'endpoint.

Per altre informazioni, leggere la [classificazione in Stream in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Subnet comuni

Le subnet comuni sono sottoreti private specifiche usate da Alberghi, reti Home, hotspot e aree simili. Queste subnet sono difficili da valutare a causa del loro uso diffuso. Se l'organizzazione usa una di queste subnet comuni, è consigliabile trasferirla in un'altra subnet. Questo semplifica la creazione di report in Call Quality dashboard. Una volta notati, i report nel modello tutte le reti sono stati configurati in modo da escludere queste subnet per eliminarle come origine di qualità scadente. Le subnet comuni sono definite di seguito. il loro impatto varia a seconda dell'organizzazione.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Quando si esamina una rete gestita che usa una subnet comune, è necessario usare la seconda dimensione IP locale riflessiva per raggruppare le subnet. Questa dimensione contiene l'indirizzo IP pubblico dell'endpoint.


## <a name="reliability-investigations"></a>Indagini sull'affidabilità

Il primo passaggio per migliorare la qualità consiste nel valutare lo stato di affidabilità nell'organizzazione. Dato che l'affidabilità è fondamentale per un'esperienza utente positiva, iniziamo con i due componenti che misurano l'affidabilità:

1.  **Errori di configurazione:** Non è stato possibile stabilire la chiamata.

2.  **Eliminare gli errori:** La chiamata è stata stabilita e terminata in modo imprevisto.

In questa sezione verranno illustrati i metodi per analizzare entrambe le aree.

> [!NOTE]
> Non tutti i report inclusi nei modelli sono descritti in questo articolo. Tuttavia, i metodi di analisi descritti di seguito si applicano ancora. Per altre informazioni, vedere la descrizione del report specifico.


### <a name="setup-failures"></a>Errori di configurazione

Definire la priorità per correggere gli errori di configurazione in quest'area, perché questi errori hanno un impatto negativo significativo sull'esperienza utente.

Iniziare la ricerca valutando la percentuale di errori generali di configurazione per l'organizzazione e quindi assegnare la priorità alle aree di indagine in base alla percentuale più alta per edificio o rete. 

#### <a name="setup-failure-trend-analysis"></a>Analisi delle tendenze di errore di configurazione

Questo report Visualizza la quantità totale di flussi, gli errori di configurazione del flusso e la frequenza di errore della configurazione del flusso. Posizionare il puntatore su una delle colonne per visualizzare i singoli valori. 

##### <a name="analysis"></a>Analisi

Usando questo report, è possibile rispondere alle domande seguenti e determinare la prossima procedura:

-   Qual è la percentuale di errore totale della configurazione delle chiamate per il mese corrente?

-   La percentuale di errore di configurazione totale delle chiamate è inferiore o superiore alla metrica di destinazione definita?

-   La tendenza al fallimento è peggiore o migliore del mese precedente?

-   La tendenza al fallimento aumenta, ferma o diminuisce?

Indipendentemente dalle risposte a queste domande, è necessario esaminare ulteriormente l'utilizzo dei report secondari per cercare eventuali singoli edifici o subnet che potrebbero richiedere il risanamento. Anche se il tasso di errore complessivo potrebbe essere inferiore alla metrica di destinazione, le percentuali di errore per uno o più edifici o reti potrebbero essere superiori alle metriche di destinazione e devono essere investigate.

#### <a name="setup-failure-investigations"></a>Analisi degli errori di installazione 

Questo report riepilogativo viene usato per individuare e isolare eventuali edifici o reti che potrebbero essere necessarie per la correzione.

> [!NOTE]
> Assicurarsi di regolare il filtro rapporto mese-anno nel mese corrente. Selezionare **modifica**e regolare il filtro rapporto **mese-anno** per salvare il nuovo mese predefinito.

##### <a name="remediation"></a>Correzioni 

Concentrare i primi sforzi di correzione per gli edifici o le subnet che hanno il più grande volume di errori. Questo consente di massimizzare l'impatto sull'esperienza utente e aiutare a ridurre rapidamente la frequenza degli errori di configurazione delle chiamate organizzative. Nella tabella seguente sono elencati i due motivi per cui gli errori di configurazione sono riportati da Call Quality dashboard.

| Causa errori di configurazione delle chiamate       | Causa tipica                    |
|----------------------------------|----------------------------------|
| Regola di esenzione dall'ispezione profonda del pacchetto FW mancante | Indica che le apparecchiature di rete lungo il percorso impedivano che il percorso multimediale venisse stabilito a causa di regole di controllo dei pacchetti approfondite. Questo è probabilmente dovuto alle regole del firewall che non vengono configurate correttamente. In questo scenario l'handshake TCP ha avuto esito positivo, ma l'handshake SSL non è riuscito.      |
| Regola di eccezione del blocco IP FW mancante      | Indica che le apparecchiature di rete lungo il percorso impedivano che il percorso multimediale venisse stabilito nella rete Microsoft 365 o Office 365. Questo potrebbe essere dovuto a regole proxy o firewall non configurate correttamente per consentire l'accesso agli indirizzi IP e alle porte usati per i team e il traffico di Skype for business. |

Man mano che si inizia la correzione, è possibile concentrare gli sforzi su un determinato edificio o subnet. Come illustrato nella tabella precedente, questi problemi sono dovuti a configurazioni di firewall o proxy. Esaminare le opzioni della tabella seguente per le azioni correttive.

|      Correzioni      |Linee guida  |
|-----------------------|----------|
| Configurare i firewall | Collaborare con il team di rete e verificare la configurazione dei firewall con [l'elenco di indirizzi IP di Office 365](https://aka.ms/o365ips).<br><br>Verificare che le [subnet](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) e le porte multimediali siano incluse nelle regole del firewall. <br><br>Verificare che le [porte necessarie](prepare-network.md) vengano aperte nel firewall. UDP deve avere la priorità perché TCP è considerato un protocollo di failback per la condivisione dello schermo audio, video e video e il suo uso influirà sulla qualità della chiamata. La condivisione di applicazioni RDP legacy usa solo TCP.|

### <a name="drop-failures"></a>Eliminare gli errori

A differenza dei codici di errore di configurazione, Call Quality Dashboard non ha codice di errore di rilascio per indicare il motivo per cui si verificano errori di rilascio, che rende difficile isolare una causa radice specifica. Per migliorare la valutazione degli errori di eliminazione, usa un approccio dedotto. Rimediando a qualsiasi area di interesse per il contenuto multimediale, applicando la patch a client e driver e guidando l'uso di dispositivi certificati per team e Skype for business, ci si può aspettare che gli errori di rilascio vengano rifiutati.

#### <a name="drop-failure-trend-analysis"></a>Analisi delle tendenze di eliminazione degli errori

Questo report Visualizza la quantità totale di flussi audio, gli errori di rilascio totali e la frequenza di errore di rilascio. Posizionare il puntatore su una delle colonne per visualizzarne i valori. 


##### <a name="analysis"></a>Analisi

Usando questo tipo di report, è possibile rispondere alle domande seguenti:

-   Qual è la frequenza di errore di rilascio corrente?
-   La frequenza di errore di rilascio è inferiore alla metrica di destinazione definita?
-   La tendenza al fallimento è peggiore o migliore del mese precedente?
-   La tendenza al fallimento aumenta, ferma o diminuisce?

Indipendentemente dalle risposte alle domande di cui sopra, impiegare il tempo necessario per esaminare l'uso dei report secondari per cercare edifici o reti che potrebbero essere necessarie per la correzione. Anche se il tasso di errore globale della perdita potrebbe essere inferiore alla metrica di destinazione, la percentuale di errore di rientro per uno o più edifici o reti potrebbe essere superiore alla metrica di destinazione ed è necessario investigare.

#### <a name="drop-failure-investigations"></a>Eliminare le indagini di errore

Gli errori segnalati indicano che la chiamata è stata rilasciata in modo imprevisto e ha provocato un'esperienza utente negativa. A differenza dei report di tendenza, questi report includono ulteriori informazioni sulle subnet specifiche che richiedono ulteriori indagini.


##### <a name="remediation"></a>Correzioni

Usando i report tabella inclusi, è possibile isolare le aree problematiche nella rete in cui la frequenza di rilascio è superiore alla metrica di destinazione definita. Concentrare i primi sforzi di correzione per gli edifici o le subnet che hanno il numero totale di flussi totali per ottenere l'impatto più elevato.

Cause comuni delle cadute di chiamata:

-   Rete in base a provisioning o uscita Internet
-   Nessun QoS configurato su reti vincolate
-   Versioni client meno recenti
-   Comportamento degli utenti

Dopo aver individuato le aree problematiche, è possibile usare le [analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md) per esaminare ulteriormente gli utenti in tale edificio per problemi specifici. L'analisi delle chiamate contiene dati aggiuntivi di EUII e può essere utile per isolare ulteriormente i possibili motivi per gli errori di rilascio.

Indipendentemente dal passaggio successivo, è consigliabile informare l'helpdesk che è stato individuato un problema con edifici o subnet specifiche. Questo consente all'helpdesk di rispondere in modo più efficiente alle chiamate in arrivo e agli utenti di valutazione. Gli utenti contrassegnati possono quindi essere restituiti al team di progettazione per ulteriori indagini.

Nella tabella seguente sono elencati alcuni metodi comuni per gestire e correggere gli errori di rilascio.

| Correzioni                              | Linee guida                      |
|------------------------------------------|-------------------------------|
| **Rete/Internet**                         | **Congestione**: collaborare con il team di rete per monitorare la larghezza di banda in edifici/subnet specifici per verificare che siano presenti problemi di sovrautilizzo. Se si conferma la congestione della rete, valutare la possibilità di aumentare la larghezza di banda in tale edificio o di applicare QoS. Usare i [report di riepilogo del flusso di qualità](#quality-investigations) inclusi nei poveri per esaminare le subnet dei problemi per problemi di jitter, latenza e perdita di pacchetti, perché spesso precedono un flusso abbandonato.<br><br>**QoS**: se la larghezza di banda crescente non è pratica o costi-proibitivi, valutare l'implementazione di QoS. Questo strumento è molto efficace per gestire il traffico congestionato e può garantire che i pacchetti multimediali della rete gestita siano prioritari sopra il traffico non multimediale. In alternativa, se non ci sono prove chiare che la larghezza di banda è il colpevole, considera queste soluzioni:<ul><li>[Guida QoS di Microsoft Teams](qos-in-teams.md)</li></ul><br>**Eseguire una valutazione della conformità della rete**: una valutazione della rete fornisce informazioni dettagliate sull'utilizzo previsto della larghezza di banda, su come gestire la larghezza di banda e le modifiche della rete e sulle procedure consigliate per la rete per team e Skype for business. Usando la tabella precedente come origine, è presente un elenco di edifici o sottoreti che sono candidati eccellenti per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul> |
| **Client (solo Skype for business online)** | Alcuni client Skype for business meno recenti sono noti e documentati con l'affidabilità dei contenuti multimediali. Esaminare i report di analisi delle chiamate da più utenti interessati oppure creare un report della tabella della versione client personalizzata in Call Quality dashboard filtrato in edifici o subnet specifiche con l'errore totale delle chiamate perse% Measure. Queste informazioni ti aiuteranno a capire se esiste una relazione tra le cadute delle chiamate in quell'edificio specifico e una versione specifica del client.     |
| **Dispositivi**                                  |Se i dispositivi sono il colpevole dei problemi di qualità delle chiamate, è consigliabile aggiornare i dispositivi incriminati. Leggere [i telefoni per i team](phones-for-teams.md) per saperne di più. |
| **Comportamento degli utenti**                            | Se si determina che non sono presenti reti, dispositivi o client, valutare la possibilità di sviluppare una strategia di adozione degli utenti per informare i clienti sulle modalità di partecipazione e uscita delle riunioni. Un team più intelligente e un utente di Skype for business produrrà un'esperienza utente migliore per tutti i partecipanti alla riunione. Ad esempio, un utente che mette il proprio portatile in stato di sospensione (chiudendo il coperchio) senza uscire dalla riunione verrà classificato come un calo di chiamata imprevisto.   |

## <a name="quality-investigations"></a>Indagini di qualità

Il passaggio successivo per valutare lo stato di qualità audio in tutta l'organizzazione consiste nell'esaminare l'utilizzo di flussi di flusso scadenti (PSR), TCP e proxy. È importante ricordare che i dati di Call Quality Dashboard non forniscono una causa radice specifica, ma forniscono probabilmente aree problematiche per iniziare una conversazione collaborativa con i team appropriati per le attività di correzione. 

> [!NOTE]
> Non tutti i report inclusi nei modelli sono descritti in questo articolo. Tuttavia, i metodi di analisi descritti di seguito verranno comunque applicati per tali report. Per altre informazioni, vedere la descrizione del report specifico. 

### <a name="quality"></a>Qualità

Le percentuali PSR vengono usate per indicare se l'organizzazione sta incontrando destinazioni metriche definite per una data area di attivazione. È importante tenere presente che, anche se le percentuali di alto livello si trovano all'interno della destinazione definita, le singole subnet o gli edifici potrebbero non corrispondere agli obiettivi definiti e quindi necessitano di ulteriori indagini. Ad esempio, se la percentuale complessiva di V.Q.P.R.D. è pari al 2% in aprile, che soddisfa la destinazione di esempio, i singoli edifici e subnet potrebbero avere ancora esperienze scadenti, a seconda della distribuzione complessiva del 2%. 

Per valutare la percentuale di flussi poveri, usare i report qualità. Vengono forniti diversi report di qualità per esaminare le metriche per le informazioni generali, di conferenza, per due parti, le chiamate PSTN, le VPN e le sale riunioni. Vengono forniti report mensili, settimanali e giornalieri per facilitare questo processo. I report settimanali e giornalieri sono limitati al modello reti gestite per aumentare l'efficacia e ridurre il rumore. 

#### <a name="quality-trend-analysis"></a>Analisi delle tendenze di qualità

I report di tendenza visualizzano le informazioni sulla qualità nel tempo e vengono usate per identificare e comprendere le tendenze qualitative all'interno di ogni area di interesse. Come indicato in precedenza, sono presenti alberi di report inclusi nei modelli per l'analisi della qualità; conferenze, due parti, chiamate PSTN, VPN e sale riunioni. Allo scopo di analizzare la qualità, il processo investigativo è lo stesso. Tuttavia, ti consigliamo di iniziare prima con i servizi di conferenza, perché i miglioramenti apportati alla qualità della conferenza influiranno positivamente anche su tutte le altre aree. 

> [!Note]
> Le indagini su due parti, chiamate PSTN e sale riunioni sono simili ai servizi di conferenza. Lo stato principale consiste nell'isolare gli edifici o le subnet che hanno la qualità peggiore e identificare il motivo della scarsa qualità.

> [!Important]
> I report basati su VPN vengono filtrati tramite la seconda dimensione VPN. Questa dimensione richiede che la scheda di rete VPN sia registrata correttamente come adattatore di accesso remoto. I fornitori VPN non usano questo contrassegno in modo affidabile e il chilometraggio varia a seconda del fornitore di VPN distribuito nell'organizzazione. Se necessario, modificare i report [VPN](CQD-upload-tenant-building-data.md#vpn) usando il nome dell'edificio o della rete.

##### <a name="investigation"></a>Indagine

Usando questi report, è possibile rispondere alle domande seguenti:

-   Qual è il PSR totale per il mese corrente?
-   Il PSR è sotto la metrica di destinazione definita?
-   PSR è peggiore o migliore del mese precedente?
-   La tendenza PSR sta aumentando, stabilendo o diminuendo?

Indipendentemente dalle risposte alle domande di cui sopra, impiegare il tempo necessario per esaminare i report secondari per cercare eventuali edifici o subnet che potrebbero richiedere indagini. Anche se il PSR complessivo potrebbe essere inferiore alla metrica di destinazione, spesso il PSR per uno o più edifici o reti supera la metrica e richiede il risanamento.

#### <a name="quality-investigations"></a>Indagini di qualità

I report di riepilogo qualità consentono di comprendere in modo più approfondito ciò che ha contribuito a classificare i flussi come poveri e consente di isolare le aree problematiche nella rete gestita.

Anche se le dimensioni usate potrebbero differire leggermente tra report, ogni report includerà misure per i flussi totali, il totale dei flussi poveri, il PSR e la qualità scadente a causa di. Sono stati creati report per ogni area di interesse: Servizi di conferenza, due parti, chiamate PSTN, VPN e sale riunioni. Il modello di rete gestita include report aggiuntivi per sfruttare le informazioni sulla posizione caricate tramite il file di costruzione.


> [!Note]
> Le subnet comuni sono difficili da valutare a causa del loro uso diffuso. Un report distinto che Visualizza l'IP pubblico del client (secondo IP locale riflessivo) è stato aggiunto al modello tutte le reti per facilitare gli uffici di correzione che usano reti comuni.


![Schermata che mostra il riepilogo del flusso audio scadente](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Correzioni

Concentrare gli sforzi di correzione per gli edifici o le subnet che hanno il più grande volume di flussi, perché questo massimizza l'impatto e contribuisce a migliorare rapidamente l'esperienza utente. Usare le misure per il jitter, la perdita di pacchetti e il tempo di andata e ritorno (RTT) per capire cosa contribuisce alla qualità scadente (è possibile che ci siano più problemi):

-   **Jitter**: i pacchetti multimediali arrivano a velocità diverse, che causano l'audio di un altoparlante.
-   **Perdita di pacchetti**: i pacchetti multimediali vengono eliminati, per creare l'effetto di parole o sillabe mancanti.
-   **RTT**: i pacchetti multimediali impiegano molto tempo per raggiungere la destinazione, creando così un effetto walkie-talkie.

Per facilitare l'analisi dei problemi di qualità, USA [analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md). Con le analisi delle chiamate, è possibile esaminare un report specifico sulla chiamata di una conferenza o un utente. Questo report conterrà dati EUII/PII ed è utile quando si sta cercando la causa di un errore. Dopo aver individuato quale edificio è interessato, dovrebbe essere semplice tenere traccia degli utenti in quell'edificio. 

Non dimenticare di informare l'helpdesk che queste reti stanno riscontrando problemi di qualità, in modo che possano valutare e rispondere rapidamente alle chiamate in arrivo.

| Correzioni                              | Linee guida                         |
|------------------------------------------|----------------------------------|
| **Reti**                                 | **Congestione**: una rete overused o under-provisioning può causare problemi di qualità multimediale. Collaborare con il team di rete per determinare se le connessioni di rete dall'utente al punto di uscita Internet dispongano di larghezza di banda sufficiente per supportare il supporto. <br><br>**Eseguire una valutazione della conformità della rete**: una valutazione della rete fornisce informazioni dettagliate sull'utilizzo previsto della larghezza di banda, su come gestire la larghezza di banda e le modifiche della rete e sulle procedure consigliate per la rete per team e Skype for business. Usando la tabella precedente come origine, è presente un elenco di edifici o sottoreti che sono candidati eccellenti per una valutazione.<ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li></ul>|
| **QoS (Quality of Service)**  | QoS è uno strumento collaudato per dare priorità ai pacchetti in una rete congestionata per assicurarsi che arrivino a destinazione intatto e puntuale. Valutare l'implementazione della funzionalità QoS nell'organizzazione per massimizzare la qualità dell'esperienza utente in cui è vincolata la larghezza di banda. QoS consentirà di risolvere i problemi tipicamente associati ad alti livelli di perdita di pacchetti e, in misura minore, a jitter e tempi di andata e ritorno.<ul><li>[Guida QoS Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | La rete Wi-Fi può avere un impatto significativo sulla qualità delle chiamate. Le distribuzioni Wi-Fi non prendono in genere in considerazione i requisiti di rete per i servizi VoIP e spesso sono una fonte di scarsa qualità. Per altre informazioni su come ottimizzare l'infrastruttura Wi-Fi, vedere [questo articolo sulla pianificazione Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Driver wireless**: verificare che i driver wireless siano aggiornati. Ciò consentirà di mitigare qualsiasi esperienza utente scadente correlata a un driver obsoleto. Molte organizzazioni non includono driver wireless nei loro cicli di patch e questi driver possono non essere inviati per anni. Molti problemi wireless vengono risolti garantendo che i driver wireless siano aggiornati.<br><br>**WMM**: Wireless Multimedia Extensions (WMM), noto anche come Wi-Fi Multimedia, offre funzionalità di base QoS alle reti wireless. Le moderne reti wireless devono supportare molti dispositivi. Questi dispositivi competono per la larghezza di banda e possono determinare problemi di qualità per i servizi VoIP, dove la velocità e la latenza sono essenziali. Consulta il fornitore wireless per informazioni specifiche e valuta l'implementazione di WMM sulla tua rete wireless per dare priorità a Skype for business e a teams media.<br><br>**Densità del punto di accesso**: i punti di accesso possono essere troppo distanti o non in una posizione ideale. Per ridurre al minimo le potenziali interferenze, posizionare punti di accesso aggiuntivi nelle sale riunioni e in posizioni non ostruite da muri o altri oggetti in cui il segnale Wi-Fi è debole.<br><br>**2,4 GHz versus 5 GHz**: 5 GHz fornisce meno interferenze in background e velocità più elevate e dovrebbe essere prioritario quando si distribuisce VoIP tramite Wi-Fi. Tuttavia, 5 GHz non è forte quanto 2,4 GHz e non penetra facilmente nelle pareti. Esaminare il layout dell'edificio per determinare la frequenza su cui si può fare affidamento per la connessione ottimale. |
|**Dispositivo di rete** | Le organizzazioni più grandi potrebbero avere centinaia di dispositivi distribuiti in rete. Collaborare con il team di rete per verificare che i dispositivi di rete dell'utente a Internet vengano mantenuti e aggiornati. |
| **VPN**  | Gli apparecchi VPN non sono tradizionalmente progettati per gestire i carichi di lavoro multimediali in tempo reale. Alcune configurazioni VPN vietano l'uso di UDP (che è il protocollo preferito per l'elemento multimediale) e si basano solo su TCP. Valutare l'implementazione di una soluzione per la suddivisione in tunnel VPN per ridurre la VPN come fonte di scarsa qualità. |
| **Client** <br>(Solo Skype for business online) | Verificare che tutti i client vengano aggiornati regolarmente. |
| **Dispositivi** | Se i dispositivi sono il colpevole dei problemi di qualità delle chiamate, è consigliabile aggiornare i dispositivi incriminati. Leggere [i telefoni per i team](phones-for-teams.md) per saperne di più. |
| **Driver** | I driver di rete (Ethernet e Wi-Fi), audio, video e USB dovrebbero far parte della strategia di gestione delle patch complessiva. Molti problemi di qualità vengono risolti aggiornando i driver. |
| **Sale riunioni su Wi-Fi** | È consigliabile che i dispositivi della sala riunioni siano connessi alla rete utilizzando almeno una connessione Ethernet da 1 Gbps. I dispositivi della sala riunioni includono in genere più flussi audio e video, oltre al contenuto della riunione, ad esempio la condivisione dello schermo, e hanno requisiti di rete più alti rispetto ad altri team o endpoint di Skype for business. Le sale riunioni sono, per definizione, dispositivi stazionari in cui la rete Wi-Fi offre un vantaggio solo durante l'installazione.<br><br>Le sale riunioni devono essere trattate con cura e attenzione per fare in modo che l'esperienza con questi dispositivi sia conforme o superiore alle aspettative. I problemi di qualità con le sale riunioni vengono in genere escalati rapidamente, perché spesso vengono usati da personale di alto livello.<br><br>La prestazione Wi-Fi è spesso inferiore a una connessione cablata, a parità di tutte le caratteristiche (a prescindere dalla convenienza). Con l'aumento dei criteri "porta il tuo dispositivo" e la proliferazione dei portatili, i punti di accesso Wi-Fi sono spesso sovrautilizzati. Gli elementi multimediali in tempo reale potrebbero non essere classificati in base alle reti Wi-Fi, che possono determinare problemi di qualità durante l'uso dei tempi di punta. Questo uso pesante può coincidere con una riunione in cui potrebbero esserci una dozzina di partecipanti, ognuno con il proprio portatile e smartphone, tutti connessi allo stesso punto di accesso Wi-Fi del dispositivo della sala riunioni.<br><br>La rete Wi-Fi dovrebbe essere considerata solo una soluzione temporanea, per un'installazione per dispositivi mobili o quando la connessione Wi-Fi è stata provisionata correttamente per supportare elementi multimediali basati su Business Class e in tempo reale. |


### <a name="tcp"></a>TCP 

TCP (Transmission Control Protocol) è considerato un trasporto di failback e non il trasporto primario che si vuole usare per i supporti in tempo reale. Il motivo per cui è un trasporto di failback è dovuto alla natura dello stato di TCP. Ad esempio, se una chiamata viene eseguita in una rete latente e i pacchetti multimediali sono in ritardo, i pacchetti di pochi secondi fa, che non sono più utili, competono per la larghezza di banda per accedere al destinatario, che può peggiorare la situazione. Questo fa sì che il guaritore audio cucini e si estenda l'audio, ottenendo artefatti udibili, spesso sotto forma di jitter.

I report in questa sezione non distinguono tra flussi buoni e poveri. In base alle preferenze di UDP, i report cercano l'uso di TCP per la condivisione dello schermo audio, video e video (VBSS). Vengono fornite tariffe di flusso insufficienti per confrontare la qualità UDP rispetto alla qualità TCP, in modo da poter concentrare gli sforzi in cui l'impatto è il più grande. L'utilizzo di TCP è principalmente causato da regole di firewall incomplete. Per altre informazioni sulle regole del firewall per team e Skype for business online, vedere [URL e intervalli di indirizzi IP di Microsoft 365 e Office 365](https://aka.ms/o365ips).

> [!Note]
> Le funzionalità audio, video e VBSS preferiscono il trasporto principale UDP. Il carico di lavoro di condivisione dell'applicazione RDP legacy usa solo TCP.

#### <a name="tcp-usage"></a>Utilizzo di TCP

I report TCP indicano l'utilizzo complessivo di TCP negli ultimi sette mesi. Tutti gli altri report in questa sezione consentiranno di limitare la riduzione di edifici e subnet specifici in cui TCP viene usato più comunemente. I report distinti sono disponibili sia per i flussi di conferenza che per quelli a due parti.

![Grafico che mostra la percentuale di flussi audio che usano TCP](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Indagine

Usando questo report, è possibile rispondere alle domande seguenti:

-   Qual è il volume totale dei flussi TCP per il mese corrente?
-   È peggio o migliore del mese precedente?
-   La tendenza all'uso TCP aumenta, si stabilizza o diminuisce?
-   Il PSR TCP è lo stesso del PSR globale?

Se si nota che la tendenza all'uso di TCP aumenta o supera l'utilizzo mensile normale, è possibile usare i report secondari per individuare eventuali edifici o reti che potrebbero essere necessarie per la correzione. In teoria, puoi usare il minor numero possibile di sessioni audio basate su TCP nella rete gestita.

#### <a name="tcp-vs-udp"></a>TCP e UDP

Questo report identifica il volume di report sull'utilizzo di TCP o UDP nell'ultimo mese per la condivisione dello schermo audio, video e video (VBSS). 

![Report che mostra il volume di flussi che usano TCP o UDP](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analisi

Anche se si vuole che l'utilizzo di TCP sia il più basso possibile, potrebbe essere visualizzato un po' di utilizzo di TCP in una distribuzione altrimenti sana. TCP da solo non contribuirà a una chiamata scadente, quindi vengono fornite tariffe di flusso per determinare se l'uso di TCP è un collaboratore di qualità scadente. 

#### <a name="tcp-investigations"></a>Indagini TCP

Nei modelli di Call Quality dashboard forniti passare ai flussi TCP tramite la creazione e i report di subnet tramite il modello reti gestite o tutte le reti. Allo scopo di analizzare l'uso di TCP, il processo è lo stesso, quindi concentriamo la discussione qui in conferenza.


##### <a name="remediation"></a>Correzioni

Questo report identifica edifici e subnet specifici che contribuiscono al volume dell'utilizzo di TCP. Viene inoltre incluso un report aggiuntivo per identificare l'IP di inoltro Microsoft usato nella chiamata per isolare le regole del firewall mancanti. Concentrare gli sforzi di correzione per gli edifici che hanno il volume più alto di flussi TCP per massimizzare l'impatto.

La causa più comune dell'utilizzo di TCP mancano le regole di eccezione nei firewall o nei proxy. Parleremo di proxy nella sezione successiva, quindi per ora concentrare gli sforzi sui firewall. Usando l'edificio o la subnet fornita, puoi determinare quale firewall deve essere aggiornato.

| Correzioni        | Linee guida     |
|--------------------|--------------------------------------|
| Configurare il firewall | Verificare che le [porte e gli indirizzi IP di Microsoft 365 o Office 365](https://aka.ms/o365ips) siano esclusi dal firewall. Per i problemi TCP correlati ai contenuti multimediali, concentrare gli sforzi iniziali sui seguenti:<ul><li>Verificare che le subnet multimediali client 13.107.64.0/18 e 52.112.0.0/14 siano presenti nelle regole del firewall.</li><li>Porte UDP 3478 – 3481 sono le porte multimediali necessarie e devono essere aperte, in caso contrario il client non tornerà alla porta TCP 443.</li></ul> |
| Verificare             | Usare lo [strumento di valutazione della rete Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) per verificare la connettività a specifici indirizzi IP di Microsoft 365 o Office 365 e alle porte dall'edificio o dalla subnet interessata.    |

### <a name="http-proxy"></a>Proxy HTTP

I proxy HTTP non sono il percorso preferito per la creazione di sessioni multimediali, per una moltitudine di motivi. Molti contengono funzionalità Deep Packet Inspection che possono impedire il completamento delle connessioni al servizio e l'introduzione di interruzioni. Inoltre, quasi tutti i proxy forzano TCP invece di consentire l'UDP, consigliato per una qualità audio ottimale.

Ti consigliamo sempre di configurare il client per la connessione diretta ai team e ai servizi Skype for business. Questo aspetto è particolarmente importante per il traffico basato su supporti multimediali.


> [!IMPORTANT]
> È consigliabile caricare un file di [compilazione valido](CQD-upload-tenant-building-data.md) in modo da distinguere l'interno da flussi audio esterni durante l'analisi dell'utilizzo del proxy. 


#### <a name="http-proxy-usage"></a>Uso del proxy HTTP

Il report del flusso del proxy HTTP in questa sezione del modello è molto simile ai report TCP. Non è possibile verificare se le chiamate sono scarse o valide, ma se la chiamata è connessa tramite HTTP.

![Screenshot del report di flussi audio che usano HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analisi

Si vogliono vedere come pochi flussi multimediali HTTP possibili. Se si hanno flussi che attraversano il proxy, consultare il team di rete per verificare che siano presenti le esclusioni appropriate in modo che i client vengano direttamente indirizzati a teams o alle subnet multimediali di Skype for business online.

Se si ha un solo proxy Internet nell'organizzazione, verificare le esclusioni appropriate per gli [URL di Microsoft 365 o di Office 365 e per gli intervalli di indirizzi IP](https://aka.ms/o365ips). Se nell'organizzazione sono configurati più proxy Internet, usare il sottoreport HTTP per isolare l'edificio o la subnet interessata.

Per le organizzazioni che non possono ignorare il proxy, assicurati che il client Skype for business sia configurato per l'accesso in modo corretto quando si trova dietro un proxy, come descritto nell'articolo [Skype for business dovrebbe usare il server proxy per accedere invece di provare a connettersi direttamente](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Indagini proxy HTTP

Questo report identifica edifici e subnet specifici che contribuiscono all'utilizzo di HTTP.


##### <a name="remediation"></a>Correzioni

Ti [consigliamo](proxy-servers-for-skype-for-business-online.md) di ignorare sempre i proxy per Skype for business e teams, in particolare per il traffico multimediale. I proxy non rendono Skype for business più sicuro, perché il traffico è già crittografato. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. I problemi come questi generano un'esperienza negativa con la condivisione audio, video e dello schermo, dove i flussi in tempo reale sono essenziali.

La causa più comune dell'utilizzo HTTP mancano le regole di eccezione nei proxy. Utilizzando l'edificio o la subnet specificata, è possibile determinare rapidamente quale proxy deve essere configurato per il bypass multimediale.

Verificare che i nomi di [dominio completi Microsoft 365 o Office 365](https://aka.ms/o365ips) siano disponibili in whitelist nel proxy.

## <a name="endpoint-investigations"></a>Indagini endpoint

Questa sezione è incentrata sulle attività per la creazione di report sulle versioni client e sull'uso di dispositivi certificati. I report sono disponibili per strutturare l'utilizzo per le versioni client, il tipo di client, i dispositivi di acquisizione e i driver (microfono), i dispositivi di acquisizione video e il fornitore e le versioni del driver Wi-Fi.

> [!NOTE]
> Non tutti i report inclusi nei modelli sono descritti in questo articolo. Tuttavia, i metodi di analisi descritti di seguito si applicano ancora. Per altre informazioni, vedere la descrizione del report specifico.

### <a name="client-versions"></a>Versioni client

Questi report evidenziano l'identificazione delle versioni client Skype for business in uso e il relativo volume relativo nell'ambiente.

> [!IMPORTANT]
> Attualmente i client di team vengono distribuiti e aggiornati automaticamente tramite la rete di distribuzione dei contenuti di Azure e verranno mantenuti aggiornati dal servizio. Di conseguenza, non è necessario monitorare le versioni client di Teams (a meno che non si spenga l'aggiornamento automatico, che non è consigliabile).

A meno che non si escludano i dati dei partecipanti federati, questi report includeranno la telemetria client dagli endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per il secondo ID tenant impostato sull' [ID tenant](CQD-data-and-reports.md#how-to-find-your-tenant-id)dell'organizzazione. In alternativa, puoi usare un [filtro URL](CQD-data-and-reports.md#url-filters) per escludere la telemetria dei partecipanti federati.



#### <a name="remediation"></a>Correzioni

Una parte fondamentale della gestione delle esperienze degli utenti di alta qualità assicura che i client gestiti eseguano versioni aggiornate di Skype for business, oltre a garantire che i driver audio, video, di rete e USB di supporto siano aggiornati. In questo articolo vengono forniti diversi vantaggi, tra cui: 

-   È più semplice gestire alcune versioni rispetto a molte versioni.
-   Offre un livello di coerenza dell'esperienza.
-   Semplifica la risoluzione dei problemi relativi alla qualità delle chiamate e all'usabilità.
-   Microsoft apporta continuamente miglioramenti e ottimizzazioni generali in tutto il prodotto. Assicurarsi che gli utenti ricevano questi aggiornamenti riducano il rischio di un problema già risolto.

La limitazione della distribuzione alle versioni client con meno di sei mesi migliorerà l'esperienza complessiva degli utenti e migliorerà la gestibilità riducendo il numero di versioni che devono essere supportate.

Se si usa solo Office a portata di clic, è possibile passare automaticamente all'interno della finestra di sei mesi. Non è necessaria alcuna ulteriore azione.

Se si ha una combinazione di pacchetti a portata di clic e di installazione (MSI), è possibile usare il report per verificare che i client MSI vengano aggiornati regolarmente. Se si nota che i clienti sono in ritardo, collaborare con il team responsabile della gestione degli aggiornamenti di Office e verificare che l'approvazione e la distribuzione delle patch client siano regolari.

È inoltre importante considerare e verificare che anche i driver di rete, video, USB e audio vengano corretti. Può essere facile ignorare questi driver e non includerli nella strategia di gestione delle patch.

I numeri di versione per Skype for business possono essere trovati tramite i collegamenti seguenti:

-   [Rilasciare informazioni per gli aggiornamenti delle app Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Cronologia degli aggiornamenti per le app Microsoft 365 per le aziende](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Download e aggiornamenti per Skype for Business](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Dispositivi

Per usare il report del dispositivo microfonico, è necessario comprendere il concetto di Punteggio di opinione media (MOS). MOS è la misura standard Gold per valutare la qualità audio percepita. È rappresentato come un numero intero compreso tra 0 e 5.

La base di tutte le misure di qualità vocale è il modo in cui una persona percepisce la qualità del discorso. Dato che è influenzato dalla percezione umana, è intrinsecamente soggettivo. Esistono diverse metodologie per i test soggettivi. La maggior parte delle misure di qualità vocale si basa su una scala di classificazione assoluta (ACR).

In un test soggettivo di ACR un numero statisticamente significativo di persone valuta la qualità dell'esperienza in una scala da 1 (cattivo) a 5 (eccellente). La media dei punteggi è il MOS. Il MOS risultante dipende dall'intervallo di esperienze che sono state esposte al gruppo e dal tipo di esperienza che si sta valutando.

Dato che non è pratico eseguire test soggettivi di qualità vocale per un sistema di comunicazione live, Microsoft teams e Skype for business generano valori MOS usando algoritmi avanzati per prevedere oggettivamente i risultati di un test soggettivo.

Il set disponibile di MOS e metriche associate consente di visualizzare la qualità dell'esperienza che viene recapitata agli utenti da un dispositivo audio. 

Fornendo agli utenti i dispositivi certificati per i team e Skype for business, è possibile ridurre la probabilità di incontrare esperienze negative dovute al dispositivo stesso (che è più probabile, ad esempio, con gli altoparlanti e i microfoni del portatile integrati). Per altre informazioni, vedere questi articoli sul [programma di certificazione](/SkypeForBusiness/certification/overview) e il [Catalogo soluzioni partner](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

I report del dispositivo vengono usati per valutare l'uso del dispositivo in base al Punteggio di volume e MOS (solo audio) e possono essere trovati nei modelli di accompagnamento in client & dispositivi. 

> [!IMPORTANT]
> A meno che non si escludano i dati dei partecipanti federati, questi report includeranno la telemetria client dagli endpoint federati. Per escludere gli endpoint federati, è necessario aggiungere un filtro di query per il **secondo ID tenant** impostato sull' [ID tenant](CQD-data-and-reports.md#how-to-find-your-tenant-id)dell'organizzazione. In alternativa, puoi usare un [filtro URL](CQD-data-and-reports.md#url-filters) per escludere la telemetria dei partecipanti federati.


> [!Note]
> Quando si visualizza questo report, è possibile che venga visualizzato lo stesso dispositivo segnalato più volte. Ciò è dovuto al modo in cui il dispositivo viene segnalato come segnalato in Call Quality dashboard. Le differenze tra le impostazioni locali dell'hardware e del sistema operativo causano differenze nella modalità di segnalazione dei dati del dispositivo.

##### <a name="remediation"></a>Correzioni

In genere, è necessario individuare e eliminare gradualmente i dispositivi non certificati e sostituirli con i dispositivi certificati. Alcune considerazioni relative alla revisione dei report sui dispositivi includono:

-   I dispositivi in uso sono certificati per i team e Skype for business? 
-   Puoi identificare gli utenti di un dispositivo specifico usando le [analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md). Verificare che abbiano i driver di dispositivo più recenti e che il dispositivo non sia connesso tramite un hub USB o una docking station. 
-   Quante versioni diverse di diversi driver sono in uso? Vengono regolarmente corretti? Verificare che i driver audio, video e Wi-Fi vengano corretti regolarmente per risolvere i problemi di qualità e rendere più prevedibile e coerente l'esperienza utente.

##### <a name="audio"></a>Audio

L'attività successiva consiste nel determinare l'utilizzo complessivo dei [dispositivi audio certificati](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). È consigliabile che almeno 80% di tutti i flussi audio usi un dispositivo audio certificato. Questa operazione viene eseguita in modo ottimale esportando il report dispositivi microfono in Excel per calcolare l'utilizzo di dispositivi certificati o approvati. Le organizzazioni in genere mantengono un elenco di tutti i dispositivi approvati, quindi filtrare e ordinare i dati dovrebbero essere semplici.

##### <a name="video"></a>Video

I driver video sono importanti anche per essere sempre aggiornati. Assicurarsi che le schede video vengano regolarmente patchate aiuteranno ad escludere i driver video come fonte di qualità scadente per i flussi video. L'uso di [dispositivi video certificati](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) consente di garantire un'esperienza utente fluida e di alta qualità. I dispositivi video che supportano la codifica nativa H. 264 sono preferiti per ridurre l'utilizzo della CPU durante la videoconferenza.

##### <a name="wi-fi"></a>Wi-Fi

Anche i driver Wi-Fi devono essere corretti per una cadenza regolare e devono essere inclusi nella strategia di gestione delle patch. Molti problemi di qualità possono essere corretti mantenendo i driver Wi-Fi aggiornati. Per altre informazioni su come ottimizzare l'infrastruttura Wi-Fi, vedere [questo articolo sulla pianificazione Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Argomenti correlati

[Usare Advisor per Teams](use-advisor-teams-roll-out.md)

[Preparare la rete per Teams](prepare-network.md)

[Principi di connettività di rete di Office 365](https://aka.ms/pnc)

[Analisi e creazione di report in teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gestire i dispositivi in Teams](device-management.md)

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Che cos'è Call Quality dashboard?](CQD-what-is-call-quality-dashboard.md)

[Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e della creazione](CQD-upload-tenant-building-data.md)

[Dati e report di Call Quality dashboard](CQD-data-and-reports.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)
