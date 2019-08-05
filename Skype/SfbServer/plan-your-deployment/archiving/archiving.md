---
title: Pianificare l'archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: "Riepilogo: leggere questo argomento per informazioni su come pianificare l'archiviazione in Skype for Business Server."
ms.openlocfilehash: 9d24457d8345aa6b496489b68347a98c069abc69
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195933"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Pianificare l'archiviazione in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare l'archiviazione in Skype for Business Server.
  
Le aziende e le altre organizzazioni sono soggette a un numero crescente di normative di settore e governative che richiedono il mantenimento di specifici tipi di comunicazioni. Se l'organizzazione ha requisiti di questo tipo, è possibile usare l'archiviazione in Skype for Business Server per archiviare le comunicazioni di messaggistica istantanea e di conferenza (riunione) per supportare alcuni requisiti di conformità.
  
## <a name="archiving-components"></a>Archiviazione di componenti

Skype for Business Server usa i seguenti componenti di archiviazione:
  
- **Agenti di archiviazione**. Gli agenti di archiviazione (noti anche come agenti di raccolta dati unificati) vengono installati e attivati automaticamente in ogni pool Enterprise Edition front-end e Standard Edition Server. Anche se gli agenti di archiviazione vengono attivati automaticamente, nessun messaggio viene effettivamente acquisito finché l'archiviazione non viene abilitata e configurata in modo appropriato. Per impostazione predefinita, l'archiviazione è disabilitata.
    
- Archiviazione **dei dati archiviati**. L'archiviazione dei dati per Skype for Business Server può essere implementata come database di SQL Server di Skype for Business Server oppure, se si dispone di una distribuzione di Exchange, integrata con lo spazio di archiviazione di Exchange. 
    
L'archiviazione richiede anche l'archiviazione dei file, ma l'archiviazione usa lo stesso spazio di archiviazione dei file del front end server o del server Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinare i requisiti delle organizzazioni per l'archiviazione

Per implementare l'archiviazione, è necessario decidere come soddisfare i requisiti dell'organizzazione per l'archiviazione determinando le operazioni seguenti:
  
- **Opzione di archiviazione da usare**. È possibile implementare lo spazio di archiviazione in due modi o utilizzare una combinazione di entrambi:
    
  - **Archiviazione di Exchange.** Se si dispone di una distribuzione di Exchange, è possibile integrare Skype for Business Server e l'archiviazione di Exchange in modo che i dati archiviati in Skype for Business Server e Exchange vengano archiviati insieme in Exchange. Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate in Exchange Server usano lo spazio di archiviazione di Exchange per i dati archiviati, ma solo se le cassette postali sono state messe sul posto. Per impostazione predefinita, l'integrazione di Microsoft Exchange non è abilitata.
    
  - **Archiviazione di Skype for Business Server.** Se si hanno utenti non residenti in Exchange o che non hanno inserito le cassette postali sul posto o se non si vuole usare l'integrazione di Microsoft Exchange per uno o tutti gli utenti della distribuzione, è possibile distribuire i database di archiviazione di Skype for Business Server tramite S Server QL.
    
- **Quando distribuire l'archiviazione**. Puoi distribuire l'archiviazione come parte della distribuzione iniziale di Skype for Business Server oppure puoi aggiungerla a una distribuzione esistente. Per usare lo spazio di archiviazione di archiviazione di Skype for Business Server (database di SQL Server), è possibile usare generatore di topologie per aggiungere i database alla topologia e quindi pubblicare di nuovo la topologia. Se tutti gli utenti sono ospitati in Exchange e le cassette postali vengono posizionate sul posto, non è necessario aggiornare la topologia, ma è sufficiente abilitare l'integrazione di Microsoft Exchange per archiviare i dati archiviati in Exchange. 
    
- **I siti e gli utenti dell'organizzazione richiedono l'archiviazione**. È possibile configurare le impostazioni di archiviazione per l'intera organizzazione e, facoltativamente, per siti specifici, pool, utenti e gruppi di utenti.
    
- **Quali contenuti devono essere archiviati**. Se si specifica l'archiviazione a livello globale o per siti e utenti specifici, in ognuno di questi livelli si specifica se abilitare i tipi di contenuto seguenti: 
    
  - Messaggi istantanei peer-to-peer
    
  - Conferenze (riunioni), che sono messaggi istantanei a più parti
    
  - Contenuto della conferenza, incluso il contenuto caricato, ad esempio gli stampati, e il contenuto correlato agli eventi (ad esempio, partecipazione, uscita, caricamento della condivisione e modifica della visibilità)
    
  - Lavagne e sondaggi condivisi durante una conferenza
    
