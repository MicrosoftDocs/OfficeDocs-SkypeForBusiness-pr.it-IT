---
title: Valutare l'ambiente per i workload vocali di Microsoft teams cloud
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare gli utenti e le analisi di rete per valutare la disponibilità dell'organizzazione, aprire le porte TCP e UDP corrette, eseguire le operazioni di correzione della rete.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ad3700b3b0186ba3e95d8f55ad704f37cf33bc7
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925077"
---
# <a name="evaluate-my-environment"></a>Valutare il proprio ambiente

Questo articolo offre una panoramica dei requisiti per valutare correttamente l'ambiente corrente per l'utilizzo dei servizi cloud Voice. Valutando l'ambiente, identifichi i rischi e i requisiti che influenzeranno la distribuzione globale della voce cloud. Identificando preventivamente questi elementi, è possibile modificare la pianificazione per guidare il successo.

## <a name="introduction-to-evaluating-your-environment"></a>Introduzione alla valutazione dell'ambiente 

Per ottenere i risultati delle chiavi oggettive (OKRs), in precedenza sono state effettuate le decisioni sui servizi chiave. Il passaggio successivo consiste nell'eseguire l'individuazione ambientale per valutare tutti gli aspetti relativi all'infrastruttura IT e alla telefonia, alla rete e alle operazioni per verificare che l'organizzazione sia pronta per l'implementazione della soluzione.

L'individuazione ambientale deve includere la valutazione della conformità della rete per garantire che la rete sia in grado di supportare l'implementazione di servizi di audioconferenza o di sistema telefonico con il servizio di chiamata piano.

Si identificano i rischi tecnici nell'ambito di una valutazione ambientale e di conformità all'adozione e si sviluppa un piano di attenuazione per ogni rischio identificato.
Dovresti includere queste informazioni nel registro dei rischi.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Ambiente corrente

Come parte della tua individuazione ambientale, Includi tutte le questioni relative al calcolo degli utenti finali, ad esempio una valutazione della conformità di PC e dispositivi mobili per supportare i servizi di audioconferenza e il sistema telefonico con i casi di utilizzo del piano di chiamata, da requisiti hardware a requisiti software.

