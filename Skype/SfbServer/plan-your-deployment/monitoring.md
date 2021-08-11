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
ms.openlocfilehash: 0845fb0aa266b955fd86ebc7abf418b98034e31334fbc50dbbb048040e943cf4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306737"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Pianificare il monitoraggio in Skype for Business Server

**Riepilogo:** Leggere questo argomento durante la pianificazione del servizio di monitoraggio in Skype for Business Server.

Il servizio di monitoraggio di Skype for Business Server consente agli amministratori di raccogliere dati di utilizzo e qualità per le sessioni di comunicazione che si svolgono nell'organizzazione, in modo da consentire loro di identificare tendenze e problemi. Il monitoraggio continuo della distribuzione consente di rilevare i problemi in anticipo e di mantenere soddisfatti gli utenti dell'organizzazione.

Il monitoraggio in Skype for Business Server non richiede un ruolo del server separato (come nelle versioni precedenti di Lync); al contrario, il servizio di monitoraggio è incorporato in ogni Front End Server. Il monitoraggio non è abilitato per impostazione predefinita in Skype for Business Server. Questo articolo consente di determinare se abilitare il monitoraggio durante o dopo la configurazione di Skype for Business Server iniziale e quali risorse SQL necessarie per supportare le attività di monitoraggio. Se non si è certi di cosa sia o non sia monitorato e di come il monitoraggio possa essere utile, passare a [Nozioni di base sul monitoraggio](monitoring.md#Basics). Per iniziare il processo di pianificazione, passare a [Definire i requisiti per il monitoraggio](monitoring.md#requirements). Per ulteriori dettagli sui requisiti SQL per il monitoraggio, vedere SQL [requisiti per il monitoraggio](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Nozioni di base sul monitoraggio
<a name="Basics"> </a>

Una sessione è un termine generico per la connessione di un utente a un:

- Conferenza

- Strumento di conferenza, ad esempio Audio/Video o Condivisione applicazioni

- Un altro utente tramite una conversazione peer-to-peer come la messaggistica istantanea o una chiamata audio

> [!NOTE]
> Skype for Business Server tiene traccia delle informazioni su ogni sessione: chi ha chiamato chi; quali endpoint sono stati usati nella sessione; per quanto tempo è durata la sessione; qual era la qualità percepita della sessione; E così via. Skype for Business Server non registra e archivia la chiamata effettiva. Sono incluse le sessioni di messaggistica istantanea: sebbene Skype for Business Server le informazioni sulle sessioni di messaggistica istantanea, non mantiene un record di ogni messaggio istantaneo inviato durante la sessione.

Le informazioni dettagliate sulle chiamate di base raccolte Skype for Business Server per ogni sessione possono essere utilizzate per:

- **Analisi del ritorno sull'investimento (ROI).** Gli amministratori possono confrontare i dati di utilizzo con dati simili raccolti per il sistema di telefonia precedente per mostrare risparmi sui costi e giustificare la distribuzione di Skype for Business Server.

- **Gestione dell'inventario dei dispositivi**. Le informazioni sulla gestione delle risorse consentono agli amministratori di identificare i vecchi dispositivi ancora in uso che devono essere sostituiti e di identificare i dispositivi costosi inutilizzati o sottoutilizzate.

- **Help Desk**. La risoluzione dei problemi dei dati consente ai tecnici del supporto tecnico di determinare il motivo per cui la chiamata di un utente non è riuscita, senza dover raccogliere registri lato server o client. Queste informazioni possono essere facilmente accessibili e comprese dal personale di supporto che non dispone di una conoscenza tecnica approfondita del client Skype for Business e Skype for Business Server.

- **Risoluzione dei problemi di sistema**. Gli amministratori hanno la possibilità di rilevare i principali problemi che possono impedire agli utenti finali di eseguire attività di base come partecipare a una conferenza, eseguire una chiamata o inviare un messaggio istantaneo.

Il monitoraggio fornisce inoltre un meccanismo che consente agli endpoint SIP (ad esempio Skype for Business) di fornire informazioni sulla risoluzione dei problemi a cui l'amministratore non avrebbe altrimenti accesso:

- **Metriche che influiscono sulla qualità**. Queste metriche trattano la trasmissione effettiva della chiamata stessa; forniscono una sorta di travelogue mentre la chiamata attraversa la rete. Queste metriche (che includono aspetti quali perdita di pacchetti, instabilità e tempi di round trip) forniscono informazioni su cosa è successo alla chiamata dal momento in cui ha lasciato l'endpoint di una persona al momento in cui è arrivato all'endpoint dell'altra persona.

- **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di qualità scarsa che Skype for Business presenta agli utenti finali nei casi in cui sono troppo lontani da un microfono, parlano troppo piano, hanno una connessione di rete scarsa o stanno riscontrando una qualità scarsa perché un altro programma nel computer sta consumando le risorse disponibili.

- **Informazioni sull'ambiente**. Queste metriche offrono dati dettagliati su aspetti che influiscono sulla qualità delle chiamate, come il tipo di microfono e altoparlanti in uso, se l'utente è connesso tramite VPN e se l'utente sta utilizzando una connessione wireless.

Al termine di ogni chiamata, gli endpoint conformi a SIP trasmettono queste informazioni al Front End Server che ha facilitato la chiamata. Non è necessario eseguire alcuna operazione per fare in modo che gli endpoint trasmettano tali informazioni, perché questo comportamento è incorporato nel protocollo SIP. Se si desidera raccogliere e archiviare tali informazioni, tuttavia, è necessario installare e abilitare il monitoraggio. In questo modo, le informazioni sulle chiamate vengono raccolte dagli agenti in esecuzione nel Front End Server e inoltrate a una coppia di database di SQL Server. Il servizio di monitoraggio (sotto forma di "agenti di raccolta dati unificati") è collocato in tutti i Front End Server.

## <a name="define-your-requirements-for-monitoring"></a>Definire i requisiti per il monitoraggio
<a name="requirements"> </a>

Esistono ancora diversi problemi chiave che devono essere risolti prima di iniziare a installare e configurare il monitoraggio con Skype for Business Server:There are still several key issues that should be addressed before you begin to install and configure monitoring with Skype for Business Server:

 **Quando si desidera installare il monitoraggio?** Il monitoraggio può essere installato e configurato contemporaneamente all'installazione e alla configurazione Skype for Business Server; la Skype for Business Server guidata consente di associare i pool Front End a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo Skype for Business Server è stato installato; A tale scopo, è possibile utilizzare Generatore di topologie per associare i pool e i server Front End a un database di monitoraggio e quindi pubblicare la topologia rivista.

Tenere presente che è SQL Server essere installato e configurato prima di distribuire e configurare il monitoraggio. Tuttavia, è necessario distribuire solo SQL Server se stesso. i database di monitoraggio verranno creati automaticamente quando si pubblica la Skype for Business Server topologia.

 **Che tipo di dati si desidera monitorare?** Skype for Business Server consente di monitorare due tipi generali di dati: i dati di registrazione dettagli chiamata (CDR) e i dati QoE (Quality of Experience). La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo di funzionalità Skype for Business Server quali le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea; trasferimenti di file; audio/video (A/V) conferencing; e sessioni di condivisione delle applicazioni. Queste informazioni consentono di sapere quali Skype for Business Server sono in uso (e quali non lo sono) e forniscono anche informazioni su quando queste funzionalità vengono utilizzate. I dati sulla qualità dell'esperienza consentono di mantenere un record della qualità delle chiamate audio e video effettuate nell'organizzazione, ad esempio il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti).

