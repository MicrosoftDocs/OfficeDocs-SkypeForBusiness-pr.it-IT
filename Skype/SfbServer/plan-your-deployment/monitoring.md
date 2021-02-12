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

**Riepilogo:** Leggere questo argomento durante la pianificazione del servizio di monitoraggio in Skype for Business Server.

Il servizio di monitoraggio in Skype for Business Server consente agli amministratori di raccogliere dati di utilizzo e qualità per le sessioni di comunicazione che si svolgono nell'organizzazione, che consente loro di identificare tendenze e problemi. Il monitoraggio continuo della distribuzione consente di rilevare i problemi in anticipo e di mantenere soddisfatti gli utenti dell'organizzazione.

Il monitoraggio in Skype for Business Server non richiede un ruolo del server separato (come nelle versioni precedenti di Lync); il servizio di monitoraggio è invece incorporato in ogni Front End Server. Il monitoraggio non è abilitato per impostazione predefinita in Skype for Business Server. Questo articolo consente di determinare se abilitare il monitoraggio durante o dopo la configurazione iniziale di Skype for Business Server e quali risorse SQL saranno necessarie per supportare le attività di monitoraggio. Se non si è sicuri di cosa sia o non sia monitorato e di come il monitoraggio possa essere utile, vedere [Nozioni di base sul monitoraggio.](monitoring.md#Basics) Per iniziare il processo di pianificazione, passare [a Definire i requisiti per il monitoraggio.](monitoring.md#requirements) Per ulteriori dettagli sui requisiti SQL per il monitoraggio, vedere SQL [requisiti per il monitoraggio.](monitoring.md#topologies)

## <a name="basics-about-monitoring"></a>Nozioni di base sul monitoraggio
<a name="Basics"> </a>

Una sessione è un termine generico per la connessione di un utente a:

- Conferenza

- Strumento di conferenza come Audio/Video o Condivisione applicazioni

- Un altro utente tramite una conversazione peer-to-peer come la messaggistica istantanea o una chiamata audio

> [!NOTE]
> Skype for Business Server tiene traccia delle informazioni su ogni sessione: chi ha chiamato; quali endpoint sono stati usati nella sessione; per quanto tempo è durata la sessione; qual era la qualità percepita della sessione; E così via. Skype for Business Server non registra e archivia la chiamata effettiva. Sono incluse le sessioni di messaggistica istantanea: anche se Skype for Business Server registra informazioni sulle sessioni di messaggistica istantanea, non mantiene un record di ogni messaggio istantaneo inviato durante la sessione.

Le informazioni dettagliate sulle chiamate di base raccolte da Skype for Business Server per ogni sessione possono essere utilizzate per:

- **Analisi del rendimento dell'investimento (ROI, Return on Investment).** Gli amministratori possono confrontare i dati di utilizzo con dati simili raccolti per il sistema di telefonia precedente per mostrare risparmi sui costi e giustificare la distribuzione di Skype for Business Server.

- **Gestione dell'inventario dei dispositivi**. Le informazioni sulla gestione delle risorse consentono agli amministratori di identificare i vecchi dispositivi ancora in uso che devono essere sostituiti e di identificare i dispositivi costosi inutilizzati o non utilizzati.

- **Help Desk.** I dati relativi alla risoluzione dei problemi consentono ai tecnici del supporto tecnico di determinare il motivo per cui la chiamata di un utente non è riuscita, senza dover raccogliere log lato server o client. Queste informazioni possono essere facilmente accessibili e comprese dal personale di supporto che non ha una conoscenza approfondita tecnica del client Skype for Business e di Skype for Business Server.

- **Risoluzione dei problemi di sistema**. Gli amministratori hanno la possibilità di rilevare i principali problemi che possono impedire agli utenti finali di eseguire attività di base come partecipare a una conferenza, eseguire una chiamata o inviare un messaggio istantaneo.

Il monitoraggio fornisce anche un meccanismo che consente agli endpoint SIP (come Skype for Business) di fornire informazioni sulla risoluzione dei problemi a cui l'amministratore non avrebbe altrimenti accesso:

- **Metriche che influiscono sulla qualità**. Queste metriche trattano la trasmissione effettiva della chiamata stessa; forniscono una sorta di viaggio mentre la chiamata attraversa la rete. Queste metriche (che includono elementi come perdita di pacchetti, instabilità e tempi di andata e ritorno) forniscono informazioni su cosa è successo alla chiamata dal momento in cui ha lasciato l'endpoint di una persona al momento in cui è arrivato all'endpoint dell'altra persona.

- **Problemi segnalati all'utente finale**. Queste metriche includono notifiche di scarsa qualità che Skype for Business presenta agli utenti finali nei casi in cui sono troppo lontani da un microfono, parlano troppo piano, hanno una connessione di rete scadente o stanno riscontrando una qualità scarsa perché un altro programma sul computer sta consumando le risorse disponibili.

- **Informazioni sull'ambiente**. Queste metriche offrono dati dettagliati su aspetti che influiscono sulla qualità delle chiamate, come il tipo di microfono e altoparlanti in uso, se l'utente è connesso tramite VPN e se l'utente sta utilizzando una connessione wireless.

Al termine di ogni chiamata, gli endpoint conformi a SIP trasmettono queste informazioni al Front End Server che ha facilitato la chiamata. Non è necessario eseguire alcuna operazione per fare in modo che gli endpoint trasmettano tali informazioni, perché questo comportamento è incorporato nel protocollo SIP. Se si desidera raccogliere e archiviare tali informazioni, tuttavia, è necessario installare e abilitare il monitoraggio. In questo modo, le informazioni sulle chiamate vengono raccolte dagli agenti in esecuzione nel Front End Server e inoltrate a una coppia di database di SQL Server. Il servizio di monitoraggio (sotto forma di "agenti di raccolta dati unificati") è collocato in tutti i Front End Server.

## <a name="define-your-requirements-for-monitoring"></a>Definire i requisiti per il monitoraggio
<a name="requirements"> </a>

Esistono ancora diversi problemi chiave che devono essere risolti prima di iniziare a installare e configurare il monitoraggio con Skype for Business Server:

 **Quando si desidera installare il monitoraggio?** Il monitoraggio può essere installato e configurato contemporaneamente all'installazione e alla configurazione di Skype for Business Server; La Distribuzione guidata di Skype for Business Server offre l'opportunità di associare i pool Front End a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo l'installazione di Skype for Business Server stesso; A tale scopo, è possibile utilizzare Generatore di topologie per associare i pool e i server Front End a un database di monitoraggio e quindi pubblicare la topologia modificata.

Tenere presente che è SQL Server essere installato e configurato prima di distribuire e configurare il monitoraggio. Tuttavia, è necessario distribuire solo SQL Server se stesso; i database di monitoraggio verranno creati automaticamente quando si pubblica la topologia di Skype for Business Server.

 **Che tipo di dati si desidera monitorare?** Skype for Business Server consente di monitorare due tipi generali di dati: i dati di registrazione dettagli chiamata (CDR) e i dati QoE (Quality of Experience). La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle funzionalità di Skype for Business Server, ad esempio le chiamate telefoniche VoIP( Voice over IP). messaggistica istantanea; trasferimenti di file; audio/video (A/V) conferencing; e le sessioni di condivisione applicazioni. Queste informazioni consentono di sapere quali funzionalità di Skype for Business Server sono in uso (e quali non lo sono) e forniscono anche informazioni su quando queste funzionalità vengono utilizzate. I dati sulla qualità dell'esperienza consentono di registrare la qualità delle chiamate audio e video effettuate nell'organizzazione, ad esempio il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti).

