---
title: Pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Informazioni sul controllo dell'ammissione alle chiamate, che può impedire che le chiamate avvengano se hanno una qualità media scadente, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3942c3d50267593f393655e19d0cc80b5f5028f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187775"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server

Informazioni sul controllo dell'ammissione alle chiamate, che può impedire che le chiamate avvengano se hanno una qualità media scadente, in Skype for Business Server VoIP aziendale.

Per le applicazioni basate su IP, come la telefonia, il video e la condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non viene in genere considerata un fattore limitante all'interno di ambienti LAN. Tuttavia, nei collegamenti WAN che interconnettono i siti, la larghezza di banda della rete può essere limitata.

Quando il traffico di rete esegue l'oversubscription di un collegamento WAN, per risolvere la congestione vengono usati meccanismi correnti come l'accodamento, il buffer e l'eliminazione dei pacchetti. Il traffico aggiuntivo viene in genere ritardato finché la congestione della rete non si semplifica o, se necessario, il traffico viene eliminato. Per il traffico dati convenzionale in tali situazioni, il client ricevente può recuperare. Tuttavia, per il traffico in tempo reale, ad esempio le comunicazioni unificate, la congestione della rete non può essere risolta in questo modo, perché il traffico delle comunicazioni unificate è sensibile sia alla latenza che alla perdita di pacchetti. La congestione della rete WAN può causare una scarsa qualità dell'esperienza (QoE) per gli utenti. Per il traffico in tempo reale in condizioni congestionate, è preferibile negare le chiamate piuttosto che ottenere connessioni con qualità scadente.

Il controllo di ammissione di chiamata (CAC) determina se la larghezza di banda della rete è sufficiente per stabilire una sessione in tempo reale di qualità accettabile. In Skype for Business Server, CAC controlla il traffico in tempo reale solo per l'audio e il video, ma non influenza il traffico dei dati. Se il percorso WAN predefinito non ha la larghezza di banda necessaria, il CAC può provare a instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network).

Questa sezione descrive la funzionalità controllo ammissione chiamata e spiega come pianificare il comando CAC.

> [!NOTE]
> Skype for Business Server include tre funzionalità vocali avanzate: controllo di ammissione delle chiamate (CAC), servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni sulla pianificazione comuni a tutte e tre queste caratteristiche, vedere [impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server](network-settings-for-advanced-features.md).

La progettazione CAC in Skype for Business Server offre quattro attributi principali:

- È semplice eseguire la distribuzione e la gestione senza richiedere ulteriori dispositivi, ad esempio router appositamente configurati.

- Risolve i casi di utilizzo delle comunicazioni unificate critiche, ad esempio utenti mobili e più punti di presenza. I criteri di CAC vengono applicati in base al punto in cui si trova l'endpoint, non in cui è ospitato l'utente.

- Oltre alle chiamate vocali, può essere applicato ad altri traffici, ad esempio videochiamate e sessioni di conferenze audio/video.

- Offre la flessibilità necessaria per consentire la rappresentazione di vari tipi di topologie di rete.

Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) viene reinstradata alla rete PSTN.

CAC controlla il traffico in tempo reale solo per voce e video. Non controlla il traffico dati.

Gli amministratori definiscono i criteri di CAC, applicati dal servizio dei criteri di larghezza di banda installato con ogni pool Front-end. Le impostazioni di CAC vengono propagate automaticamente a tutti i server front-end di Skype for Business Server nella rete.

Per le chiamate che non riescono a causa di criteri di CAC, l'ordine di precedenza per il reinstradamento della chiamata è il seguente:

1. Internet

2. PSTN

3. Segreteria telefonica

La registrazione dei dettagli delle chiamate (CDR) acquisisce informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica. CDR non acquisisce informazioni sulle chiamate reinstradate a Internet, poiché Internet viene considerato come percorso alternativo anziché come opzione secondaria.

> [!NOTE]
> I depositi della segreteria telefonica non verranno negati a causa di vincoli di larghezza di banda.

Il servizio criteri di larghezza di banda genera due tipi di file di log in formato CSV (comma separated values). Il file di log degli **errori di controllo** acquisisce informazioni quando le richieste di larghezza di banda vengono negate. Il file di log di **utilizzo del collegamento** acquisisce uno snapshot della topologia di rete e dell'utilizzo della larghezza di banda dei collegamenti WAN. Entrambi i file di log possono aiutarti a ottimizzare i criteri di CAC in base all'utilizzo.

## <a name="call-admission-control-considerations"></a>Considerazioni sul controllo dell'ammissione alle chiamate

