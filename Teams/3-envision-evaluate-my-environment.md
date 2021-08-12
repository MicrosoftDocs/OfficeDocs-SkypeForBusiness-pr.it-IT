---
title: Valutare l'ambiente per i carichi di lavoro vocali nel cloud
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare le persone e l'analisi di rete per valutare la conformità dell'organizzazione, aprire le porte TCP e UDP corrette, eseguire qualsiasi correzione della rete.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2498d634bda4760d34b6d76762312e56ae51efe4ea08a9b42b875ac250759403
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302090"
---
# <a name="evaluate-my-environment"></a>Valutare il proprio ambiente

Questo articolo fornisce una panoramica dei requisiti per valutare correttamente l'ambiente corrente per l'uso dei servizi vocali cloud. Valutando l'ambiente, si identificano i rischi e i requisiti che influiranno sulla distribuzione globale del cloud voice. Identificando questi elementi in anticipo, è possibile modificare la pianificazione in modo da ottenere il successo.

## <a name="introduction-to-evaluating-your-environment"></a>Introduzione alla valutazione dell'ambiente

Per ottenere i risultati chiave obiettivi (OKR), in precedenza sono state prese decisioni chiave relative ai servizi. Il passaggio successivo consiste nell'eseguire l'individuazione dell'ambiente per valutare tutti gli aspetti relativi all'infrastruttura IT e telefonia, alla rete e alle operazioni per verificare che l'organizzazione sia pronta per implementare la soluzione.

L'individuazione dell'ambiente deve includere la valutazione della conformità della rete per garantire che la rete supporti l'implementazione dei servizi di audioconferenza o Sistema telefonico con i servizi del piano per chiamate.

È possibile identificare i rischi tecnici come parte di una valutazione dell'ambiente e della conformità all'adozione e sviluppare un piano di attenuazione per ogni rischio identificato.
È consigliabile incorporare queste informazioni nel registro dei rischi.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Ambiente corrente

Nell'ambito dell'individuazione dell'ambiente, includere tutte le questioni relative all'elaborazione degli utenti finali, ad esempio una valutazione della conformità di PC e dispositivi mobili per supportare audioconferenze e Sistema telefonico con casi d'uso aziendali del piano chiamate, dai requisiti hardware ai requisiti software.