Se si sceglie di abilitare il monitoraggio in Skype for Business Server è possibile abilitare sia il monitoraggio cdR che il monitoraggio QoE oppure è possibile scegliere di abilitare un tipo di monitoraggio lasciando disabilitato l'altro tipo. Si supponga, ad esempio, che gli utenti utilizzino solo la messaggistica istantanea e i trasferimenti di file e non esemplino chiamate audio o video. In tal caso, potrebbe essere necessario abilitare il monitoraggio QoE. Allo stesso modo, Skype for Business Server consente di abilitare e disabilitare facilmente il monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, è possibile scegliere di distribuire il monitoraggio, ma inizialmente lasciare disabilitato il monitoraggio QoE. Se gli utenti iniziano a verificarsi problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e usare tali dati per risolvere i problemi.

Non esiste alcun vantaggio (o svantaggio) particolare per l'installazione del monitoraggio contemporaneamente all'installazione di Skype for Business Server rispetto all'installazione del monitoraggio dopo l'Skype for Business Server è stato installato. L'unico punto da tenere presente è che, prima di installare il monitoraggio, è necessario selezionare un computer per ospitare l'archivio di monitoraggio back-end e che una versione supportata di SQL Server deve essere installata e configurata in tale computer prima di poter utilizzare tale computer per il monitoraggio. Se è già stato installato SQL Server in un computer e tale computer è pronto per l'uso, è possibile installare il monitoraggio contemporaneamente all'installazione Skype for Business Server. Se non si dispone di un computer back-end pronto, è possibile procedere all'installazione di Skype for Business Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

 **Quanti database di monitoraggio back-end sono necessari?** È stato stimato che un database collocato per il monitoraggio e l'archiviazione poteva supportare 240.000 Skype for Business Server utenti). Inoltre, un singolo database di monitoraggio può essere utilizzato da più pool Front End. se nell'organizzazione sono presenti tre pool Front End, è possibile associare tutti e tre i pool allo stesso archivio back-end.