L'individuazione ambientale può anche scoprire se è necessario [trasferire i numeri di telefono a Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
Questa operazione consentirà all'organizzazione di modificare il piano di progetto e di preparare le informazioni necessarie per la portabilità dei numeri. È possibile usare l' [individuazione ambientale per l'implementazione di Microsoft teams](environmental-discovery-for-microsoft-teams-rollout.md) per eseguire l'individuazione ambientale.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Chi sarà responsabile per il completamento di una valutazione ambientale?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare i risultati della valutazione dell'ambiente.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Funzionalità di valutazione della gestione delle modifiche e delle adozioni 

La distribuzione pone una nuova tecnologia a portata di mano di un utente, ma i risultati aziendali vengono realizzati solo dopo che gli utenti adottano realmente tale soluzione. Per garantire l'adozione di una nuova soluzione, è necessario concentrare gli sforzi sulla disponibilità degli utenti e sulla gestione delle modifiche. Per ottenere risultati ottimali, conduci la pianificazione della preparazione degli utenti come workstream parallelo alle tue attività di preparazione tecnica e incorpora le attività seguenti:

-   **Profilo dell'organizzazione e dell'utente:** Analisi delle ricettività organizzative per cambiare oltre a usare l'analisi case e persona

-   **Disponibilità e preparazione delle risorse:** Creazione di risorse di sensibilizzazione, formazione e supporto mirate e a portata di mano, tra cui la messaggistica con valori mirati per accelerare il buy-in degli utenti

Usare le considerazioni seguenti per valutare la preparazione dell'organizzazione per l'indirizzo di gestione delle modifiche degli utenti.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Si è avuto successo in precedenza con l'adozione di software o servizi da un utente?</li><li>È possibile tenere traccia dell'assorbimento dell'uso?</li><li>Si dispone delle risorse necessarie per progettare e gestire una campagna&mdash;di adozione iniziale&mdash;e continua (sensibilizzazione, formazione e supporto tecnico)?</li><li>Si ha un team di gestione di adozioni/cambiamenti per gli utenti dedicati o si può investire in tali risorse per garantire risultati aziendali?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Se hai risposto &quot;Sì&quot; a tutto quanto sopra indicato, identifica gli stakeholder di gestione degli utenti giusti e inizia la pianificazione della preparazione degli utenti.</li><li>Se non&quot; si &quot;è risposto ad alcuno o a tutto quanto sopra indicato, è consigliabile coinvolgere le risorse esterne per facilitare la guida delle attività correlate alla gestione delle modifiche e alle adozioni per l'organizzazione.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Disponibilità della rete

Teams USA la tecnologia audio e video (codec) che può adattarsi e quindi eseguire in modo migliore in più condizioni di rete. Per garantire prestazioni ottimali e coerenti, è consigliabile preparare la rete per i team.

![Diagramma che descrive i tre componenti della qualità](media/evaluate-my-environment-image1.png "Diagramma che descrive i tre componenti della qualità e in che modo la gestione dei servizi si sovrappone a tutti e tre i componenti. Con lo stato attivo sulla rete.")

## <a name="key-takeaways"></a>Takeaway chiave

Questi sono i principali takeaway di queste linee guida. È necessario:

-   Aprire le porte TCP 80 e 443 in uscita dai client che utilizzeranno teams.

-   Aprire le porte UDP da 3478 a 3481 in uscita dai client che utilizzeranno teams.

-   Verificare di avere larghezza di banda sufficiente per la distribuzione di team.

-   Eseguire lo [strumento di valutazione della rete](https://www.microsoft.com/download/details.aspx?id=53885) e verificare di soddisfare i requisiti descritti in [qualità multimediale e prestazioni della connettività di rete](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) sia dal segmento Edge che dal segmento client.

## <a name="why-should-you-prepare-your-network"></a>Perché preparare la rete?

Prima di esaminare i passaggi da eseguire, è importante capire cosa può influenzare le prestazioni dei team e quindi la felicità e la soddisfazione degli utenti.
Tre aree di rischio principali possono influire sul modo in cui gli utenti percepiscono la qualità della rete:

-   Larghezza di banda insufficiente disponibile

-   Firewall e bloccanti proxy

-   Compromissione della rete, ad esempio jitter e perdita di pacchetti

La procedura descritta di seguito consente di determinare se la distribuzione potrebbe essere interessata da uno di questi fattori e consentirà di procedere verso una risoluzione.
La mancata preparazione della rete consentirà probabilmente a utenti scontenti e a costosi, ad hoc, correzioni. Preparando la rete e l'organizzazione per i team, è possibile aumentare notevolmente le possibilità di successo.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Pianificazione della larghezza di banda

Il primo passaggio verso la disponibilità della rete assicura che la rete disponga di larghezza di banda sufficiente per le modalità che i team forniranno agli utenti. La pianificazione della larghezza di banda sufficiente è un'attività abbastanza semplice e un inizio molto limitato per garantire agli utenti un'esperienza di team di alta qualità.

### <a name="local-internet-egress"></a>Uscita Internet locale

Molte reti sono state progettate per l'uso di una topologia hub e spoke. In questa topologia, il traffico Internet in genere attraversa la rete WAN fino a un centro dati centrale prima che venga emerge (egresses) a Internet. Spesso questa operazione viene eseguita per centralizzare i dispositivi di sicurezza della rete con l'obiettivo di ridurre i costi complessivi.

Il traffico di back-haul attraverso la rete WAN aumenta la latenza e ha un impatto negativo sulla qualità e sull'esperienza utente. Poiché Microsoft teams viene eseguito nella grande rete globale di Microsoft, c'è spesso una posizione di peering di rete vicina all'utente. Un utente probabilmente otterrà prestazioni migliori egressing fuori da un punto Internet locale vicino alla propria posizione e alla rete ottimizzata per la voce il più presto possibile. Per alcuni carichi di lavoro, le richieste DNS vengono usate per inviare il traffico al server front-end più vicino. In questi casi, è importante che quando si usa un punto di uscita locale sia associato alla risoluzione DNS locale.

Per ottimizzare il percorso di rete della rete globale Microsoft, è possibile migliorare le prestazioni e infine garantire l'esperienza migliore per gli utenti. Per altri dettagli, vedere il post di Blog per [ottenere la connettività e le prestazioni migliori in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Le VPN garantiscono un servizio prezioso a molte organizzazioni. Sfortunatamente, in genere non sono progettati o configurati per supportare elementi multimediali in tempo reale. Alcune VPN potrebbero anche non supportare UDP. Le VPN introducono anche un ulteriore livello di crittografia sulla parte superiore del traffico multimediale già crittografato. Inoltre, la connettività al servizio teams potrebbe non essere efficiente a causa del traffico di pinning dei capelli attraverso un dispositivo VPN.
Inoltre, non sono necessariamente progettati da una prospettiva di capacità per soddisfare i carichi previsti necessari per i team.

La raccomandazione consiste nel creare un percorso alternativo che ignori la VPN per il traffico di teams. Questa operazione è comunemente nota come *VPN a tunnel separato*. Split tunneling significa che il traffico per Office 365 non attraverserà la VPN, ma passerà direttamente a Office 365. Questa modifica avrà un impatto positivo sulla qualità, ma offre anche il vantaggio secondario di ridurre il carico dai dispositivi VPN e dalla rete dell'organizzazione.

Per implementare un tunnel suddiviso, consultare il proprio fornitore di VPN per i dettagli della configurazione.

### <a name="wi-fi"></a>Wi-Fi

Come VPN, le reti Wi-Fi non sono necessariamente progettate o configurate per supportare elementi multimediali in tempo reale. La pianificazione o l'ottimizzazione di una rete Wi-Fi per supportare team è una considerazione importante per una distribuzione di alta qualità.

Esistono diversi fattori che entrano in gioco per ottimizzare una rete Wi-Fi:

-   Implementazione di QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale sia di conseguenza prioritario per le reti Wi-Fi.

-   Pianificare e ottimizzare le bande Wi-Fi e il posizionamento dei punti di accesso. L'intervallo di 2,4 GHz può avere un'esperienza adeguata a seconda della posizione del punto di accesso, ma i punti di accesso sono spesso colpiti da altri dispositivi consumer che operano in tale intervallo. La gamma a 5 GHz è più adatta a elementi multimediali in tempo reale a causa della loro gamma densa, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo e essere configurati in base a tali bande.

-   Se vengono distribuite reti Wi-Fi dual-band, è consigliabile implementare lo sterzo della banda. Lo sterzo della banda è una tecnica implementata dai fornitori Wi-Fi per influenzare i client dual-band in modo da usare l'intervallo a 5 GHz.

-   Quando i punti di accesso dello stesso canale sono troppo vicini, possono causare sovrapposizioni di segnali e competere involontariamente, con conseguente esperienza negativa per l'utente. Verificare che i punti di accesso adiacenti si trovino nei canali che non si sovrappongono.

Ogni fornitore wireless ha le proprie raccomandazioni per la distribuzione della soluzione wireless. È consigliabile consultare il fornitore per indicazioni specifiche.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisiti per firewall e proxy

Microsoft teams si connette ai Microsoft Online Services e richiede connettività Internet. Affinché i team funzionino correttamente, è necessario aprire le porte TCP 80 e 443 dai client a Internet e le porte UDP da 3478 a 3481 dai client a Internet. Le porte TCP vengono usate per connettersi a contenuto basato sul Web, ad esempio SharePoint Online, Exchange Online e i servizi di chat di teams.
I plug-in e i connettori si connettono anche su queste porte TCP. Le quattro porte UDP vengono usate per elementi multimediali come l'audio e il video per assicurarne il flusso corretto.

L'apertura di queste porte è essenziale per una distribuzione affidabile di teams. Il blocco di queste porte non è supportato e avrà un effetto sulla qualità dei contenuti multimediali.

Se l'organizzazione richiede di specificare gli intervalli di indirizzi IP esatti e i domini a cui devono essere aperte queste porte, è possibile limitare gli intervalli e i domini IP di destinazione per queste porte. Per un elenco di porte, protocolli e intervalli IP esatti, vedere [URL e intervalli di indirizzi IP di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Se si sceglie di limitare gli intervalli di indirizzi IP di destinazione e i domini, è necessario verificare che l'elenco delle porte e degli intervalli sia aggiornato perché potrebbe cambiare. È possibile sottoscrivere [questo feed RSS per l'](https://go.microsoft.com/fwlink/p/?linkid=236301) aggiornamento quando si verificano le modifiche. È anche buona norma verificare se tutte le porte vengono aperte eseguendo regolarmente lo strumento di [valutazione della rete Skype for business](https://www.microsoft.com/download/details.aspx?id=53885) . Per altre informazioni sulle funzionalità di questo strumento, vedere la sezione successiva.

In caso di distribuzione di un server proxy, è consigliabile ignorare il server proxy per tutti i servizi teams. Anche se l'uso di un proxy potrebbe funzionare, è molto probabile che la qualità venga ridotta a causa del fatto che i contenuti multimediali vengono costretti a usare TCP anziché UDP. Per altre informazioni sui server proxy e l'esclusione, vedere [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Testare la rete

Dopo aver completato la pianificazione e la preparazione della rete, tra cui l'aggiornamento della larghezza di banda e l'apertura delle porte nel firewall, è consigliabile verificare le prestazioni della rete. I risultati di questo test dipingeranno un quadro più chiaro di qualsiasi ottimizzazione o correzione della rete necessaria per l'esito positivo dei servizi di audioconferenza o del sistema telefonico con l'implementazione del piano di chiamata.

È possibile scaricare lo [strumento di valutazione della rete Skype for business](https://www.microsoft.com/download/details.aspx?id=53885) per verificare se la rete è pronta per i team. Lo strumento offre funzionalità duali: può verificare se tutte le porte corrette sono state aperte e può verificare la presenza di problemi di rete.

Dopo aver scaricato e installato lo strumento, è possibile trovarlo in C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool. Una guida dettagliata su come usare lo strumento, Usage. docx, è inclusa in tale directory.

### <a name="test-for-opened-ports"></a>Testare le porte aperte

Aprire una finestra del prompt dei comandi e passare alla directory dello strumento di valutazione della rete immettendo **CD C:\\Program\\Files Microsoft Skype for Business Network Assessment Tool**. Al prompt dei comandi avviare il test per le porte aperte immettendo **networkassessmenttool. exe/connectivitycheck**

Dopo aver eseguito i controlli, lo strumento visualizzerà il messaggio "verifiche completate correttamente" o un report sulle porte bloccate.
Viene inoltre generato un file denominato Connectivity_results. txt, che contiene l'output dello strumento e lo archivia nella directory% UserProfile\\% AppData\\Local\\Microsoft Skype for Business Network Assessment Tool.\\

È consigliabile eseguire regolarmente i controlli di connettività per verificare che le porte siano state aperte e funzionino correttamente.

### <a name="test-for-network-impairments"></a>Testare i problemi di rete

Per aumentare la soddisfazione degli utenti, è consigliabile limitare eventuali danni alla rete.
I problemi di rete più comuni sono ritardo (latenza), perdita di pacchetti e jitter:

-   **Latenza:** Questo è il tempo necessario per ottenere un pacchetto IP dal punto a al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e la velocità della luce, incluso il sovraccarico aggiuntivo adottato dai vari router in mezzo.
    La latenza viene misurata in modo unidirezionale o di andata e ritorno.

-   **Perdita di pacchetti**: spesso viene definita come percentuale di pacchetti persi in una determinata finestra di tempo. La perdita di pacchetti influenza direttamente la qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto sulle perdite di burst di back-to-back che causano il ritaglio completo dell'audio.

-   **Jitter di arrivo tra pacchetti o semplicemente jitter:** Questa è la variazione media di ritardo tra i pacchetti successivi. La maggior parte dei moderni software VoIP, incluso Skype for business, può adattarsi ad alcuni livelli di jitter attraverso il buffering. Solo quando il jitter supera il buffering che un partecipante noterà gli effetti di jitter.

I valori massimi per questi problemi sono descritti in [qualità multimediale e prestazioni della connettività di rete](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Quando si verificano questi problemi, distinguiamo tra due segmenti distinti:

-   Il *segmento Edge* è il segmento in cui risiede il router. Si tratta del segmento di rete logica più vicino connesso a Internet in ogni posizione. Nella maggior parte dei casi, si tratta del punto di connessione del router o eventualmente di una rete perimetrale (nota anche come *DMZ*, *zona demilitarizzata*e *subnet schermata*). Nessun ulteriore traffico che influisce su dispositivi diversi da quelli del router deve avvenire tra questo segmento e Internet.

-   Il *segmento client* è il segmento di rete logica in cui risiedono i client.

È consigliabile testare entrambi i segmenti usando lo strumento di valutazione della rete. Per testare il segmento, passare alla directory e immettere **networkassessmenttool. exe** al prompt dei comandi. I risultati vengono scritti in un file denominato Results. TSV ed è possibile confrontarli con i [requisiti](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) per ogni segmento.

Tieni presente che entrambi i segmenti devono soddisfare i requisiti per una distribuzione di alta qualità. È consigliabile eseguire lo strumento più volte per un'ora direttamente per ottenere una buona indicazione delle prestazioni della rete.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correzione della rete

Se i risultati della pianificazione della larghezza di banda, dei test di porta o di requisiti di rete mostrano che la rete corrente deve essere risolta prima di distribuire Team, è possibile eseguire questa operazione in diversi modi:

-   Per una larghezza di banda insufficiente, le connessioni di aggiornamento in modo che il traffico a Office 365 possa fluire senza ostacoli.

-   Per le porte bloccate, modificare le regole del firewall e riprovare le porte.

-   Per i problemi di rete, eseguire sempre un'analisi causa radice.

La qualità del servizio (QoS) può essere usata per combattere le disabilità privilegiando e separando il traffico. Alcune organizzazioni scelgono di distribuire QoS per superare i problemi di larghezza di banda o limitare la quantità di flusso di traffico. Ciò non migliorerà la qualità e consentirà di creare nuovi problemi. Un'analisi causa radice deve essere sempre eseguita quando i problemi di rete superano i requisiti. QoS può essere una soluzione.
Per altre informazioni, Vedi [qualità del servizio in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>Molte reti si evolvono nel tempo a causa di aggiornamenti, espansioni o altri requisiti aziendali. Verificare di avere a disposizione processi operativi per mantenere queste aree nell'ambito della pianificazione della gestione dei servizi.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Chi sarà responsabile per il completamento delle opportune valutazioni di rete in tutti i segmenti di rete e le posizioni dell'organizzazione?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>È possibile eseguire una valutazione dettagliata della rete per garantire che la rete sia pronta per la distribuzione di Microsoft teams.</li><li>Eseguire il risanamento della rete in base ai risultati della valutazione per ogni segmento di rete.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->