L'individuazione dell'ambiente può anche scoprire se è necessario [trasferire numeri di telefono a Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
In questo modo l'organizzazione modificherà di conseguenza il piano di progetto e preparerà le informazioni necessarie per la portabilità dei numeri. È possibile usare [l'individuazione dell'Microsoft Teams per](environmental-discovery-for-microsoft-teams-rollout.md) eseguire l'individuazione dell'ambiente.

<table>
<tr><td>Titolo</td><td>Descrizione</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Who sarà responsabile del completamento di una valutazione dell'ambiente?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare i risultati della valutazione dell'ambiente.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Funzionalità di valutazione dell'adozione e della gestione delle modifiche

La distribuzione mette a portata di mano una nuova tecnologia, ma i risultati aziendali vengono realizzati solo dopo che gli utenti hanno effettivamente adottato la soluzione come propria. Per garantire un'adozione sostenuta di una nuova soluzione, è necessario concentrare gli sforzi sulla preparazione degli utenti e sulla gestione delle modifiche. Per ottenere risultati ottimali, pianificare la conformità degli utenti come flusso di lavoro parallelo alle attività di preparazione tecnica e incorporare le attività seguenti:

-   **Profilo dell'organizzazione e degli utenti:** Analisi della ricettività dell'organizzazione da modificare oltre all'analisi di casi di utilizzo e persona

-   **Preparazione e preparazione delle risorse:** Creazione di risorse mirate e a vasta portata per la consapevolezza, la formazione e il supporto, tra cui la messaggistica a valore mirato per accelerare il buy-in degli utenti

Usare le considerazioni seguenti per valutare la preparazione dell'organizzazione per la gestione delle modifiche degli utenti.

<table>
<tr><td>Titolo</td><td>Descrizione</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Hai avuto successo con l'adozione di software o servizi da parte degli utenti?</li><li>È possibile tenere traccia dell'utilizzo?</li><li>Si hanno le risorse necessarie per progettare e gestire una campagna di adozione iniziale e continua &mdash; &mdash; (consapevolezza, formazione e supporto)?</li><li>Si ha un team dedicato all'adozione/gestione delle modifiche o si possono investire in queste risorse per garantire i risultati aziendali?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Se si risponde sì a tutte le informazioni precedenti, identificare gli stakeholder di gestione delle modifiche degli utenti e &quot; iniziare la pianificazione della conformità degli &quot; utenti.</li><li>Se si è risposto no ad alcune o a tutte le operazioni precedenti, è consigliabile coinvolgere risorse esterne per agevolare la gestione delle modifiche e le attività correlate &quot; &quot; all'adozione per l'organizzazione.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Conformità alla rete

Teams la tecnologia audio e video (codec) in grado di adattarsi alla maggior parte delle condizioni di rete e quindi di migliorare le prestazioni. Per garantire prestazioni ottimali e coerenti, è consigliabile preparare la rete per Teams.

![Diagramma che descrive i tre componenti della qualità](media/evaluate-my-environment-image1.png "Diagramma che descrive i tre componenti della qualità e il modo in cui la gestione dei servizi si sovrappone a tutti e tre i componenti. Con un focus sulla rete.")

## <a name="key-takeaways"></a>Da asporto chiave

Queste sono le principali indicazioni. È necessario:

-   Aprire le porte TCP 80 e 443 in uscita dai client che useranno Teams.

-   Aprire le porte UDP da 3478 a 3481 in uscita dai client che useranno Teams.

-   Assicurarsi di avere larghezza di banda sufficiente per la distribuzione Teams.

-   Eseguire lo [strumento di valutazione della rete](https://www.microsoft.com/download/details.aspx?id=53885) e assicurarsi di soddisfare i requisiti descritti in Qualità multimediale e prestazioni di connettività di rete sia dal segmento perimetrale che dal segmento client. [](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

## <a name="why-should-you-prepare-your-network"></a>Perché è consigliabile preparare la rete?

Prima di esaminare i passaggi da eseguire, è importante comprendere cosa può influire sulle prestazioni dei Teams e quindi la soddisfazione e la soddisfazione degli utenti.
Tre aree di rischio principali possono influire sul modo in cui gli utenti percepiscono la qualità della rete:

-   Larghezza di banda insufficiente disponibile

-   Firewall e blocchi proxy

-   Problemi di rete, ad esempio instabilità e perdita di pacchetti

La procedura descritta di seguito consente di determinare se la distribuzione potrebbe essere interessata da uno di questi fattori e consente di passare a una risoluzione.
La mancata preparazione della rete porterà probabilmente a utenti insoddisfatti e a costose correzioni ad hoc. Preparando la rete e l'organizzazione per Teams, è possibile aumentare notevolmente le possibilità di successo.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Pianificazione della larghezza di banda

Il primo passaggio verso la conformità della rete consiste nel verificare che la rete abbia una larghezza di banda sufficiente per le modalità Teams fornire agli utenti. La pianificazione di una larghezza di banda sufficiente è un'attività abbastanza semplice e un inizio molto basso per garantire agli utenti un'esperienza Teams qualità elevata.

### <a name="local-internet-egress"></a>Uscita internet locale

Molte reti sono state progettate per l'uso di una topologia hub e spoke. In questa topologia, il traffico Internet attraversa in genere la WAN verso un data center centrale prima che emersa (in uscita) verso Internet. Spesso questa operazione viene eseguita per centralizzare i dispositivi di sicurezza di rete con l'obiettivo di ridurre i costi complessivi.

Il traffico di back-uling nella WAN aumenta la latenza e ha un impatto negativo sulla qualità e sull'esperienza utente. Poiché Microsoft Teams viene eseguito sulla rete globale di grandi dimensioni di Microsoft, spesso esiste una posizione di peering di rete vicina all'utente. È probabile che un utente otterrà prestazioni migliori in uscita da un punto Internet locale vicino alla propria posizione e alla rete ottimizzata per la voce il più presto possibile. Per alcuni carichi di lavoro, le richieste DNS vengono usate per inviare traffico al server front-end più vicino. In questi casi, è importante che quando si usa un punto di uscita locale, sia associato alla risoluzione DNS locale.

L'ottimizzazione del percorso di rete della rete globale di Microsoft migliorerà le prestazioni e in definitiva fornirà agli utenti la migliore esperienza possibile. Per altre informazioni, vedere il post di blog [Ottenere la connettività](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)e le prestazioni ottimali in Office 365 .

### <a name="vpn"></a>VPN

Le VPN forniscono un servizio prezioso a molte organizzazioni. Purtroppo, in genere non sono progettati o configurati per supportare supporti multimediali in tempo reale. Alcune VPN potrebbero anche non supportare UDP. Le VPN introducono anche un livello di crittografia aggiuntivo al traffico multimediale già crittografato. Inoltre, la connettività al servizio Teams potrebbe non essere efficiente a causa del traffico che blocca i capelli attraverso un dispositivo VPN.
Inoltre, non sono necessariamente progettati dal punto di vista della capacità per supportare i carichi previsti che Teams richiederanno.

Si consiglia di fornire un percorso alternativo che bypassi la VPN per Teams traffico. Questa funzionalità è comunemente nota come *VPN a tunnel diviso.* Il tunneling diviso significa che il traffico per Microsoft 365 o Office 365 non attraverserà la VPN, ma andrà direttamente a Microsoft 365 o Office 365. Questa modifica avrà un impatto positivo sulla qualità, ma offre anche il vantaggio secondario di ridurre il carico dai dispositivi VPN e dalla rete dell'organizzazione.

Per implementare un split tunnel, contattare il fornitore della VPN per i dettagli di configurazione.

### <a name="wi-fi"></a>Wi-Fi

Come vpn, le Wi-Fi non sono necessariamente progettate o configurate per supportare supporti multimediali in tempo reale. La pianificazione o l'ottimizzazione di una rete Wi-Fi per supportare Teams è una considerazione importante per una distribuzione di alta qualità.

Esistono diversi fattori che vengono in gioco per ottimizzare una rete Wi-Fi rete:

-   Implementazione di QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale sia in ordine di priorità di conseguenza rispetto alle reti Wi-Fi multimediali.

-   Pianificazione e ottimizzazione delle bande Wi-Fi e del posizionamento del punto di accesso. L'intervallo di 2,4 GHz può offrire un'esperienza adeguata a seconda del posizionamento del punto di accesso, ma i punti di accesso sono spesso interessati da altri dispositivi consumer che operano in tale intervallo. L'intervallo di 5 GHz è più adatto ai supporti multimediali in tempo reale a causa della loro fitta gamma, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo ed essere configurati per sfruttare tali bande di conseguenza.

-   Se vengono distribuite reti Wi-Fi banda doppia, valutare l'implementazione dello sterzo a banda. Lo sterzo a banda è una tecnica implementata dai Wi-Fi per influenzare i client a banda doppia per l'uso dell'intervallo di 5 GHz.

-   Quando i punti di accesso dello stesso canale sono troppo vicini, possono causare la sovrapposizione del segnale e competere involontariamente, causando un'esperienza negativa per l'utente. Assicurarsi che i punti di accesso che si trovano uno accanto all'altro siano su canali che non si sovrappongono.

Ogni fornitore wireless ha le proprie raccomandazioni per l'implementazione della propria soluzione wireless. È consigliabile consultare il fornitore per indicazioni specifiche.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisiti per firewall e proxy

Microsoft Teams si connette a Microsoft Online Services e richiede connettività Internet per questo scopo. Per il corretto funzionamento di Teams, è necessario aprire le porte TCP 80 e 443 dai client a Internet e le porte UDP da 3478 a 3481 dai client a Internet. Le porte TCP vengono usate per connettersi a contenuti basati sul Web, ad esempio SharePoint Online, Exchange Online e ai servizi Teams Chat.
I plug-in e i connettori si connettono anche tramite queste porte TCP. Le quattro porte UDP vengono usate per supporti multimediali come audio e video, per garantire il corretto flusso.

L'apertura di queste porte è essenziale per una distribuzione Teams affidabile. Il blocco di queste porte non è supportato e avrà un effetto sulla qualità dei supporti.

Se l'organizzazione richiede di specificare gli intervalli di indirizzi IP e i domini esatti a cui aprire queste porte, è possibile limitare gli intervalli IP e i domini di destinazione per queste porte. Per un elenco di porte, protocolli e intervalli IP esatti, vedere Microsoft 365 o Office 365 URL e [intervalli di indirizzi IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)
Se si sceglie di limitare gli intervalli di indirizzi IP e i domini di destinazione, è necessario assicurarsi di mantenere aggiornato l'elenco di porte e intervalli perché potrebbero cambiare. È possibile [sottoscrivere questo feed RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) da aggiornare quando si verificano modifiche. È anche consigliabile verificare se tutte le porte [](https://www.microsoft.com/download/details.aspx?id=53885) vengono aperte eseguendo regolarmente lo strumento di valutazione Skype for Business rete. Per altre informazioni sulle funzionalità di questo strumento, vedere la sezione successiva.

In caso di distribuzione di un server proxy, è consigliabile ignorare il server proxy per tutti Teams servizi. Anche se l'uso di un proxy potrebbe funzionare, è molto probabile che la qualità venga ridotta a causa del fatto che i supporti sono costretti a usare TCP invece di UDP. Per altre informazioni sui server proxy e sull'esclusione, vedere Microsoft 365 o Office 365 URL e [intervalli di indirizzi IP.](./office-365-urls-ip-address-ranges.md)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Testare la rete

Dopo aver completato la pianificazione e la preparazione della rete, tra cui l'aggiornamento della larghezza di banda e l'apertura delle porte nel firewall, è consigliabile testare le prestazioni della rete. I risultati di questo test dipingeranno un quadro più chiaro di qualsiasi ottimizzazione di rete o correzione necessaria per il successo delle audioconferenze o dei Sistema telefonico con l'implementazione del piano per le chiamate.

È possibile scaricare lo strumento Skype for Business di valutazione [della rete per](https://www.microsoft.com/download/details.aspx?id=53885) verificare se la rete è pronta per Teams. Lo strumento offre una doppia funzionalità: può verificare se sono state aperte tutte le porte corrette e può testare la possibilità di problemi di rete.

Dopo aver scaricato e installato lo strumento, è possibile trovarlo in C: \\ Programmi Microsoft Skype for Business Network Assessment \\ Tool. In tale directory è inclusa una guida dettagliata per l'Usage.docx dello strumento.

### <a name="test-for-opened-ports"></a>Test per le porte aperte

Aprire una finestra del prompt dei comandi e passare alla directory dello Strumento di valutazione della rete immettendo **cd C: \\ Programmi Microsoft Skype for Business Network Assessment \\ Tool**. Al prompt dei comandi, avviare il test per le porte aperte immettendo **networkassessmenttool.exe /connectivitycheck**

Dopo aver eseguito i controlli, lo strumento visualizza il messaggio "Verifiche completate" o segnala le porte bloccate.
Genera anche un file denominato Connectivity_results.txt, che contiene l'output dello strumento e lo archivia nella directory %userprofile% \\ appdata \\ locale microsoft skype for business network assessment \\ \\ tool.

È consigliabile eseguire regolarmente i controlli di connettività per assicurarsi che le porte siano state aperte e funzionino correttamente.

### <a name="test-for-network-impairments"></a>Test per problemi di rete

Per aumentare la soddisfazione degli utenti, è consigliabile limitare le eventuali disabilità nella rete.
I problemi di rete più comuni sono il ritardo (latenza), la perdita di pacchetti e l'instabilità:

-   **Latenza:** Questo è il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e alla velocità della luce, incluso l'ulteriore sovraccarico dei vari router in mezzo.
    La latenza viene misurata come tempo unidirebile o di andata e ritorno.

-   **Perdita di pacchetti:** spesso si tratta di una percentuale di pacchetti persi in un determinato intervallo di tempo. La perdita di pacchetti influisce direttamente sulla qualità audio, dai piccoli pacchetti persi individuali che non hanno quasi alcun impatto sulle perdite di burst back-to-back che causano il completo taglio dell'audio.

-   **Instabilità di arrivo tra pacchetti o semplicemente instabilità:** Questa è la variazione media del ritardo tra pacchetti successivi. La maggior parte dei software VoIP moderni, inclusi Skype for Business, può adattarsi ad alcuni livelli di instabilità attraverso il buffering. È solo quando l'instabilità supera il buffering che un partecipante noterà gli effetti di instabilità.

I valori massimi per queste disabilità sono descritti in Qualità multimediale e [prestazioni di connettività di rete.](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
Durante i test per queste disabilità, distinguiamo due segmenti distinti:

-   Il *segmento di bordo* è il segmento in cui si trova il router. Si tratta del segmento di rete logico più vicino connesso a Internet in ognuna delle posizioni. Nella maggior parte dei casi si tratta del punto di connessione del router o, eventualmente, di una rete perimetrale (nota anche come *DMZ,* *zona demilitarizzata* e *subnet schermata).* Non dovrebbe verificarsi un ulteriore traffico che interessa dispositivi diversi dal router tra questo segmento e Internet.

-   Il *segmento client è* il segmento di rete logico in cui risiedono i clienti.

È consigliabile testare entrambi i segmenti usando lo strumento di valutazione della rete. Per testare il segmento, passare alla directory e immetterenetworkassessmenttool.exe **al** prompt dei comandi. I risultati vengono scritti in un file denominato Results.tsv ed è possibile confrontarli con i [requisiti](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) per ogni segmento.

Si noti che entrambi i segmenti devono soddisfare i requisiti per una distribuzione di alta qualità. È consigliabile eseguire lo strumento più volte per un'ora di fila per ottenere una buona indicazione delle prestazioni della rete.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Correzione della rete

Se i risultati della pianificazione della larghezza di banda, dei test delle porte o dei test dei requisiti di rete indicano che è necessario correggere la rete corrente prima di distribuire Teams, è possibile eseguire questa operazione in diversi modi:

-   Per una larghezza di banda insufficiente, aggiornare le connessioni in modo che il traffico verso Microsoft 365 o Office 365 possa fluire senza problemi.

-   Per le porte bloccate, modificare le regole del firewall e rieseguire il test delle porte.

-   Per problemi di rete, eseguire sempre un'analisi delle cause radice.

La qualità del servizio (QoS) può essere usata per combattere le disabilità assegnando priorità e separando il traffico. Alcune organizzazioni scelgono di distribuire QoS per superare i problemi di larghezza di banda o limitare la quantità di traffico che scorre. Questo non migliorerà la qualità e porterà a nuovi problemi. Un'analisi delle cause radice deve sempre essere eseguita quando le disabilità di rete superano i requisiti. QoS può essere una soluzione.
Per altre informazioni, vedere [Qualità del servizio in Microsoft Teams](./qos-in-teams.md).

>[!NOTE]
>Molte reti si evolvono nel tempo a causa di aggiornamenti, espansione o altri requisiti aziendali. Assicurarsi che siano stati eserciti processi operativi per mantenere queste aree nell'ambito della pianificazione della gestione dei servizi.


<table>
<tr><td>Titolo</td><td>Descrizione</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Who sarà responsabile del completamento di valutazioni di rete appropriate in tutti i segmenti di rete e le posizioni dell'organizzazione?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>È possibile eseguire una valutazione dettagliata della rete per assicurarsi che la rete sia pronta per la Microsoft Teams distribuzione.</li><li>Eseguire la correzione della rete in base ai risultati della valutazione per ogni segmento di rete.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->