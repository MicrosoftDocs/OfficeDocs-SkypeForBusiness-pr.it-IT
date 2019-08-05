---
title: Pianificare il monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Riepilogo: rivedere questo argomento durante la pianificazione per il servizio di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: e03fc9714cbb958a9c34bb14db0129a94e49692b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194916"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Pianificare il monitoraggio in Skype for Business Server

**Riepilogo:** Esaminare questo argomento durante la pianificazione per il servizio di monitoraggio in Skype for Business Server.

Il servizio di monitoraggio in Skype for Business Server consente agli amministratori di raccogliere dati sull'uso e la qualità per le sessioni di comunicazione che si svolgono nell'organizzazione, che consente loro di identificare tendenze e problemi. Il monitoraggio continuo della distribuzione consente di rilevare i problemi in anticipo e di soddisfare gli utenti dell'organizzazione.

Il monitoraggio in Skype for Business Server non richiede un ruolo server distinto, come nel caso delle versioni precedenti di Lync; il servizio di monitoraggio è invece incorporato in ogni server front-end. Il monitoraggio non è abilitato per impostazione predefinita in Skype for Business Server. Questo articolo consente di determinare se abilitare il monitoraggio durante o dopo la configurazione iniziale di Skype for Business Server e le risorse SQL necessarie per supportare le attività di monitoraggio. Se non si è sicuri di cosa sia o non sia monitorato e di come può essere utile il monitoraggio, vedere [informazioni di base sul monitoraggio](monitoring.md#Basics). Per iniziare il processo di pianificazione, vedere [definire i requisiti per il monitoraggio](monitoring.md#requirements). Per altre informazioni sui requisiti SQL per il monitoraggio, vedere [requisiti SQL per il monitoraggio](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Nozioni di base sul monitoraggio
<a name="Basics"> </a>

Una sessione è un termine generico per la connessione di un utente a:

- Conferenza

- Strumento di conferenza, ad esempio condivisione audio/video o applicazioni

- Un altro utente tramite una conversazione peer-to-peer, ad esempio la messaggistica istantanea o una chiamata audio

> [!NOTE]
> Skype for Business Server tiene traccia delle informazioni relative a ogni sessione: chi ha chiamato chi; quali endpoint sono stati usati nella sessione; durata della sessione Qual è stata la qualità percepita della sessione; E così via. Skype for Business Server non registra e archivia la chiamata effettiva stessa. Che include sessioni di messaggistica istantanea: anche se Skype for Business Server registra informazioni sulle sessioni di messaggistica istantanea, non mantiene un record di ogni messaggio istantaneo inviato durante la sessione.

Le informazioni dettagliate sulle chiamate di base raccolte da Skype for Business Server per ogni sessione possono essere usate per:

- Analisi **return on Investment (ROI)** . Gli amministratori possono confrontare i dati di utilizzo con dati simili raccolti per il sistema di telefonia precedente per mostrare il risparmio dei costi e giustificare la distribuzione di Skype for Business Server.

- **Gestione inventario dispositivi**. Le informazioni sulla gestione degli asset aiutano gli amministratori a identificare i vecchi dispositivi ancora in uso che devono essere sostituiti e ad identificare dispositivi costosi inutilizzati o sottoutilizzati.

- **Help desk**. La risoluzione dei problemi dei dati consente agli ingegneri del supporto di determinare il motivo per cui la chiamata di un utente non è riuscita, senza dover raccogliere log lato server o client. Queste informazioni possono essere facilmente accessibili e comprese dal personale di supporto che non ha una profonda conoscenza tecnica del client Skype for business e di Skype for Business Server.

- **Risoluzione dei problemi di sistema**. Consente agli amministratori di rilevare problemi importanti che potrebbero impedire agli utenti finali di eseguire attività di base, ad esempio partecipare a una conferenza, stabilire una chiamata o inviare un messaggio istantaneo.

Il monitoraggio offre anche un meccanismo che consente agli endpoint SIP (ad esempio Skype for business) di fornire informazioni di risoluzione dei problemi che l'amministratore non avrebbe altrimenti accesso:

- **Metriche multimediali che incidono sulla qualità**. Queste metriche trattano la trasmissione effettiva della chiamata stessa; Essi costituiscono una sorta di diario di viaggio durante i viaggi di chiamata in tutta la rete. Queste metriche (che includono elementi come la perdita di pacchetti, il jitter e i tempi di andata e ritorno) offrono informazioni su ciò che è accaduto alla chiamata dal momento in cui ha lasciato l'endpoint di una persona fino al momento in cui è arrivato all'endpoint dell'altra persona.

- **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di qualità scadente che Skype for business presenta agli utenti finali nei casi in cui siano troppo lontani da un microfono, che parli troppo dolcemente, che abbiano una connessione di rete scadente o che abbiano una qualità scadente perché un altro programma della il computer sta consumando le risorse disponibili.

- **Informazioni sull'ambiente**. Queste metriche denominano fattori di qualità come il tipo di microfono e gli altoparlanti usati, se l'utente è connesso tramite una connessione VPN e se l'utente si trova in una connessione wireless.

Alla fine di ogni chiamata, gli endpoint conformi a SIP trasmettono queste informazioni al server front-end che facilita la chiamata. Non è necessario eseguire alcuna operazione per ottenere gli endpoint per trasmettere tali informazioni; Questo comportamento è incorporato nel protocollo SIP. Tuttavia, se si vogliono raccogliere e archiviare tali informazioni, è necessario installare e abilitare il monitoraggio. Se si installa e si Abilita il monitoraggio, le informazioni sulle chiamate vengono raccolte dagli agenti in uso nel server front-end e inoltrate a una coppia di database di SQL Server. Il servizio di monitoraggio (sotto forma di "agenti di raccolta dati unificati") è collocato in tutti i server front-end.

## <a name="define-your-requirements-for-monitoring"></a>Definire i requisiti per il monitoraggio
<a name="requirements"> </a>

Ci sono ancora diversi problemi chiave che devono essere affrontati prima di iniziare a installare e configurare il monitoraggio con Skype for Business Server:

 **Quando si vuole installare il monitoraggio?** Il monitoraggio può essere installato e configurato contemporaneamente all'installazione e alla configurazione di Skype for Business Server; la distribuzione guidata di Skype for Business Server ti offre l'opportunità di associare i pool Front-end a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo l'installazione di Skype for Business Server; Questa operazione può essere eseguita usando generatore di topologie per associare i pool e i server front-end a un database di monitoraggio e quindi pubblicare la topologia riveduta.

Tieni presente che SQL Server deve essere installato e configurato prima di distribuire e configurare il monitoraggio. È tuttavia necessario distribuire solo SQL Server. i database di monitoraggio verranno creati quando pubblichi la topologia di Skype for Business Server.

 **Quali tipi di dati si desidera monitorare?** Skype for Business Server consente di monitorare due tipi generali di dati: i dati di registrazione Detailing delle chiamate (CDR) e la qualità dell'esperienza (QoE). La registrazione dei dettagli delle chiamate offre un modo per tenere traccia dell'uso delle funzionalità di Skype for Business Server, ad esempio chiamate VoIP (Voice over IP); messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Queste informazioni consentono di sapere quali funzionalità di Skype for Business Server vengono usate (e quali no) e forniscono anche informazioni su quando vengono usate queste caratteristiche. La qualità dei dati sulle esperienze consente di mantenere un record della qualità delle chiamate audio e video effettuate nella propria organizzazione, inclusi elementi come il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto).