Se si sceglie di abilitare il monitoraggio in Skype for Business Server, è possibile abilitare sia il monitoraggio CDR che il monitoraggio QoE oppure è possibile scegliere di abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Si supponga, ad esempio, che gli utenti utilizzino solo la messaggistica istantanea e i trasferimenti di file e non esemplino chiamate audio o video. In tal caso, potrebbe esserci poco motivo per abilitare il monitoraggio QoE. Analogamente, Skype for Business Server facilita l'abilitazione e la disabilitazione del monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, è possibile scegliere di distribuire il monitoraggio, ma inizialmente lasciare disabilitato il monitoraggio QoE. Se gli utenti iniziano a verificarsi problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e utilizzare tali dati per risolvere tali problemi.

Non esiste alcun vantaggio (o svantaggio) particolare per l'installazione del monitoraggio contemporaneamente all'installazione di Skype for Business Server e dell'installazione del monitoraggio dopo l'installazione di Skype for Business Server. L'unico punto da tenere presente è che, prima di installare il monitoraggio, è necessario selezionare un computer in cui ospitare l'archivio di monitoraggio back-end e che una versione supportata di SQL Server deve essere installata e configurata in tale computer prima di poter utilizzare tale computer per il monitoraggio. Se hai già installato SQL Server in un computer e il computer è pronto per l'uso, puoi installare il monitoraggio contemporaneamente all'installazione di Skype for Business Server. Se non si dispone di un computer back-end pronto, è possibile procedere all'installazione di Skype for Business Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

 **Quanti database di monitoraggio back-end sono necessari?** È stato stimato che un database collocato sia per il monitoraggio che per l'archiviazione poteva supportare 240.000 utenti di Skype for Business Server. Inoltre, un singolo database di monitoraggio può essere utilizzato da più pool Front End; Se nell'organizzazione sono presenti tre pool Front End, è possibile associare tutti e tre i pool allo stesso archivio back-end.

