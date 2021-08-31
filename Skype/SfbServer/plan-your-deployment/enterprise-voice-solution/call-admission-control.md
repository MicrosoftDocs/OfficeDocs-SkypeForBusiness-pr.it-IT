---
title: Pianificare il controllo di ammissione di chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Informazioni sul controllo di ammissione di chiamata, che può impedire l'accesso alle chiamate se hanno una qualità multimediale scarsa, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b57d9f4d6a26acb33b03ab1befb9132ffebc9a20
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725965"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Pianificare il controllo di ammissione di chiamata in Skype for Business Server

Informazioni sul controllo di ammissione di chiamata, che può impedire l'accesso alle chiamate se hanno una qualità multimediale scarsa, in Skype for Business Server VoIP aziendale.

Per le applicazioni basate su IP, ad esempio telefonia, video e condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non è generalmente considerata un fattore limitante negli ambienti LAN. Nei collegamenti WAN tra i siti tuttavia la larghezza di banda della rete può essere limitata.

Quando il traffico di rete esegue l'oversubscription di un collegamento WAN, vengono utilizzati meccanismi correnti come accodamento, buffering e eliminazione di pacchetti per risolvere la congestione. Il traffico in eccesso in genere viene ritardato finché non si risolve la congestione di rete o, se necessario, finché non viene eliminato il traffico. Per il traffico di dati convenzionali, in questi casi è possibile ripristinare il client di ricezione. Tuttavia, per il traffico in tempo reale, ad esempio le comunicazioni unificate, la congestione di rete non può essere risolta in questo modo, perché il traffico delle comunicazioni unificate è sensibile sia alla latenza che alla perdita di pacchetti. La congestione nella WAN può determinare una qualità percepita dagli utenti (QoE) scadente. Per il traffico in tempo reale in condizioni congestionate, è in realtà meglio negare le chiamate piuttosto che fornire connessioni di qualità scarsa.

Il Servizio Controllo di ammissione di chiamata determina se è disponibile una larghezza di banda di rete sufficiente per stabilire una sessione in tempo reale di qualità accettabile. In Skype for Business Server controllo di ammissione di chiamata controlla il traffico in tempo reale solo per audio e video, ma non influisce sul traffico dati. Se il percorso WAN predefinito non dispone della larghezza di banda necessaria, il servizio Controllo di ammissione di chiamata può tentare di instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network).

In questa sezione viene descritta la funzionalità di Controllo di ammissione di chiamata e viene illustrata la relativa pianificazione.

> [!NOTE]
> Skype for Business Server dispone di tre funzionalità VoIP aziendale avanzate: controllo di ammissione di chiamata, servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni di pianificazione comuni a tutte e tre queste funzionalità, vedere Impostazioni di rete per le funzionalità VoIP aziendale avanzate [in Skype for Business Server](network-settings-for-advanced-features.md).

La progettazione del controllo di ammissione di Skype for Business Server offre quattro attributi principali:

- È semplice da distribuire e gestire senza richiedere apparecchiature aggiuntive, ad esempio router configurati in modo speciale.

- Consente di risolvere casi critici di utilizzo delle comunicazioni unificate, ad esempio relativi a utenti mobili e a più punti di presenza. I criteri di controllo di ammissione di chiamata vengono applicati in base alla posizione dell'endpoint e non a quella in cui risiede l'utente.

- Oltre alle chiamate vocali, può essere applicato ad altro traffico, ad esempio alle videochiamate e alle sessioni di conferenza audio/video.

- Offre la flessibilità necessaria per consentire la rappresentazione di diversi tipi di topologie di rete.

Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata (solo per le chiamate telefoniche) o reinstradata alla rete PSTN.

Il controllo di ammissione di chiamata controlla solo il traffico audio e video in tempo reale, ma non il traffico di dati.

Gli amministratori definiscono i criteri di controllo di ammissione di chiamata, che vengono applicati dal servizio criteri larghezza di banda installato con ogni pool Front End. Le impostazioni del controllo di ammissione di chiamata vengono propagate automaticamente a Skype for Business Server Front End Server nella rete.