Per molte organizzazioni, la capacità del database non sarà il fattore determinante per determinare il numero di database di monitoraggio back-end necessari. Al contrario, una considerazione più importante potrebbe essere la velocità di rete. Si supponga di disporre di tre pool Front End, ma uno di tali pool si trova su una connessione di rete lenta. In tal caso, potrebbe essere necessario utilizzare due database di monitoraggio: un database per il servizio dei due pool con la connessione di rete buona e un database separato per il servizio del pool con la connessione di rete più lenta.

È inoltre necessario prendere in considerazione che Skype for Business Server supporta l'utilizzo di database mirror. Il "mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede su un server diverso. Ogni volta che i dati vengono scritti in un database primario, gli stessi dati vengono scritti anche nel database mirror. Se il database primario ha esito negativo o altrimenti non è più disponibile, è possibile eseguire il "failover" nel database mirror utilizzando un semplice comando Skype for Business Server PowerShell. Ad esempio:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Ciò è importante a scopo di pianificazione semplicemente perché il mirroring richiede il doppio del numero necessario di database: oltre a ogni database primario sarà necessario un secondo database per fungere da mirror.

 **I siti Skype for Business Server devono avere configurazioni di monitoraggio personalizzate?** Quando si installa Skype for Business Server si installano anche raccolte globali di impostazioni di configurazione di registrazione dei dati e QoE. queste raccolte globali offrono la possibilità di applicare le stesse impostazioni cdR e QoE all'intera organizzazione. In molti casi, ciò sarà sufficiente: spesso si desidera, ad esempio, che il monitoraggio della registrazione dei dati sia abilitato per tutti gli utenti.

È tuttavia possibile che in alcuni casi si desideri applicare impostazioni diverse a siti diversi. Ad esempio, è possibile che si desideri utilizzare sia il monitoraggio cdR che il monitoraggio QoE nel sito Redmond, ma utilizzare solo il monitoraggio della registrazione dei dati nel sito di Dublino. Analogamente, è possibile conservare i dati di monitoraggio per 60 giorni nel sito Redmond, ma è necessario mantenere questo tipo di dati solo per 30 giorni nel sito di Dublino. Skype for Business Server consente di creare raccolte separate di impostazioni di configurazione cdR e QoE nell'ambito del sito; che consente di gestire ogni sito in modo diverso. Ciò include sia l'abilitazione che la disabilitazione del monitoraggio, nonché la configurazione delle impostazioni di gestione, ad esempio la durata della conservazione dei dati.

Tenere presente che è possibile prendere questa decisione prima di distribuire il monitoraggio o dopo la distribuzione del monitoraggio. Ad esempio, è possibile distribuire il monitoraggio e quindi gestire l'intera organizzazione utilizzando le impostazioni globali. Se successivamente si cambia idea, è possibile creare una raccolta separata di impostazioni per, ad esempio, il sito Redmond e quindi utilizzare tali impostazioni per gestire il monitoraggio per Redmond. Le Impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale. Se si cambia idea di nuovo, è sufficiente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale di impostazioni verrà applicata automaticamente a tale sito.

## <a name="sql-requirements-for-monitoring"></a>SQL requisiti per il monitoraggio
<a name="topologies"> </a>

Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni Front End Server quando si abilita il monitoraggio. Per le versioni supportate di SQL Server e altri dettagli, vedere [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

I dati di monitoraggio possono condividere SQL Server'istanza con altri tipi di dati. In genere, il database di registrazione dettagli chiamata (LcsCdr) e il database QoEMetrics condividono la stessa istanza SQL chiamata. è inoltre comune che i due database di monitoraggio si trovano nella stessa SQL del database di archiviazione (LcsLog). L'unico requisito reale con SQL Server istanze è che qualsiasi istanza di SQL Server è limitata ai seguenti:

- Un'istanza del Skype for Business Server back-end 2015. Come regola generale, non è consigliabile collocare il database di monitoraggio nella stessa istanza di SQL o nello stesso computer del database back-end. Sebbene tecnicamente possibile, si esegue il rischio che il database di monitoraggio utilizzi lo spazio su disco necessario per il database back-end.

- Un'istanza del database di registrazione dettagli chiamata.

- Un'istanza del database di qualità dell'esperienza.

- Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database LcsCdr, è necessario configurare più istanze di SQL Server.

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)