- **Quali contenuti non possono essere archiviati**. Non è possibile archiviare i tipi di contenuto seguenti: 
    
  - Trasferimenti di file peer-to-peer
    
  - Audio/video per i messaggi istantanei e le conferenze peer-to-peer
    
  - Condivisione di desktop e applicazioni per i messaggi istantanei e le conferenze peer-to-peer
    
    Anche Skype for Business Server non archivia le conversazioni di chat persistenti. Per archiviare le conversazioni di chat persistenti, è necessario abilitare e configurare il servizio di conformità, che è un componente che può essere distribuito con il server di chat persistente. Per informazioni dettagliate, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
    
- **Quanto tempo devono essere conservati i materiali archiviati**. Il database di archiviazione non è progettato per la conservazione a lungo termine e Skype for Business Server non offre una soluzione di ricerca e-individuazione per i dati archiviati, quindi i dati devono essere spostati in un altro spazio di archiviazione. Skype for Business Server offre uno strumento di esportazione della sessione che puoi usare per esportare i dati archiviati e che crea trascrizioni ricercabili dei dati archiviati. 
    
     Per i criteri globali e per ogni criterio di sito e utente creato, è possibile specificare quando eliminare i dati archiviati ed esportati. Per altre informazioni sull'eliminazione dei dati, vedere [gestire l'eliminazione di dati archiviati in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Per altre informazioni sull'uso dello strumento di esportazione della sessione, vedere [esportare dati archiviati in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Se archiviare comunicazioni interne o esterne**. È possibile abilitare l'archiviazione per le comunicazioni interne (comunicazioni tra utenti interni), le comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna) o entrambe. Puoi specificare queste opzioni per l'intera organizzazione oppure puoi specificarle per siti e pool specifici. Per impostazione predefinita, nessuna opzione è abilitata.
    
    > [!NOTE]
    > Il controllo dell'archiviazione per comunicazioni interne o esterne è disponibile solo per i criteri di Skype for business. Per l'archiviazione integrata in Exchange, le comunicazioni interne ed esterne vengono archiviate o non archiviate. 
  
- **Se implementare la modalità critica**. Se l'archiviazione è un requisito per l'organizzazione, la configurazione della modalità critica bloccherà le sessioni di messaggistica istantanea e di conferenza in caso di errore di Skype for Business Server che impedirebbe l'archiviazione. Ad esempio: 
    
  - Un problema con il servizio di archiviazione di Skype for Business Server. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - Una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica istantanea che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Scegliere l'archiviazione delle opzioni di distribuzione e configurazione

L'archiviazione viene automaticamente installata in ogni server front-end quando si distribuisce il server, ma l'archiviazione non è abilitata finché non viene configurata. La modalità di configurazione dell'archiviazione dipende dalla modalità di distribuzione. È possibile distribuire l'archiviazione in uno dei modi seguenti:
  
- Usare lo spazio di archiviazione di Microsoft Exchange
    
- Usare lo spazio di archiviazione di Skype for Business Server
    
> [!NOTE]
> Se si implementano entrambi i database di archiviazione di Skype for Business Server e si Abilita l'integrazione di Microsoft Exchange, i criteri di Exchange eseguono l'override dei criteri di archiviazione di Skype for Business Server, ma solo per gli utenti residenti in Exchange e hanno inserito le cassette postali Blocco sul posto. L'archiviazione di Skype for business dipende dal criterio di blocco sul posto di Microsoft Exchange. 
  
Se si distribuisce l'archiviazione per un pool Front-end o un server Standard Edition, è consigliabile abilitarlo per tutti gli altri pool Front end e i server Standard Edition nella distribuzione. Se l'archiviazione non è abilitata nel pool in cui è ospitata una conversazione o una riunione, è possibile che non vengano archiviati tutti i dati della conferenza. L'archiviazione continuerà a funzionare anche per i messaggi di messaggistica istantanea, ma il contenuto e gli eventi di conferenza potrebbero non essere archiviati.
  