Per le chiamate non riuscite a causa di criteri di controllo di ammissione di chiamata, l'ordine di precedenza per il rerouting della chiamata è il seguente:

1. Internet

2. PSTN

3. Segreteria telefonica

Tramite la registrazione dettagli chiamata (CDR) vengono acquisite informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica. CDR non consente l'acquisizione di informazioni sulle chiamate reinstradate a Internet, perché Internet viene considerato un percorso alternativo anziché un'opzione secondaria.

> [!NOTE]
> L'archiviazione nella segreteria telefonica non viene negata a causa di vincoli di larghezza di banda.

Il servizio criteri di larghezza di banda genera due tipi di file di registro in formato con valori separati da virgole (CSV). Nel file di registro degli **errori di verifica** vengono acquisite informazioni quando vengono negate richieste di larghezza di banda. Nel file di registro dell'**utilizzo dei collegamenti** viene acquisita un'istantanea dell'utilizzo della larghezza di banda della topologia di rete e del collegamento WAN. Entrambi questi file di registro possono semplificare l'ottimizzazione dei criteri di controllo di ammissione di chiamata in base all'utilizzo.

## <a name="call-admission-control-considerations"></a>Considerazioni relative al controllo di ammissione di chiamata

L'amministratore sceglie di installare il servizio criteri larghezza di banda nel primo pool configurato nel sito centrale. Poiché esiste un singolo sito centrale per area di rete, esiste un solo servizio criteri di larghezza di banda per ogni area di rete, che gestisce i criteri di larghezza di banda per l'area, i siti associati e i collegamenti a tali siti. Il servizio criteri larghezza di banda viene eseguito come parte dei Front End Server e pertanto la disponibilità elevata è incorporata all'interno del pool. Il servizio criteri larghezza di banda in esecuzione in ogni Front End Server viene sincronizzato ogni 15 secondi. Se il pool Front End ha esito negativo, i criteri di controllo di ammissione di chiamata non vengono più applicati per il sito fino a quando il pool Front End non diventa di nuovo operativo. Ciò implica che tutte le chiamate verranno effettuate per la durata del servizio dei criteri di larghezza di banda fuori servizio. Di conseguenza, esiste la possibilità di un oversubscription della larghezza di banda dei collegamenti durante questo periodo

Il servizio criteri larghezza di banda offre disponibilità elevata all'interno di un pool Front End. tuttavia, non fornisce ridondanza tra i pool Front End. Il servizio Criteri di larghezza di banda non può eseguire il failover da un pool Front End a un altro. Una volta ripristinato il servizio nel pool Front End, il servizio criteri larghezza di banda viene ripreso e può applicare di nuovo i controlli dei criteri di larghezza di banda.

### <a name="network-considerations"></a>Considerazioni sulla rete

Sebbene la limitazione della larghezza di banda per audio e video sia applicata dal servizio criteri di larghezza di banda in Skype for Business Server, questa restrizione non viene applicata al router di rete (livello 2 e 3). Il controllo di ammissione di chiamata non può impedire a un'applicazione dati, ad esempio, di utilizzare l'intera larghezza di banda di rete su un collegamento WAN, inclusa la larghezza di banda riservata per audio e video dal criterio CAC. Per proteggere la larghezza di banda necessaria nella rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio Servizi differenziati (DiffServ). Di conseguenza, una procedura consigliata consiste nel coordinare i criteri di larghezza di banda del controllo di ammissione di chiamata definiti con le eventuali impostazioni QoS che è possibile distribuire.

### <a name="media-and-signaling-paths-over-vpn"></a>Percorsi di contenuti multimediali e segnali su VPN

Se l'organizzazione supporta contenuto multimediale tramite VPN, verificare che il flusso multimediale e il flusso dei segnali attraversino la rete VPN o che venga eseguito il routing di entrambi tramite internet. Per impostazione predefinita, i flussi multimediali e dei segnali passano attraverso il tunnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Controllo di ammissione di chiamata di utenti esterni