Per molte organizzazioni, la capacità dei database non sarà il fattore determinante per determinare il numero di database di monitoraggio back-end che saranno necessari. Al contrario, una considerazione più importante potrebbe essere la velocità di rete. Si supponga di disporre di tre pool Front End, ma uno di tali pool si trova in una connessione di rete lenta. In tal caso, è possibile utilizzare due database di monitoraggio: un database per la gestione dei due pool con una buona connessione di rete e un database separato per la gestione del pool con la connessione di rete più lenta.

È inoltre necessario prendere in considerazione che Skype for Business Server supporta l'uso di database mirror. Il "mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede in un server diverso. Ogni volta che i dati vengono scritti in un database primario, gli stessi dati vengono scritti anche nel database mirror. Se il database primario non riesce o diventa in altro modo non disponibile, è possibile eseguire il "failover" nel database mirror utilizzando un semplice comando di PowerShell di Skype for Business Server. Ad esempio:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Questo è importante per scopi di pianificazione semplicemente perché il mirroring richiede il doppio del numero necessario di database: oltre a ogni database primario sarà necessario un secondo database per fungere da mirror.

 **I siti di Skype for Business Server necessitano di configurazioni di monitoraggio personalizzate?** Quando si installa Skype for Business Server, si installano anche raccolte globali di impostazioni di configurazione cdr e QoE; Queste raccolte globali offrono la possibilità di applicare le stesse impostazioni cdr e QoE all'intera organizzazione. In molti casi, sarà sufficiente: spesso si desidera, ad esempio, che il monitoraggio cdR sia abilitato per tutti gli utenti.

È tuttavia possibile che in alcuni casi si desideri applicare impostazioni diverse a siti diversi. Ad esempio, è possibile che si desideri utilizzare sia il monitoraggio CDR che il monitoraggio QoE nel sito Redmond, ma utilizzare solo il monitoraggio cdr nel sito dublinese. Analogamente, è possibile conservare i dati di monitoraggio per 60 giorni nel sito Redmond, ma è necessario mantenere questo tipo di dati solo per 30 giorni nel sito di Dublino. Skype for Business Server consente di creare raccolte separate di impostazioni di configurazione cdr e QoE nell'ambito del sito; che consente di gestire ogni sito in modo diverso. Ciò include sia l'abilitazione che la disabilitazione del monitoraggio, nonché la configurazione delle impostazioni di gestione, ad esempio la durata della conservazione dei dati.

Tenere presente che è possibile prendere questa decisione prima di distribuire il monitoraggio o dopo aver distribuito il monitoraggio. Ad esempio, è possibile distribuire il monitoraggio e quindi gestire l'intera organizzazione utilizzando le impostazioni globali. Se in seguito si cambia idea, è possibile creare una raccolta separata di impostazioni per, ad esempio, il sito Redmond e quindi utilizzarle per gestire il monitoraggio per Redmond. Le impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale. Se si cambia idea di nuovo, è sufficiente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale di impostazioni verrà applicata automaticamente a tale sito.

## <a name="sql-requirements-for-monitoring"></a>SQL per il monitoraggio
<a name="topologies"> </a>

Gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni Front End Server quando si abilita il monitoraggio. Per le versioni supportate di SQL Server e altri dettagli, vedere [Requisiti server per Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

I dati di monitoraggio possono condividere SQL Server'istanza con altri tipi di dati. In genere, il database di registrazione dettagli chiamata (LcsCdr) e il database QoEMetrics (QoEMetrics) condividono la stessa istanza SQL chiamata; è inoltre comune che i due database di monitoraggio si presentino nella stessa istanza SQL del database di archiviazione (LcsLog). L'unico requisito reale con SQL Server istanze è che qualsiasi istanza di SQL Server è limitata ai seguenti:

- Un'istanza del database back-end di Skype for Business Server 2015. Come regola generale, non è consigliabile collocare il database di monitoraggio nella stessa istanza di SQL o nello stesso computer del database back-end. Anche se tecnicamente possibile, si rischia che il database di monitoraggio utilizzi lo spazio su disco necessario per il database back-end.

- Un'istanza del database di registrazione dettagli chiamata.

- Un'istanza del database di qualità dell'esperienza.

- Un'istanza del database di archiviazione.

In altre parole, non è possibile avere due istanze del database LcsCdr nella stessa istanza di SQL Server. Se sono necessarie più istanze del database LcsCdr, è necessario configurare più istanze di SQL Server.

## <a name="see-also"></a>Vedere anche


[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