Se si sceglie di abilitare il monitoraggio in Skype for Business Server è possibile abilitare sia il monitoraggio CDR che il controllo QoE oppure si può scegliere di abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Supponiamo ad esempio che gli utenti usino solo la messaggistica istantanea e i trasferimenti di file e non effettuino chiamate audio o video. In questo caso, è possibile che venga attivato il monitoraggio QoE. Allo stesso modo, Skype for Business Server semplifica l'abilitazione e la disabilitazione del monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, potresti scegliere di distribuire il monitoraggio, ma lasci inizialmente il monitoraggio QoE disabilitato. Se gli utenti iniziano a riscontrare problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e usare questi dati per risolvere i problemi e risolverli.

Non c'è un particolare vantaggio (o svantaggio) per installare il monitoraggio contemporaneamente all'installazione di Skype for Business Server e all'installazione del monitoraggio dopo che è stato installato Skype for Business Server. Il punto da tenere presente è che, prima di installare il monitoraggio, è necessario selezionare un computer per ospitare l'archivio di monitoraggio del backend e una versione supportata di SQL Server deve essere installata e configurata nel computer prima di poter usare il computer per il monitoraggio . Se SQL Server è già installato in un computer e il computer è pronto per l'uso, è possibile installare il monitoraggio contemporaneamente all'installazione di Skype for Business Server. Se non si dispone di un computer back-end pronto, è possibile procedere con l'installazione di Skype for Business Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

 **Quanti database di monitoraggio backend sono necessari?** È stato valutato che un database collocato sia per il monitoraggio che per l'archiviazione potrebbe supportare gli utenti di 240.000 Skype for Business Server). Inoltre, un singolo database di monitoraggio può essere usato da più pool Front-end. Se sono presenti tre pool di front-end nell'organizzazione, è possibile associare tutti e tre i pool allo stesso archivio backend.