Il controllo di ammissione di chiamata non viene applicato oltre i limiti dell'organizzazione Skype for Business Server chiamata. Il controllo di ammissione di chiamata non può essere applicato al traffico multimediale che attraversa Internet, che non è gestito da Skype for Business Server. I controlli CAC verranno eseguiti sulla parte della chiamata che attraversa la rete aziendale se l'endpoint chiamato appartiene all'organizzazione e il server perimetrale è stato aggiunto alla configurazione di rete, come descritto in Distribuzione del controllo di ammissione di [chiamata:](../../deploy/deploy-enterprise-voice/final-checklist.md)elenco di controllo finale per Skype for Business Server . Se l'endpoint chiamato non appartiene all'organizzazione, ad esempio un utente federato o PIC, non vengono eseguiti controlli dei criteri di larghezza di banda e la chiamata in uscita ignorerà eventuali restrizioni del controllo di ammissione di chiamata.

### <a name="call-admission-control-of-pstn-connections"></a>Controllo di ammissione di chiamata di connessioni PSTN

Il controllo di ammissione di chiamata è applicabile nel Mediation Server indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP. Poiché Mediation Server è un agente utente back-to-back (B2BUA), termina i supporti. Ha due lati di connessione: un lato connesso a Skype for Business Server e un lato gateway, connesso a gateway PSTN, IP/PBX o trunk SIP. Per informazioni dettagliate sulle connessioni PSTN, vedere [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

Il controllo di ammissione di chiamata può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale. Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, ma passa direttamente tra il client Skype for Business e il gateway. In questo caso, il controllo di ammissione di chiamata non è necessario. Per informazioni dettagliate, vedere [Plan for media bypass in Skype for Business](media-bypass.md).

Nella figura seguente viene illustrata l'applicazione di controllo di ammissione di chiamata in connessioni PSTN con o senza il bypass multimediale abilitato.

**Applicazione del controllo di ammissione di chiamata in connessioni alla rete PSTN**

![Applicazione della connessione bypass multimediale del controllo di ammissione di chiamata vocale.](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Definizione dei requisiti per il controllo di ammissione di chiamata

La pianificazione del controllo di ammissione di chiamata (CAC, Call Admission Control) richiede informazioni dettagliate sulla topologia di rete aziendale. Per pianificare più agevolmente i criteri di controllo di ammissione di chiamata, eseguire la procedura seguente.

1. Identificare gli hub/backbone (noti come aree di rete) nella rete aziendale.

2. Identificare gli uffici o le sedi (noti come siti di rete) in ogni area di rete.

3. Stabilire la route di rete tra ogni coppia di aree di rete.

4. Determinare i limiti di larghezza di banda per ogni collegamento WAN.

    > [!NOTE]
    > I limiti di larghezza di banda si riferiscono alla quantità di larghezza di banda su un collegamento WAN allocata VoIP aziendale traffico audio/video. Quando un collegamento WAN viene descritto come "vincolato alla larghezza di banda", il collegamento WAN ha un limite di larghezza di banda inferiore al traffico di picco previsto sul collegamento.

5. Identificare le subnet IP assegnate a ogni sito di rete.

Per spiegare questi concetti, verrà utilizzata la topologia di rete di esempio illustrata nella figura seguente.

**Topologia di esempio per il controllo di ammissione di chiamata**

![Litware Inc. Esempio di topologia di rete.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Tutti i siti di rete sono associati a un'area di rete. Portland, Reno e Albuquerque, ad esempio, sono inclusi nell'area Nord America. In questa figura sono visualizzati solo i collegamenti WAN a cui sono applicati criteri di controllo di ammissione di chiamata, con limiti di larghezza di banda. I siti di rete Chicago, New York e Detroit sono visualizzati all'interno dell'ovale dell'area Nord America perché non presentano limitazioni di larghezza di banda e quindi non richiedono criteri di controllo di ammissione di chiamata.

I componenti di questa topologia di esempio sono spiegati nelle sezioni seguenti. Per informazioni dettagliate sulla pianificazione di questa topologia, inclusi i limiti di larghezza di banda, vedere [Example: Gathering requirements for call admission control in Skype for Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identificare le aree di rete

Un'area di rete rappresenta un backbone o un hub della rete.

Un backbone o un hub di rete è una parte dell'infrastruttura di rete di computer che interconnette parti diverse della rete, offrendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Un backbone può collegare reti diverse, da una piccola sede a un'area geografica più ampia. La capacità del backbone è generalmente più alta rispetto a quella delle reti che vi si connettono.

La topologia dell'esempio include tre aree di rete, ovvero Nord America, EMEA e APAC. Un'area di rete contiene un insieme di siti di rete (vedere la definizione di siti di rete più avanti in questo argomento). Collaborare con il team responsabile delle operazioni di rete per identificare le aree.

### <a name="associating-a-central-site-with-each-network-region"></a>Associazione di un sito centrale a ogni area di rete

Il controllo di ammissione di chiamata richiede Skype for Business Server un sito centrale per ogni area di rete. Il sito centrale selezionato deve avere la connettività di rete più efficiente e la larghezza di banda più ampia verso tutti gli altri siti nell'area di rete. La topologia di rete dell'esempio precedente mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni relative al servizio Controllo di ammissione di chiamata. Per questo esempio l'associazione appropriata è illustrata nella tabella seguente.

> [!NOTE]
> I siti centrali non corrispondono necessariamente a siti di rete. Negli esempi in questa documentazione alcuni siti centrali, come Chicago, Londra e Pechino, hanno lo stesso nome di alcuni siti di rete. Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Skype for Business Server, mentre il sito di rete fa parte della rete complessiva in cui risiede la topologia Skype for Business Server.

**Aree di rete, siti centrali e siti di rete**

|**Area di rete**|**Sito centrale**|**Siti di rete**|
|:-----|:-----|:-----|
|Nord America  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londra  <br/> |Londra  <br/> Cologne  <br/> |
|APAC  <br/> |Pechino  <br/> |Pechino  <br/> Manila  <br/> |

### <a name="identify-network-sites"></a>Identificare i siti di rete

Un sito di rete rappresenta una località in cui l'organizzazione dispone di spazi fisici, ad esempio uffici, un gruppo di edifici o un campus. Uno spazio fisico con connettività LAN e WAN ad altri siti è considerata un sito di rete. Iniziare con l'inventario di tutti gli uffici dell'organizzazione. Nella topologia dell'esempio, l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

È necessario associare ogni sito di rete a un'area di rete. A seconda che il sito di rete abbia o meno un collegamento WAN limitato, al sito di rete vengono associati criteri per la larghezza di banda. Per informazioni dettagliate sui criteri di controllo di ammissione di chiamata e la larghezza di banda che è possibile allocare tramite tali criteri, vedere "Definire i criteri di larghezza di banda" di seguito in questo argomento. Per configurare i criteri di controllo di ammissione di chiamata, è necessario associare i siti di rete alle aree di rete e quindi creare i criteri di allocazione della larghezza di banda da applicare alle connessioni con larghezza di banda limitata tra un determinato sito o una particolare area e le connessioni WAN tra siti e aree.

### <a name="identify-network-links"></a>Identificare i collegamenti di rete

I collegamenti di rete rappresentano connessioni alla rete WAN fisica che collega i vari siti e aree. Nell'esempio di topologia utilizzato in questo argomento esistono due collegamenti di rete tra aree, cinque collegamenti di rete tra aree e siti e un collegamento di rete tra due siti.

I due collegamenti tra aree sono tra l'area Nord America ed EMEA, rappresentato come COLLEGAMENTO-NA-EMEA e tra APAC ed EMEA, rappresentato come COLLEGAMENTO-EMEA-APAC.

I collegamenti tra siti sono indicati dalle linee che connettono Portland, Reno e Albuquerque all'area Nord America, Manila all'area APAC e Colonia all'area EMEA. La linea tra Reno e Albuquerque mostra un collegamento di rete diretto tra questi due siti.

### <a name="define-bandwidth-policies"></a>Definire criteri di larghezza di banda

Collaborare con il team responsabile delle operazioni di rete per stabilire la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale sui collegamenti WAN dell'organizzazione. I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'uso della larghezza di banda è vincolato, ovvero se è previsto che sia superiore alla larghezza di banda disponibile per l'allocazione alle modalità audio e video.

I criteri di larghezza di banda del servizio Controllo di ammissione di chiamata definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale. Poiché il servizio Controllo di ammissione di chiamata non limita la larghezza di banda di altri tipi di traffico, non può impedire che altri tipi di traffico dati, ad esempio trasferimenti di file di grandi dimensioni o flussi di musica, usino tutta la larghezza di banda.

I criteri di larghezza di banda per il controllo di ammissione di chiamata possono definire solo alcuni o tutti gli aspetti seguenti:

- Larghezza di banda totale massima allocata per i contenuti audio.

- Larghezza di banda totale massima allocata per i contenuti video.

- Larghezza di banda massima allocata per una singola chiamata (sessione) audio.

- Larghezza di banda massima allocata per una singola chiamata (sessione) video.

> [!NOTE]
> Tutti i valori della larghezza di banda del controllo di ammissione di chiamata rappresentano  *i limiti di larghezza di banda unidirezionali*  massimi.

> [!NOTE]
> Le Skype for Business Server dei criteri vocali consentono di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita effettuate dall'utente). Dopo l'attivazione della sessione, il consumo di larghezza di banda verrà conteggiato accuratamente. Questa impostazione dovrebbe essere usata raramente. Per informazioni dettagliate, vedere [Create or modify a voice policy and configure PSTN usage records in Skype for Business](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) or Modify a Voice Policy and Configure [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records) nella documentazione relativa alla distribuzione.

Per ottimizzare l'uso della larghezza di banda su base per utente, tenere conto del tipo dei codec audio e video che verranno usati. In particolare, evitare di allocare una quantità di larghezza di banda insufficiente per un codec con uso previsto frequente. Viceversa, se si desidera impedire l'uso di un codec che richiede maggiore larghezza di banda, è consigliabile impostare la larghezza di banda massima per sessione su un valore sufficientemente basso da scoraggiarne l'uso. Per quando riguarda i contenuti audio, non tutti i codec sono disponibili per qualsiasi scenario. Ad esempio:

- Le chiamate audio peer-to-peer tra endpoint di Skype for Business utilizzeranno RTAudio (8kHz) o RTAudio (16kHz) quando si fattorizza la larghezza di banda e la priorità dei codec.

- Le conferenze telefoniche tra Skype for Business endpoint e il servizio A/V Conferencing utilizzeranno G.722 o Siren.

- Le chiamate alla rete PSTN (Public Switched Telephone Network) verso o da endpoint Skype for Business utilizzeranno G.711 o RTAudio (8kHz).

Fare riferimento alla tabella seguente per l'ottimizzazione delle impostazioni di larghezza di banda massima per sessione.

**Utilizzo della larghezza di banda in base ai codec**

|**Codec**|**Requisito di larghezza di banda senza correzione FEC (Forward Error Correction)**|**Requisito di larghezza di banda con correzione FEC (Forward Error Correction)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49,8 kbps  <br/> |61,6 kbps  <br/> |
|RTAudio (16kHz)  <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Sirena  <br/> |57,6 kbps  <br/> |73,6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105,6 kbps  <br/> |169,6 kbps  <br/> |
|RTVideo (CIF 15 fps)  <br/> |260 kbps  <br/> |NA  <br/> |
|RTVideo (VGA 30 fps)  <br/> |610 kbps  <br/> |NA  <br/> |

> [!NOTE]
> I requisiti di larghezza di banda tengono conto dell'overhead per Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-time Transport Protocol) e SRTP (Secure Real-time Transport Protocol), oltre a includere 10 kbps per l'overhead RTCP.

I codec G.722.1 e Siren sono simili, ma offrono velocità in bit diverse.

G.722, il codec predefinito per le conferenze Skype for Business Server, è completamente diverso dai codec G.722.1 e Siren.

Il codec Siren viene utilizzato in Skype for Business Server nelle situazioni seguenti:

- Se i criteri di larghezza di banda sono impostati su un valore troppo basso per l'uso di G.722

- Se un client Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio di conferenza di Skype for Business Server (perché tali client non supportano il codec G.722).

**Utilizzo della larghezza di banda in base allo scenario**

|**Scenario**|**Requisito di larghezza di banda ottimizzata per la quantità (kbps)**|**Requisito di larghezza di banda per la modalità con bilanciamento (kbps)**|**Requisito di larghezza di banda ottimizzata per la qualità (kbps)**|
|:-----|:-----|:-----|:-----|
|Chiamate audio peer-to-peer  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|Conferenze telefoniche  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|Chiamate PSTN (tra Skype for Business e gateway PSTN, con bypass multimediale)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chiamate PSTN (tra Skype for Business e Mediation Server, senza bypass multimediale)  <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Chiamate PSTN (tra Mediation Server e gateway PSTN, senza bypass multimediale)  <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype for Business - Chiamate Polycom  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |

### <a name="identify-ip-subnets"></a>Identificare le subnet IP

Per ogni sito di rete sarà necessario collaborare con l'amministratore della rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore della rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.

In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli prenotati per New York, ad esempio 172.29.80.103.

> [!CAUTION]
> Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per il bypass multimediale. Un Skype for Business client utilizza l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata. Durante la determinazione dell'ID di bypass associato a ogni client, la funzione di registrazione confronterà l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta. Per questo motivo è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali. Se si distribuisce il controllo di ammissione di chiamata, ma non il bypass multimediale, il controllo di ammissione di chiamata funzionerà correttamente anche se si configurano subnet virtuali. Ad esempio, se un client accede a un computer con indirizzo IP 172.29.81.57 con una subnet mask IP di 255.255.255.0, Skype for Business richiederà l'ID bypass associato alla subnet 172.29.81.0. Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0. Di conseguenza, è importante che l'amministratore immissione di subnet esattamente come fornito dai client Skype for Business (di cui viene eseguito il provisioning con subnet durante la configurazione di rete in modo statico o da DHCP).

## <a name="best-practices-for-call-admission-control"></a>Procedure consigliate per il controllo di ammissione di chiamata

Per migliorare le prestazioni e facilitare la distribuzione, applicare le procedure consigliate seguenti quando si distribuisce il servizio Controllo di ammissione di chiamata:

- Verificare che il provisioning delle WAN sia adeguato al traffico multimediale corrente e previsto.

    > [!NOTE]
    > È consigliabile considerare un buffer rispetto ai limiti di larghezza di banda. Esistono scenari, ad esempio le race condition, che incidono sulla larghezza di banda totale utilizzata e possono produrre situazioni in cui i limiti di larghezza di banda vengono superati. Se ad esempio si tenta di avviare due chiamate mentre il traffico multimediale si avvicina al limite di larghezza di banda, è possibile che una delle due venga rifiutata perché l'altra è configurata per partire per prima.

- Monitorare l'utilizzo della rete e i record dettagli chiamata, in modo da poter scegliere impostazioni ottimali per il servizio Controllo di ammissione di chiamata e aggiornarle al variare dell'utilizzo della rete.

- Utilizzare i criteri larghezza di banda relativi al servizio Controllo di ammissione di chiamata a complemento delle impostazioni QoS.

- Se si desidera reindirizzare le chiamate bloccate al PSTN, verificare le funzionalità e le capacità PSTN. Per ulteriori informazioni, vedere [Planning Outbound Call Routing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-outbound-voice-routing).

    > [!NOTE]
    > La capacità fa riferimento al numero di porte che è necessario aprire per supportare il potenziale reindirizzamento PSTN.