> [!NOTE]
> Per abilitare la delega delle attività amministrative mantenendo gli standard di sicurezza dell'organizzazione, Skype for Business Server usa il controllo di accesso basato sui ruoli (RBAC). Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti i ruoli amministrativi predefiniti. Per configurare i criteri di archiviazione e le configurazioni di Skype for business, l'utente deve essere assegnato al ruolo CsArchivingAdministrator, a meno che la configurazione non venga eseguita direttamente nel server in cui è distribuita l'archiviazione, anziché in remoto da un altro computer ). Per un elenco dei diritti utente, le autorizzazioni e i ruoli necessari per l'archiviazione della distribuzione, vedere [distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Se si usa l'integrazione di Microsoft Exchange, la configurazione dei criteri di Exchange richiede diritti e autorizzazioni di amministratore appropriati. Per informazioni dettagliate, vedere la documentazione di Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange

 Se si sceglie integrazione di Microsoft Exchange, è possibile usare i criteri e le configurazioni di Exchange per controllare l'archiviazione di Skype for Business Server. È possibile configurare l'opzione di integrazione di Microsoft Exchange a livello globale, livello di sito e livello di pool. Se la distribuzione include più foreste, è necessario sincronizzare le impostazioni tra Skype for Business Server ed Exchange. Sarà necessario determinare:
  
- Se archiviare messaggi istantanei, servizi di conferenza o entrambi
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server 
    
- Selezione dell'opzione di integrazione di Microsoft Exchange per l'uso di Exchange per l'archiviazione dei dati archiviati
    
Per informazioni su come configurare i criteri e le impostazioni per il blocco sul posto di Exchange per supportare l'archiviazione, vedere la documentazione del prodotto Exchange.
  
### <a name="skype-for-business-server-storage"></a>Archiviazione di Skype for Business Server

Se si sceglie l'archiviazione di Skype for Business Server, è possibile usare i criteri di archiviazione e le configurazioni di Skype for Business Server per controllare l'abilitazione e l'implementazione dell'archiviazione. Lo spazio di archiviazione di Skype for Business Server usa i database di SQL Server, quindi dovrai aggiungere i database di SQL Server appropriati alla topologia, quindi configurare i criteri di archiviazione. 
  
### <a name="add-storage-databases-to-your-topology"></a>Aggiungere database di archiviazione alla topologia

Quando si aggiungono database di archiviazione di SQL Server alla topologia, è possibile scegliere di collocare i database di archiviazione con uno degli elementi seguenti:
  
- Database di monitoraggio
    
- Database back-end di un pool di front-end Enterprise Edition
    
> [!NOTE]
> Il server che ospita il database di archiviazione può ospitare altri database. Tuttavia, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può essere molto elevato. Per questo motivo, non è consigliabile collocare il database di archiviazione con il database back-end. 
  
Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza di SQL per uno o tutti i database oppure è possibile usare un'istanza SQL separata per ogni database, con le operazioni seguenti limitazione: ogni istanza SQL può contenere solo un database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.
  
Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere Nozioni di base sulla topologia di [Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Per informazioni dettagliate sull'aggiornamento della topologia per includere i database di archiviazione, vedere [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinare le opzioni di archiviazione e i criteri degli utenti

Sarà necessario determinare:
  
- Se abilitare o disabilitare l'archiviazione per le comunicazioni interne ed esterne
    
- Se archiviare messaggi istantanei, servizi di conferenza o entrambi
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server 
    
- Se abilitare i criteri per utenti e gruppi specifici
    
Le opzioni di archiviazione di Skype for Business Server possono essere specificate ai livelli seguenti. 
  
- **Opzione livello globale**. Questa è la configurazione di archiviazione predefinita e si applica all'intera distribuzione. Viene creato quando si distribuisce Skype for Business Server e, per impostazione predefinita, disattiva l'archiviazione per le comunicazioni interne ed esterne. Non è possibile eliminare questa opzione. Se si sceglie l'opzione Elimina, l'opzione globale viene reimpostata sulle impostazioni predefinite.
    
- **Opzioni livello sito**. È possibile abilitare o disabilitare l'archiviazione per uno o più siti specifici creando e configurando un'opzione di archiviazione a livello di sito per il sito. Puoi eliminare qualsiasi opzione di archiviazione a livello di sito creata. Un'opzione di archiviazione a livello di sito sostituisce l'opzione globale, ma solo per il sito specificato nell'opzione. 
    
    Ad esempio, se si Abilita l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale e si crea una configurazione del sito in cui si disattiva l'archiviazione per le comunicazioni esterne, verranno archiviati solo le comunicazioni interne per il sito. Per un altro esempio, se si Abilita l'archiviazione per la messaggistica istantanea solo nella configurazione globale e si crea una configurazione del sito in cui è possibile abilitare l'archiviazione sia per la messaggistica istantanea che per i servizi di conferenza, i servizi di conferenza verranno archiviati solo per il sito e non per il resto della organizzazione.
    
- **Opzioni**per il livello del pool. È possibile specificare le impostazioni di archiviazione per uno o più pool specifici creando e configurando una configurazione a livello di pool per il singolo pool. Una configurazione di archiviazione a livello di pool esiste solo se è stata creata. È possibile modificare ed eliminare qualsiasi configurazione di archiviazione a livello di pool. Una configurazione di archiviazione a livello di pool sostituisce la configurazione globale e qualsiasi configurazione di archiviazione del sito che potrebbe essere stata creata. 
    
    Supponiamo ad esempio di abilitare l'archiviazione per la messaggistica istantanea solo nella configurazione globale, quindi creare una configurazione a livello di sito in cui abilitare l'archiviazione sia per la messaggistica istantanea che per i servizi di conferenza e quindi creare una configurazione a livello di pool in cui è possibile abilitare l'archiviazione solo per la messaggistica istantanea. . Le comunicazioni verranno archiviate per la messaggistica istantanea e la conferenza per tutti gli utenti del sito, ad eccezione degli utenti ospitati nel pool specificato nella configurazione a livello di pool. Per tutti gli altri utenti dell'organizzazione, l'archiviazione verrà abilitata solo per la messaggistica istantanea.
    
- **Criteri di archiviazione degli utenti**. È possibile abilitare o disabilitare l'archiviazione per uno o più utenti e gruppi di utenti specifici creando, configurando e applicando criteri di archiviazione a livello di utente per gli utenti e i gruppi di utenti specificati. Puoi eliminare qualsiasi criterio di archiviazione a livello di utente che crei e puoi modificare gli utenti e il gruppo di utenti a cui si applicano i criteri di archiviazione. Un criterio di archiviazione a livello di utente esegue l'override dei criteri globali e di tutti i criteri del sito, ma solo per gli utenti e gruppi di utenti a cui è applicato il criterio. 
    
    Ad esempio, supponiamo di disabilitare l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale, creare un criterio a livello di sito in cui abilitare l'archiviazione per le comunicazioni interne ed esterne e quindi creare un criterio a livello di utente in cui si disabilitare l'archiviazione per le comunicazioni esterne. Le comunicazioni verranno archiviate sia per le comunicazioni esterne che interne per tutti gli utenti del sito, ad eccezione degli utenti a cui si applicano i criteri a livello di utente: per questi utenti verranno archiviati solo le comunicazioni interne.
    
Per informazioni dettagliate su come configurare le configurazioni di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Per informazioni dettagliate sulla gestione dell'archiviazione dopo la distribuzione, vedere [gestire l'archiviazione in Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Strumenti di configurazione dell'archiviazione

 Puoi controllare la maggior parte delle opzioni di archiviazione usando il pannello di controllo di Skype for Business Server. Tuttavia, esistono alcune opzioni disponibili solo con Skype for Business Server Management Shell. Queste opzioni includono l'archiviazione di messaggi duplicati ed esportazione di dati archiviati. Per altre informazioni sull'uso del pannello di controllo di Skype for Business Server e di Skype for Business Server Management Shell per gestire i criteri di archiviazione, vedere [gestire l'archiviazione in Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accedere ai dati archiviati

L'accesso ai dati archiviati dipende dalla posizione in cui sono archiviati i dati: 
  
- **Archiviazione di Microsoft Exchange**. Se si sceglie l'opzione di integrazione di Exchange, Skype for Business Server deposita il contenuto dell'archiviazione in Exchange Store per tutti gli utenti ospitati in Exchange e che hanno inserito le cassette postali sul posto. I dati archiviati vengono archiviati nella cartella elementi ripristinabili delle cassette postali degli utenti, che in genere sono invisibili agli utenti e che possono essere cercati solo dagli utenti con un ruolo di **Gestione individuazione** di Exchange. Exchange consente la ricerca e l'individuazione federate, insieme a SharePoint, se è distribuita. Per ulteriori informazioni sull'archiviazione, la conservazione e l'individuazione dei dati archiviati in Exchange, vedere la documentazione di Exchange e SharePoint.
    
- **Archiviazione di archiviazione di Skype for Business Server**. Se si configurano i database di archiviazione di Skype for Business Server, Skype for Business Server archivia i contenuti archiviati nei database di archiviazione di Skype for Business Server per tutti gli utenti non residenti in Exchange e che non hanno inserito le cassette postali sul posto. Questi dati non sono ricercabili, ma possono essere esportati in formati ricercabili con altri strumenti. Per informazioni dettagliate sull'esportazione dei dati archiviati nei database di archiviazione, vedere [esportare dati archiviati in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Per altre informazioni

Per altre informazioni sull'archiviazione, vedere gli argomenti seguenti:
  
- [Distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gestire l'archiviazione in Skype for Business Server](../../manage/archiving/archiving.md)
    
Per altre informazioni su come collaborare con Skype for Business Server e Exchange, Vedi [pianificare l'integrazione di Skype for business e Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

