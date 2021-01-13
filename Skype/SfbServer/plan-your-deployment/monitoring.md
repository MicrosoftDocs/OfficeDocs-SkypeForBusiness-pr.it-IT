---
title: Pianificare il monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Riepilogo: esaminare questo argomento durante la pianificazione del servizio di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: b2f269d3e4cc62ca08ee423858e13d12b23bddd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825626"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Pianificare il monitoraggio in Skype for Business Server

**Riepilogo:** Esaminare questo argomento durante la pianificazione del servizio di monitoraggio in Skype for Business Server.

Il servizio di monitoraggio in Skype for Business Server consente agli amministratori di raccogliere dati di utilizzo e di qualità per le sessioni di comunicazione che si verificano nella propria organizzazione, consentendo loro di individuare le tendenze e i problemi. Il monitoraggio continuo della distribuzione consente di rilevare i problemi in anticipo e di soddisfare gli utenti dell'organizzazione.

Il monitoraggio in Skype for Business Server non richiede un ruolo del server separato (come nel caso delle versioni precedenti di Lync); al contrario, il servizio di monitoraggio è incorporato in ogni Front End Server. Il monitoraggio non è abilitato per impostazione predefinita in Skype for Business Server. Questo articolo consente di stabilire se abilitare il monitoraggio durante o dopo la configurazione iniziale di Skype for Business Server e quali risorse SQL è necessario per supportare le attività di monitoraggio. Se non si è sicuri di cosa sia o non è monitorato e di come il monitoraggio può essere utile, passare a [informazioni di base sul monitoraggio](monitoring.md#Basics). Per iniziare il processo di pianificazione, passare a [definire i requisiti per il monitoraggio](monitoring.md#requirements). Per ulteriori informazioni sui requisiti SQL per il monitoraggio, visitare i [requisiti SQL per il monitoraggio](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Nozioni di base sul monitoraggio
<a name="Basics"> </a>

Una sessione è un termine generico per la connessione di un utente a un:

- Conferenza

- Strumento di conferenza, ad esempio audio/video o condivisione applicazioni

- Un altro utente tramite una conversazione peer-to-peer come la messaggistica istantanea o una chiamata audio

> [!NOTE]
> Skype for Business Server tiene una registrazione delle informazioni su ogni sessione: chi ha chiamato chi; quali endpoint sono stati utilizzati nella sessione; durata della sessione. Qual è la qualità percepita della sessione; E così via. Skype for Business Server non registra e archivia la chiamata vera e propria. Che include sessioni di messaggistica istantanea: Sebbene Skype for Business Server registri informazioni sulle sessioni di messaggistica istantanea, non gestisce un record di ogni messaggio istantaneo inviato durante la sessione.

Le informazioni dettagliate sulle chiamate di base raccolte da Skype for Business Server per ogni sessione possono essere utilizzate per:

- Analisi **del ritorno sull'investimento (ROI)** . Gli amministratori possono confrontare i dati di utilizzo con dati simili raccolti per il sistema di telefonia precedente per mostrare risparmi sui costi e contribuire a giustificare la distribuzione di Skype for Business Server.

- **Gestione dell'inventario dei dispositivi**. Le informazioni relative alla gestione delle risorse consentono agli amministratori di identificare i dispositivi obsoleti ancora in uso che devono essere sostituiti e di identificare i costosi dispositivi inutilizzati o sottoutilizzati.

- **Supporto tecnico**. La risoluzione dei problemi dei dati consente agli ingegneri del supporto di determinare il motivo per cui la chiamata di un utente non è riuscita, senza dover raccogliere registri sul server o sul client Tali informazioni possono essere facilmente accessibili e intese da personale di supporto che non dispone di una conoscenza approfondita tecnica del client Skype for business e di Skype for Business Server.

- **Risoluzione dei problemi di sistema**. Gli amministratori hanno la possibilità di rilevare i principali problemi che possono impedire agli utenti finali di eseguire attività di base come partecipare a una conferenza, eseguire una chiamata o inviare un messaggio istantaneo.

Il monitoraggio fornisce anche un meccanismo che consente agli endpoint SIP (come Skype for business) di fornire informazioni per la risoluzione dei problemi a cui l'amministratore non avrebbe altrimenti accesso:

- **Metriche che influiscono sulla qualità**. Queste metriche riguardano la trasmissione effettiva della chiamata stessa; Essi forniscono una sorta di diario di viaggio come i viaggi di chiamata attraverso la rete. Queste metriche (che includono elementi quali perdita di pacchetti, instabilità e tempi di andata e ritorno) forniscono informazioni su ciò che è accaduto alla chiamata dal momento in cui è stato lasciato l'endpoint di una persona al momento in cui è arrivato all'endpoint dell'altra persona.

- **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di qualità scadente che Skype for business presenta agli utenti finali nei casi in cui sono troppo lontani da un microfono, parlando troppo piano, hanno una connessione di rete scadente o stanno vivendo una qualità scadente perché un altro programma del computer sta consumando le risorse disponibili.

- **Informazioni sull'ambiente**. Queste metriche offrono dati dettagliati su aspetti che influiscono sulla qualità delle chiamate, come il tipo di microfono e altoparlanti in uso, se l'utente è connesso tramite VPN e se l'utente sta utilizzando una connessione wireless.

Al termine di ogni chiamata, gli endpoint conformi a SIP trasmettono queste informazioni al front end server che facilita la chiamata. Non è necessario eseguire alcuna operazione per fare in modo che gli endpoint trasmettano tali informazioni, perché questo comportamento è incorporato nel protocollo SIP. Se si desidera raccogliere e archiviare tali informazioni, tuttavia, è necessario installare e abilitare il monitoraggio. In questo modo, le informazioni sulle chiamate vengono raccolte dagli agenti in esecuzione nel Front End Server e inoltrate a una coppia di database di SQL Server. Il servizio di monitoraggio, sotto forma di "agenti di raccolta dati unificati", è collocato in tutti i Front End Server.

## <a name="define-your-requirements-for-monitoring"></a>Definire i requisiti per il monitoraggio
<a name="requirements"> </a>

Sono ancora numerosi i problemi principali che devono essere risolti prima di iniziare a installare e configurare il monitoraggio con Skype for Business Server:

 **Quando si desidera installare il monitoraggio?** Il monitoraggio può essere installato e configurato nello stesso momento in cui si installa e configura Skype for Business Server; la distribuzione guidata di Skype for Business Server offrirà la possibilità di associare i pool Front end a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo che è stato installato Skype for Business Server. a tale scopo, è possibile utilizzare il generatore di topologie per associare i pool Front end e i server a un database di monitoraggio e quindi pubblicare la topologia riveduta.

Tenere presente che SQL Server deve essere installato e configurato prima di distribuire e configurare il monitoraggio. Tuttavia, è necessario solo distribuire SQL Server stesso. i database di monitoraggio verranno creati per l'utente quando si pubblica la topologia di Skype for Business Server.

 **Che tipo di dati si desidera monitorare?** Skype for Business Server consente di monitorare due tipi generali di dati, ovvero dati di registrazione dettagli chiamata (CDR) e dati QoE (Quality of Experience). La registrazione dettagli chiamata consente di monitorare l'utilizzo delle funzionalità di Skype for Business Server, ad esempio le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Queste informazioni consentono di sapere quali funzionalità di Skype for Business Server sono in uso (e quali no) e fornisce anche informazioni su quando vengono utilizzate queste funzionalità. La qualità dei dati di utilizzo consente di mantenere una registrazione della qualità delle chiamate audio e video eseguite nell'organizzazione, inclusi il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "jitter" (differenze nel ritardo dei pacchetti).

Se si sceglie di abilitare il monitoraggio in Skype for Business Server, è possibile abilitare sia il monitoraggio del CDR che il monitoraggio QoE oppure è possibile scegliere di abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Si supponga, ad esempio, che gli utenti utilizzino solo la messaggistica istantanea e i trasferimenti di file e non effettuino chiamate audio o video. In tal caso, è possibile che venga attivato il monitoraggio QoE. Analogamente, Skype for Business Server facilita l'abilitazione e la disabilitazione del monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, è possibile scegliere di distribuire il monitoraggio ma lasciare inizialmente il monitoraggio QoE disabilitato. Se gli utenti iniziano a riscontrare problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e utilizzare tali dati per risolvere i problemi e risolverli.

Non vi sono vantaggi particolari (o svantaggi) per l'installazione del monitoraggio contemporaneamente all'installazione di Skype for Business Server e all'installazione del monitoraggio dopo l'installazione di Skype for Business Server. Il punto da tenere in considerazione consiste nel fatto che, prima di installare il monitoraggio, è necessario selezionare un computer per ospitare l'archivio di monitoraggio di back-end e una versione supportata di SQL Server deve essere installata e configurata nel computer prima che sia possibile utilizzare il computer per il monitoraggio. Se SQL Server è stato già installato in un computer e il computer è pronto per l'uso, è possibile installare il monitoraggio contemporaneamente all'installazione di Skype for Business Server. Se non si dispone di un computer back-end pronto, è possibile procedere con l'installazione di Skype for Business Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

 **Quanti database di monitoraggio back-end sono necessari?** È stato valutato che un database collocato per il monitoraggio e l'archiviazione potrebbe supportare gli utenti di 240.000 Skype for Business Server. Inoltre, un singolo database di monitoraggio può essere utilizzato da più pool Front end. Se nell'organizzazione sono presenti tre pool Front End, è possibile associare tutti e tre i pool allo stesso archivio back-end.

Per molte organizzazioni, la capacità del database non sarà il fattore decisivo quando si determina il numero di database di monitoraggio back-end che saranno necessari. Invece, una considerazione più importante potrebbe essere la velocità della rete. Si supponga di disporre di tre pool Front End, ma uno di questi pool si trova in una connessione di rete lenta. In tal caso, è possibile utilizzare due database di monitoraggio: un database per il servizio dei due pool con la connessione di rete valida e un database separato per il servizio del pool con la connessione di rete più lenta.

È inoltre necessario tenere presente che Skype for Business Server supporta l'utilizzo dei database mirror. "Mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede in un server diverso. Ogni volta che i dati vengono scritti in un database primario, anche gli stessi dati vengono scritti nel database mirror. Se il database primario deve avere esito negativo o altrimenti non è disponibile, è possibile eseguire il failover del database mirror utilizzando un semplice comando di PowerShell per Skype for Business Server. Ad esempio:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Questo è importante per la pianificazione, semplicemente perché il mirroring richiederà di raddoppiare il numero di database necessari: in aggiunta a ogni database primario, sarà necessario un secondo database per fungere da mirror.

 **I siti di Skype for Business Server devono disporre di configurazioni di monitoraggio personalizzate?** Quando si installa Skype for Business Server, vengono installate anche raccolte globali di impostazioni di configurazione di CDR e QoE. Queste raccolte globali offrono la possibilità di applicare le stesse impostazioni CDR e QoE all'intera organizzazione. In molti casi, questo sarà sufficiente: spesso, ad esempio, si vorrà dire che il monitoraggio CDR è abilitato per tutti gli utenti.

Tuttavia, è possibile che si verifichino anche momenti in cui si desidera applicare impostazioni diverse a siti diversi. Ad esempio, se si desidera utilizzare il monitoraggio CDR e QoE nel sito Redmond, è possibile utilizzare solo il monitoraggio di registrazione dettagli chiamata nel sito di Dublino. Analogamente, potrebbe essere necessario mantenere i dati di monitoraggio per 60 giorni nel sito Redmond, ma è sufficiente mantenere questo tipo di dati per 30 giorni nel sito di Dublino. Skype for Business Server consente di creare raccolte separate di impostazioni di configurazione di registrazione dettagli chiamata e QoE nell'ambito del sito. che consente di gestire ogni sito in modo diverso. Questo include sia l'abilitazione e la disabilitazione del monitoraggio, sia la configurazione delle impostazioni di gestione, ad esempio la durata di conservazione dei dati.

Tenere presente che è possibile prendere questa decisione prima di distribuire il monitoraggio o dopo aver distribuito il monitoraggio. Ad esempio, è possibile distribuire il monitoraggio e quindi gestire l'intera organizzazione utilizzando le impostazioni globali. Se in seguito si cambia idea, è possibile creare una raccolta distinta di impostazioni per, ad esempio, il sito Redmond e quindi utilizzare tali impostazioni per gestire il monitoraggio di Redmond. (Le impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale). Se si cambia idea, è possibile semplicemente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale di impostazioni verrà applicata automaticamente a tale sito.

## <a name="sql-requirements-for-monitoring"></a>Requisiti di SQL per il monitoraggio
<a name="topologies"> </a>

Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server quando si Abilita il monitoraggio. Per le versioni supportate di SQL Server e altri dettagli, vedere [requisiti del server per Skype for Business server 2015](requirements-for-your-environment/server-requirements.md)

I dati di monitoraggio possono condividere un'istanza di SQL Server con altri tipi di dati. In genere, il database di registrazione dettagli chiamata (LcsCdr) e il database Quality of Experience (QoEMetrics) condividono la stessa istanza SQL. è inoltre comune che i due database di monitoraggio si trovino nella stessa istanza di SQL del database di archiviazione (LcsLog). Informazioni sull'unico requisito reale con le istanze di SQL Server è che una qualsiasi istanza di SQL Server è limitata alla seguente:

- Un'istanza del database back-end di Skype for Business Server 2015. (Come regola generale, non è consigliabile che il database di monitoraggio sia collocato nella stessa istanza SQL o anche nello stesso computer, come database back-end. Anche se tecnicamente possibile, si corre il rischio che il database di monitoraggio utilizzi lo spazio su disco necessario per il database back-end.

- Un'istanza del database di registrazione dettagli chiamata.

- Un'istanza del database Quality of Experience.

- Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database di LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database di LcsCdr, è necessario configurare più istanze di SQL Server.

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