L'amministratore seleziona per installare il servizio criteri di larghezza di banda nel primo pool configurato nel sito centrale. Poiché esiste un unico sito centrale per ogni area di rete, esiste un solo servizio per i criteri di larghezza di banda per ogni area di rete, che gestisce i criteri di larghezza di banda per l'area geografica, i siti associati e i collegamenti a tali siti. Il servizio criteri di larghezza di banda viene eseguito come parte dei server front-end e quindi la disponibilità elevata è incorporata all'interno di tale pool. Il servizio criteri di larghezza di banda eseguito in ogni server front-end viene sincronizzato ogni 15 secondi. Se il pool Front-end non riesce, i criteri di CAC non vengono più applicati per il sito fino al pool Front-end e di conseguenza il servizio dei criteri di larghezza di banda diventa operativo. Questo implica che tutte le chiamate verranno effettuate per tutta la durata del servizio per i criteri di larghezza di banda fuori servizio. È quindi possibile che l'oversubscription della larghezza di banda dei collegamenti durante questo periodo

Il servizio criteri di larghezza di banda offre una disponibilità elevata all'interno di un pool Front End; Tuttavia, non offre ridondanza nei pool Front-end. Il servizio criteri di larghezza di banda non può eseguire il failover da un pool Front-end a un altro. Una volta ripristinato il servizio al pool Front-End, il servizio criteri di larghezza di banda viene ripreso e può applicare di nuovo i controlli dei criteri di larghezza di banda.

### <a name="network-considerations"></a>Considerazioni sulla rete

Anche se la restrizione della larghezza di banda per l'audio e il video viene applicata dal servizio criteri di larghezza di banda in Skype for Business Server, questa restrizione non viene applicata al router di rete (Layer 2 e 3). Il CAC non può impedire a un'applicazione dati, ad esempio, di consumare l'intera larghezza di banda della rete su un collegamento WAN, inclusa la larghezza di banda riservata per l'audio e il video in base ai criteri di CAC. Per proteggere la larghezza di banda necessaria nella rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio servizi differenziati (DiffServ). Una procedura consigliata consiste quindi nel coordinare i criteri di larghezza di banda CAC definiti con le impostazioni QoS eventualmente distribuite.

### <a name="media-and-signaling-paths-over-vpn"></a>Percorsi multimediali e di segnalazione su VPN

Se l'organizzazione supporta i contenuti multimediali tramite VPN, verificare che sia il flusso multimediale che il flusso di segnalazione passano attraverso la rete VPN oppure vengono instradati attraverso Internet. Per impostazione predefinita, i flussi di elementi multimediali e di segnalazione passano attraverso il tunnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Controllo dell'ammissione delle chiamate degli utenti esterni