Per molte organizzazioni, la capacità del database non sarà il fattore decisivo per determinare il numero di database di monitoraggio backend che saranno necessari. Una considerazione più importante potrebbe invece essere la velocità della rete. Supponiamo di avere tre pool Front-End, ma uno di questi pool si trova in una connessione di rete lenta. In questo caso, potresti voler usare due database di monitoraggio: un database per il servizio dei due pool con la connessione di rete buona e un database separato per il servizio del pool con la connessione di rete più lenta.

Dovresti anche tenere in considerazione che Skype for Business Server supporta l'uso dei database mirror. "Mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede in un server diverso. Ogni volta che i dati vengono scritti in un database primario, anche i dati vengono scritti nel database mirror. Se il database primario deve avere esito negativo o in caso contrario diventa non disponibile, è possibile eseguire il failover del database mirror usando un semplice comando di PowerShell per Skype for Business Server. Ad esempio:

```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Questo è importante per scopi di pianificazione semplicemente perché il mirroring richiederà di raddoppiare il numero di database necessario: oltre a ogni database principale è necessario un secondo database per fungere da mirror.

 **I siti di Skype for Business Server necessitano di configurazioni di monitoraggio personalizzate?** Quando si installa Skype for Business Server si installano anche raccolte globali di impostazioni di configurazione CDR e QoE; Queste raccolte globali offrono la possibilità di applicare le stesse impostazioni CDR e QoE all'intera organizzazione. In molti casi, questo sarà sufficiente: spesso si vorrà, ad esempio, avere il monitoraggio CDR abilitato per tutti gli utenti.

Tuttavia, potrebbero esserci anche momenti in cui si vogliono applicare impostazioni diverse a siti diversi. Ad esempio, è possibile usare sia il monitoraggio CDR che QoE nel sito Redmond, ma usare solo il monitoraggio CDR nel sito di Dublino. Allo stesso modo, potresti voler mantenere i dati di monitoraggio per 60 giorni nel sito Redmond, ma devi solo mantenere questo tipo di dati per 30 giorni nel sito di Dublino. Skype for Business Server consente di creare raccolte separate di impostazioni di configurazione CDR e QoE nell'ambito del sito. che consente di gestire ogni sito in modo diverso. (Questo include sia l'abilitazione che la disabilitazione del monitoraggio, nonché la configurazione delle impostazioni di gestione, ad esempio il periodo di conservazione dei dati).

Tieni presente che puoi prendere questa decisione prima di distribuire il monitoraggio o dopo la distribuzione del monitoraggio. Ad esempio, puoi distribuire il monitoraggio e quindi gestire l'intera organizzazione usando le impostazioni globali. Se in seguito si cambia idea, è possibile creare una raccolta distinta di impostazioni per, ad esempio, il sito Redmond e quindi usare queste impostazioni per gestire il monitoraggio di Redmond. Le impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale. Se si cambia idea, è possibile semplicemente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale delle impostazioni verrà applicata automaticamente a tale sito.

## <a name="sql-requirements-for-monitoring"></a>Requisiti SQL per il monitoraggio
<a name="topologies"> </a>

Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni server front-end quando si Abilita il monitoraggio. Per le versioni supportate di SQL Server e altri dettagli, vedere [requisiti del server per Skype for Business server 2015](requirements-for-your-environment/server-requirements.md)

I dati di monitoraggio possono condividere un'istanza di SQL Server con altri tipi di dati. In genere, il database di registrazione dei dettagli delle chiamate (LcsCdr) e la qualità del database di Experience (QoEMetrics) condividono la stessa istanza SQL. è inoltre comune che i due database di monitoraggio siano nella stessa istanza SQL del database di archiviazione (LcsLog). Informazioni sull'unico requisito reale delle istanze di SQL Server è che una qualsiasi istanza di SQL Server è limitata alle seguenti:

- Un'istanza del database back-end di Skype for Business Server 2015. Come regola generale, non è consigliabile che il database di monitoraggio sia collocato nella stessa istanza SQL o anche nello stesso computer, come database back-end. Anche se tecnicamente è possibile, si corre il rischio che il database di monitoraggio usi lo spazio su disco necessario per il database back-end.

- Un'istanza del database di registrazione dei dettagli delle chiamate.

- Un'istanza del database Quality of Experience.

- Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database di LcsCdr, è necessario configurare più istanze di SQL Server.

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