Il controllo dell'ammissione alle chiamate non viene applicato oltre i limiti dell'organizzazione di Skype for Business Server. Non è possibile applicare CAC al traffico multimediale che attraversa Internet, che non è gestito da Skype for Business Server. I controlli CAC verranno eseguiti nella parte della chiamata che passa attraverso la rete aziendale se l'endpoint chiamato appartiene all'organizzazione e il server perimetrale è stato aggiunto alla configurazione di rete, come descritto in [controllo di ammissione di chiamata distribuzione: elenco di controllo finale per Skype for Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Se l'endpoint chiamato non appartiene all'organizzazione, ad esempio un utente federato o PIC, non vengono eseguiti controlli dei criteri di larghezza di banda e la chiamata in uscita ignorerà le eventuali restrizioni di CAC.

### <a name="call-admission-control-of-pstn-connections"></a>Controllo ammissione chiamata delle connessioni PSTN

Il controllo di ammissione delle chiamate è impostabile sul server Mediation indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP. Poiché il Mediation Server è un agente utente back-to-back (B2BUA), termina media. Ha due lati di connessione: un lato connesso a Skype for Business Server e un lato del gateway, che è connesso a gateway PSTN, IP/PBX o trunk SIP. Per informazioni dettagliate sulle connessioni PSTN, vedere [pianificare la connettività PSTN in Skype for Business Server](pstn-connectivity-0.md).

CAC può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale. Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, bensì fluisce direttamente tra il client Skype for business e il gateway. In questo caso, CAC non è necessario. Per informazioni dettagliate, vedere [pianificare il bypass multimediale in Skype for business](media-bypass.md).

Nella figura seguente viene illustrato il modo in cui CAC viene applicato alle connessioni PSTN con e senza bypass multimediale abilitato.

**Applicazione controllo ammissione chiamata sulle connessioni alla rete PSTN**

![Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definizione dei requisiti per il controllo dell'ammissione alle chiamate

Pianificazione per il controllo di ammissione alle chiamate (CAC) richiede informazioni dettagliate sulla topologia di rete aziendale. Per pianificare i criteri di controllo dell'ammissione alle chiamate, eseguire le operazioni seguenti.

1. Identificare gli hub/backbone (chiamati aree di rete) all'interno della rete aziendale.

2. Identificare gli uffici o le posizioni (detti siti di rete) all'interno di ogni area di rete.

3. Determinare la route di rete tra ogni coppia di aree della rete.

4. Determinare i limiti di larghezza di banda per ogni collegamento WAN.

    > [!NOTE]
    > I limiti di larghezza di banda si riferiscono alla quantità di larghezza di banda di un collegamento WAN assegnata al traffico VoIP aziendale e audio/video. Quando un collegamento WAN viene descritto come "vincolato alla larghezza di banda", il collegamento WAN ha un limite di larghezza di banda inferiore al traffico di picco previsto sul collegamento.

5. Identificare le subnet IP assegnate a ogni sito di rete.

Per spiegare questi concetti, useremo la topologia di rete di esempio mostrata nella figura seguente.

**Topologia di esempio per il controllo dell'ammissione alle chiamate**

![Esempio di topologia di rete di Litware S.p.A.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Tutti i siti di rete sono associati a un'area di rete. Ad esempio, Portland, Reno e Albuquerque sono inclusi nell'area Nord America. In questa figura sono mostrati solo i collegamenti WAN con i criteri di CAC, con limiti di larghezza di banda. I siti di rete di Chicago, New York e Detroit sono visualizzati all'interno dell'area geografica Nord America, perché non sono vincolati alla larghezza di banda e quindi non richiedono criteri di CAC.

I componenti della topologia di esempio sono descritti nelle sezioni seguenti. Per informazioni dettagliate sulla pianificazione della topologia, inclusi i limiti di larghezza di banda, vedere [esempio: raccolta dei requisiti per il controllo dell'ammissione delle chiamate in Skype for Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identificare le aree di rete

Un'area di rete rappresenta un backbone di rete o un hub di rete.

Un backbone o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette diverse parti della rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Una backbone può legare insieme diverse reti da una piccola posizione a un'area geografica ampia. La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti che si connettono.

La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC. Un'area di rete contiene una raccolta di siti di rete (vedere la definizione dei siti di rete più avanti in questo argomento). Collaborare con il team delle operazioni di rete per identificare le aree di rete.

### <a name="associating-a-central-site-with-each-network-region"></a>Associazione di un sito centrale a ogni area di rete

Il CAC richiede che sia definito un sito centrale di Skype for Business Server per ogni area di rete. Il sito centrale è selezionato con la connettività di rete migliore e la larghezza di banda più alta per tutti gli altri siti all'interno dell'area di rete. L'esempio precedente della topologia di rete mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni di CAC. Nell'esempio precedente l'associazione appropriata è illustrata nella tabella seguente.

> [!NOTE]
> I siti centrali non corrispondono necessariamente ai siti di rete. Negli esempi di questa documentazione, alcuni siti centrali, ovvero Chicago, Londra e Pechino, condividono lo stesso nome dei siti di rete. Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Skype for Business Server, mentre il sito di rete fa parte della rete complessiva in cui risiede la topologia di Skype for Business Server.

**Aree di rete, siti centrali e siti di rete**

|**Area di rete**|**Sito centrale**|**Siti di rete**|
|:-----|:-----|:-----|
|America del Nord  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londra  <br/> |Londra  <br/> Colonia  <br/> |
|APAC  <br/> |Pechino  <br/> |Pechino  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identificare i siti di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio uffici, un set di edifici o un campus. Un luogo fisico con una LAN e una connettività WAN ad altri siti è considerato un sito di rete. Iniziare a inventariare tutti gli uffici dell'organizzazione. Nella topologia di esempio l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

È necessario associare ogni sito di rete a un'area di rete. A seconda che il sito di rete disponga di un collegamento WAN vincolato, un criterio di larghezza di banda è associato al sito di rete. Per informazioni dettagliate sui criteri di CAC e sulla larghezza di banda allocata usandoli, vedere "definire i criteri di larghezza di banda" più avanti in questo argomento. Per configurare CAC, è possibile associare i siti di rete alle aree di rete e quindi creare criteri di assegnazione della larghezza di banda da applicare alle connessioni con vincoli di larghezza di banda tra un sito o un'area geografica specifica e le connessioni WAN tra i siti e le aree geografiche.

### <a name="identify-network-links"></a>Identificare i collegamenti di rete

I collegamenti di rete rappresentano connessioni alla WAN fisica che collega aree e siti diversi. Nella topologia di esempio ci sono due collegamenti di rete regionali, cinque collegamenti di rete tra aree geografiche e siti e un collegamento di rete tra due siti.

I due collegamenti internazionali si trovano tra Nord America e EMEA, rappresentati come NA-EMEA-LINK e tra APAC e EMEA, rappresentati come EMEA-APAC-LINK.

I collegamenti ai siti sono indicati dalle linee che collegano Portland, Reno e Albuquerque all'area Nord America, Manila alla regione APAC e Colonia nell'area EMEA. La linea tra Reno e Albuquerque Mostra un collegamento di rete diretta tra questi due siti.

### <a name="define-bandwidth-policies"></a>Definire i criteri di larghezza di banda

Collaborare con il team operazioni di rete per determinare la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale nei collegamenti WAN dell'organizzazione. I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'utilizzo della larghezza di banda è vincolato; Se si prevede che la larghezza di banda può essere allocata per le modalità audio e video.

I criteri di larghezza di banda CAC definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale. Dato che CAC non limita la larghezza di banda di un altro traffico, non può impedire l'uso di tutta la larghezza di banda della rete, ad esempio un trasferimento di file di grandi dimensioni, lo streaming di musica.

I criteri di larghezza di banda CAC possono definire uno o tutti gli elementi seguenti:

- Larghezza di banda totale massima allocata per l'audio.

- Larghezza di banda totale massima allocata per il video.

- Larghezza di banda massima allocata per una singola chiamata audio (sessione).

- Larghezza di banda massima allocata per una singola chiamata video (sessione).

> [!NOTE]
> Tutti i valori di larghezza di banda ** CAC rappresentano i limiti massimi di larghezza di banda unidirezionali.

> [!NOTE]
> Le caratteristiche dei criteri vocali di Skype for Business Server consentono di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita inserite dall'utente). Dopo la creazione della sessione, il consumo di larghezza di banda verrà contabilizzato in modo accurato. Questa impostazione deve essere usata con parsimonia. Per informazioni dettagliate, vedere [creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) o [modificare un criterio vocale e configurare i record di utilizzo PSTN](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) nella documentazione relativa alla distribuzione.

Per ottimizzare l'utilizzo della larghezza di banda per ogni singola sessione, prendere in considerazione il tipo di codec audio e video che verranno usati. In particolare, evitare di allocare larghezza di banda insufficiente per un codec che si prevede di usare di frequente. Se invece si vuole impedire l'uso di un codec che richiede più larghezza di banda, è consigliabile impostare la larghezza di banda massima per ogni sessione abbastanza bassa da scoraggiare tale utilizzo. Per l'audio, non tutti i codec sono disponibili per ogni scenario. Ad esempio:

- Le chiamate audio peer-to-peer tra endpoint Skype for Business useranno RTAudio (8kHz) o RTAudio (16kHz) quando si fattorizza la larghezza di banda e la priorità dei codec.

- Le chiamate in conferenza tra endpoint Skype for business e il servizio di conferenza A/V utilizzeranno G. 722 o Siren.

- Le chiamate alla rete PSTN (Public Switched Telephone Network) in o da endpoint Skype for Business useranno G. 711 o RTAudio (8kHz).

Usare la tabella seguente per ottimizzare le impostazioni di larghezza di banda massima per sessione.

**Utilizzo della larghezza di banda per codec**

|**Codec**|**Requisito della larghezza di banda senza correzione degli errori in avanti (FEC)**|**Requisito della larghezza di banda con la correzione degli errori in avanti (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49,8 Kbps  <br/> |61,6 Kbps  <br/> |
|RTAudio (16kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Sirena  <br/> |57,6 Kbps  <br/> |73,6 Kbps  <br/> |
|G. 711  <br/> |102 Kbps  <br/> |166 kbps  <br/> |
|G. 722  <br/> |105,6 Kbps  <br/> |169,6 Kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 Kbps  <br/> |Non applicabile  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 Kbps  <br/> |Non applicabile  <br/> |

> [!NOTE]
> I requisiti di larghezza di banda prendono in considerazione i costi seguenti: Ethernet II, IP, User Datagram Protocol (UDP), RTP (protocollo di trasporto in tempo reale) e SRTP (Secure Real-Time Transport Protocol). Includono inoltre 10 Kbps per l'overhead di RTCP.

I codec G. 722.1 e Siren sono simili, ma offrono diversi bitrate.

G. 722, il codec predefinito per le conferenze di Skype for Business Server, è completamente diverso dai codec G. 722.1 e Siren.

Il codec Siren viene usato in Skype for Business Server nelle situazioni seguenti:

- Se i criteri di larghezza di banda sono impostati troppo bassi per l'uso di G. 722.

- Se un client di Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio di conferenza telefonica di Skype for Business Server (poiché tali client non supportano il codec G. 722).

**Utilizzo della larghezza di banda per scenario**

|**Scenario**|**Requisito di larghezza di banda ottimizzato per quantità (Kbps)**|**Requisito della larghezza di banda per la modalità bilanciata (Kbps)**|**Requisiti di larghezza di banda ottimizzati per la qualità (Kbps)**|
|:-----|:-----|:-----|:-----|
|Chiamate audio peer-to-peer  <br/> |45 Kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Chiamate in conferenza  <br/> |53 Kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Chiamate PSTN (tra Skype for business e gateway PSTN, con il bypass multimediale)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chiamate PSTN (tra Skype for business e Mediation Server, senza bypass multimediale)  <br/> |45 Kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chiamate PSTN (tra Mediation Server e gateway PSTN, senza bypass multimediale)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype for business-chiamate Polycom  <br/> |101 kbps  <br/> |101 kbps  <br/> |101 kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete, è necessario collaborare con l'amministratore di rete per determinare quali subnet IP vengono assegnate a ogni sito di rete. Se l'amministratore di rete ha già organizzato le subnet IP nelle aree di rete e nei siti di rete, il lavoro è semplificato in modo significativo.

In questo esempio, nel sito di New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supponiamo che Roberto, che lavora in genere a Detroit, viaggi nell'ufficio di New York per la formazione. Quando accende il computer e si connette alla rete, il computer riceverà un indirizzo IP in uno dei quattro intervalli riservati a New York, ad esempio 172.29.80.103.

> [!CAUTION]
> Le subnet IP specificate durante la configurazione di rete nel server devono corrispondere al formato fornito dai computer client per poter essere usate correttamente per il bypass multimediale. Un client Skype for business prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Quando si determina l'ID di bypass associato a ogni client, il registrar confronterà l'elenco delle subnet IP associate a ogni sito di rete rispetto alla subnet fornita dal client per una corrispondenza esatta. Per questo motivo, è importante che le subnet immesse durante la configurazione di rete sul server siano subnet effettive anziché sottoreti virtuali. Se si distribuisce il controllo di ammissione alle chiamate, ma non il bypass multimediale, il controllo di ammissione delle chiamate funzionerà correttamente anche se si configurano sottoreti virtuali. Ad esempio, se un client accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, Skype for business richiederà l'ID di bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, il registrar non considererà questa corrispondenza perché il registrar Cerca specificamente la subnet 172.29.81.0. Di conseguenza, è importante che l'amministratore immetta le subnet esattamente come previsto dai client Skype for business (che vengono provisionati con le subnet durante la configurazione di rete in modo statico o tramite DHCP).

## <a name="best-practices-for-call-admission-control"></a>Procedure consigliate per il controllo di ammissione di chiamata

Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il controllo di ammissione di chiamata:

- Assicurarsi che le WAN vengano adeguatamente provisionate per il traffico multimediale corrente e previsto.

    > [!NOTE]
    > Ti consigliamo di fattorizzare i limiti della larghezza di banda in un buffer. Esistono scenari come le condizioni di competizione che influiscono sulla larghezza di banda totale usata e possono causare situazioni in cui viene superato il limite di larghezza di banda. Ad esempio, se due chiamate provano a iniziare mentre il traffico multimediale si avvicina a un limite di larghezza di banda, uno di essi potrebbe essere negato perché l'altro è riuscito a iniziare per primo.

- Monitorare l'uso della rete e i record dei dettagli delle chiamate per scegliere le impostazioni di CAC ottimali e aggiornare le impostazioni di CAC come modifiche all'utilizzo della rete.

- Usare i criteri di larghezza di banda CAC per completare le impostazioni QoS.

- Se si vuole reinstradare le chiamate bloccate sulla rete PSTN, verificare la funzionalità e la capacità PSTN. Per informazioni dettagliate, vedere [pianificazione del routing delle chiamate in uscita](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > La capacità si riferisce al numero di porte che è necessario aprire per supportare l'eventuale reindirizzamento PSTN.


