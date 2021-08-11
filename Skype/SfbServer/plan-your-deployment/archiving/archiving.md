---
title: Pianificare l'archiviazione in Skype for Business Server
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
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: "Riepilogo: leggere questo argomento per informazioni su come pianificare l'archiviazione in Skype for Business Server."
ms.openlocfilehash: 87a408bd4decfcd4f1f0d1ca7806391ecb3900e8821031efec116d86a0847c3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331128"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Pianificare l'archiviazione in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare l'archiviazione in Skype for Business Server.
  
Grandi aziende e altre organizzazioni sono soggette a un numero crescente di norme di settore e legislative che richiedono la conservazione di specifici tipi di comunicazioni. Se l'organizzazione ha tali requisiti, è possibile utilizzare l'archiviazione in Skype for Business Server per archiviare le comunicazioni di messaggistica istantanea e conferenza (riunioni) per supportare alcuni dei requisiti di conformità.
  
## <a name="archiving-components"></a>Componenti di archiviazione

Skype for Business Server vengono utilizzati i componenti di archiviazione seguenti:
  
- **Agenti di archiviazione**. Gli agenti di archiviazione, noti anche come agenti di raccolta dati unificati, vengono installati e attivati automaticamente edizione Enterprise ogni pool Front End e edizione Standard Server. Anche se gli agenti di archiviazione vengono attivati automaticamente, nessun messaggio viene effettivamente acquisito finché l'archiviazione non viene abilitata e configurata in modo appropriato. Per impostazione predefinita, l'archiviazione è disabilitata.
    
- **Archivio dati di archiviazione**. L'archiviazione dei Skype for Business Server può essere implementata come database Skype for Business Server SQL Server oppure, se si dispone di una distribuzione Exchange, integrata con Exchange archiviazione. 
    
L'archiviazione richiede anche l'archiviazione dei file, ma l'archiviazione utilizza lo stesso archivio file dei Front End Server o edizione Standard Server.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinare i requisiti dell'organizzazione per l'archiviazione

Per implementare l'archiviazione, è necessario decidere come soddisfare i requisiti dell'organizzazione per l'archiviazione determinando quanto segue:
  
- **Quale opzione di archiviazione utilizzare**. È possibile implementare l'archiviazione in due modi o utilizzare una combinazione di entrambi:
    
  - **Exchange archiviazione.** Se si dispone di una distribuzione Exchange, è possibile integrare l'archiviazione Skype for Business Server e Exchange in modo che i dati archiviati di Skype for Business Server e Exchange siano archiviati insieme in Exchange. Se si abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate nel Exchange Server utilizzano l'archiviazione Exchange per i dati archiviati, ma solo se le cassette postali sono state In-Place archiviazione. Per impostazione predefinita, l'Exchange microsoft non è abilitata.
    
  - **Skype for Business Server archiviazione.** Se si dispone di utenti che non sono ospitati in Exchange o che non hanno avuto le proprie cassette postali messe In-Place blocco o se non si desidera utilizzare l'integrazione di Microsoft Exchange per uno o tutti gli utenti nella distribuzione, è possibile distribuire i database di archiviazione Skype for Business Server utilizzando SQL Server.
    
- **Quando distribuire l'archiviazione**. È possibile distribuire l'archiviazione come parte della distribuzione Skype for Business Server o aggiungerla a una distribuzione esistente. Per utilizzare Skype for Business Server di archiviazione (SQL Server database), utilizzare Generatore di topologie per aggiungere i database alla topologia e quindi pubblicare di nuovo la topologia. Se tutti gli utenti sono ospitati su Exchange e dispongono di cassette postali di archiviazione In-Place, non è necessario aggiornare la topologia, ma solo abilitare l'integrazione di Microsoft Exchange per archiviare i dati archiviati in Exchange. 
    
- **Quali siti e utenti dell'organizzazione richiedono l'archiviazione**. È possibile configurare le impostazioni di archiviazione per l'intera organizzazione e, facoltativamente, per siti, pool, utenti e gruppi di utenti specifici.
    
- **Contenuto da archiviare.** Se si specifica l'archiviazione a livello globale o per siti e utenti specifici, a ognuno di questi livelli si specifica se abilitare i tipi di contenuto seguenti: 
    
  - Messaggi istantanei peer-to-peer
    
  - Conferenze (riunioni), che corrispondono in pratica a messaggi istantanei tra più utenti
    
  - Contenuto di conferenze, compreso il contenuto caricato (ad esempio, stampati) e correlato agli eventi (ad esempio, accesso, uscita, caricamento in condivisione e modifiche della visibilità)
    
  - Lavagne e sondaggi condivisi durante una conferenza
    
- **Contenuto che non può essere archiviato.** Non è possibile archiviare i tipi di contenuto seguenti: 
    
  - Trasferimenti di file peer-to-peer
    
  - Audio e video per messaggi istantanei peer-to-peer e conferenze
    
  - Condivisione di desktop e applicazioni per messaggi istantanei peer-to-peer e conferenze
    
    Skype for Business Server inoltre non archivia le conversazioni di Persistent Chat. Per archiviare le conversazioni di Persistent Chat, è necessario abilitare e configurare il servizio conformità, che è un componente che può essere distribuito con il server Chat persistente. Per informazioni dettagliate, [vedere Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare Persistent Chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
    
- **Per quanto tempo devono essere conservati i materiali archiviati.** Il database di archiviazione non è destinato alla conservazione a lungo termine e Skype for Business Server non fornisce una soluzione di individuazione elettronica (ricerca) per i dati archiviati, quindi i dati devono essere spostati in un altro spazio di archiviazione. Skype for Business Server fornisce uno strumento di esportazione della sessione che è possibile utilizzare per esportare i dati archiviati e che crea trascrizioni ricercabili dei dati archiviati. 
    
     Per il criterio globale e per ogni criterio sito e utente creato, è possibile specificare quando eliminare i dati archiviati ed esportati. Per ulteriori informazioni sull'eliminazione dei dati, vedere [Manage purging of archived data in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Per ulteriori informazioni sull'utilizzo dello strumento di esportazione della sessione, vedere [Export archived data in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Se archiviare le comunicazioni interne o esterne.** È possibile abilitare l'archiviazione per le comunicazioni interne (comunicazioni tra utenti interni), le comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna) o entrambe. È possibile specificare queste opzioni per l'intera organizzazione oppure per siti e pool specifici. Per impostazione predefinita, nessuna delle due opzioni è abilitata.
    
    > [!NOTE]
    > Il controllo dell'archiviazione per le comunicazioni interne o esterne è disponibile solo per Skype for Business criteri. Per Exchange di archiviazione integrata, le comunicazioni interne ed esterne vengono archiviate o non archiviate. 
  
- **Se implementare la modalità critica**. Se l'archiviazione è un requisito per l'organizzazione, la configurazione della modalità critica bloccherà le sessioni di messaggistica istantanea e di conferenza in caso di un Skype for Business Server che impedirebbe l'archiviazione. Ad esempio: 
    
  - Problema con il servizio Skype for Business Server di archiviazione. In questo caso, la messaggistica istantanea è bloccata per gli utenti abilitati per l'archiviazione.
    
  - Condivisione file non disponibile o problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Scegliere le opzioni di distribuzione e configurazione dell'archiviazione

L'archiviazione viene installata automaticamente in ogni Front End Server quando si distribuisce il server, ma l'archiviazione non viene abilitata fino a quando non viene configurata. La modalità di configurazione dell'archiviazione dipende dalla modalità di distribuzione. È possibile distribuire l'archiviazione in uno dei modi seguenti:
  
- Usare Microsoft Exchange storage
    
- Usare l Skype for Business Server di archiviazione
    
> [!NOTE]
> Se si implementano entrambi i database di archiviazione Skype for Business Server e si abilita l'integrazione di Microsoft Exchange, i criteri di Exchange sostituiscono i criteri di archiviazione di Skype for Business Server, ma solo per gli utenti ospitati in Exchange e in cui le cassette postali sono state In-Place archiviazione. Skype for Business'archiviazione dipende dal criterio di blocco Exchange In-Place Microsoft. 
  
Se si distribuisce l'archiviazione per un pool Front End o un edizione Standard Server, è consigliabile abilitarla per tutti gli altri pool Front End e edizione Standard server nella distribuzione. Se l'archiviazione non è abilitata nel pool in cui è ospitata una conversazione o una riunione, tutti i dati della conferenza potrebbero non essere archiviati. L'archiviazione continuerà a funzionare per i messaggi istantanei, ma il contenuto e gli eventi delle conferenze potrebbero non essere archiviati.
  
> [!NOTE]
> Per abilitare la delega delle attività amministrative mantenendo gli standard di sicurezza dell'organizzazione, Skype for Business Server utilizza il controllo degli accessi in base al ruolo (RBAC). Con RBAC, il privilegio amministrativo viene concesso assegnando gli utenti ai ruoli amministrativi predefiniti. Per configurare le configurazioni e i criteri di archiviazione di Skype for Business, l'utente deve essere assegnato al ruolo CsArchivingAdministrator (a meno che la configurazione non venga eseguita direttamente nel server in cui è distribuita l'archiviazione, anziché in remoto da un altro computer). Per un elenco dei diritti utente, delle autorizzazioni e dei ruoli necessari per la distribuzione [dell'archiviazione,](../../deploy/deploy-archiving/deploy-archiving.md)vedere Deploy archiving for Skype for Business Server . 
  
> [!NOTE]
> Se si utilizza l'integrazione Exchange Microsoft, la configurazione dei criteri Exchange richiede autorizzazioni e diritti di amministratore appropriati. Per informazioni dettagliate, vedere la Exchange documentazione. 
  
### <a name="microsoft-exchange-storage"></a>Archiviazione Exchange Microsoft

 Se si sceglie l'integrazione di Microsoft Exchange, è possibile utilizzare Exchange e le configurazioni per controllare l'archiviazione dei Skype for Business Server. È possibile configurare l'opzione di Exchange microsoft a livello globale, a livello di sito e di pool. Se la distribuzione include più foreste, è necessario sincronizzare le impostazioni tra Skype for Business Server e Exchange. Dovrai determinare:
  
- Se archiviare messaggistica istantanea, conferenze o entrambi
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza in caso di Skype for Business Server errore 
    
- Selezione dell'opzione di integrazione di Microsoft Exchange da usare Exchange per l'archiviazione dei dati archiviati
    
Per informazioni su come configurare i criteri e le impostazioni Exchange In-Place di archiviazione per supportare l'archiviazione, vedere la documentazione Exchange prodotto.
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server archiviazione

Se si sceglie di Skype for Business Server archiviazione, è possibile utilizzare Skype for Business Server e le configurazioni di archiviazione per controllare la modalità di a attivazione e implementazione dell'archiviazione. Skype for Business Server'archiviazione utilizza SQL Server database, quindi sarà necessario aggiungere i database SQL Server appropriati alla topologia, quindi configurare i criteri di archiviazione. 
  
### <a name="add-storage-databases-to-your-topology"></a>Aggiungere database di archiviazione alla topologia

Quando si aggiungono SQL Server di archiviazione alla topologia, è possibile scegliere di collocare i database di archiviazione con una delle opzioni seguenti:
  
- Database di monitoraggio
    
- Database back-end di un pool Enterprise Edition Front End
    
> [!NOTE]
> Il server che ospita il database di archiviazione può ospitare altri database. Se, tuttavia, si desidera collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo non è consigliabile collocare il database di archiviazione con il database back-end. 
  
Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile utilizzare una singola istanza di SQL per uno o tutti i database oppure è possibile utilizzare un'istanza di SQL separata per ogni database, con la limitazione seguente: ogni istanza di SQL può contenere solo un singolo database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.
  
Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Per informazioni dettagliate sull'aggiornamento della topologia per includere database di archiviazione, vedere [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinare le opzioni di archiviazione e i criteri utente

Dovrai determinare:
  
- Se abilitare o disabilitare l'archiviazione per le comunicazioni interne ed esterne
    
- Se archiviare messaggistica istantanea, conferenze o entrambi
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza in caso di Skype for Business Server errore 
    
- Se abilitare i criteri per utenti e gruppi specifici
    
Skype for Business Server Le opzioni di archiviazione possono essere specificate ai livelli seguenti. 
  
- **Opzione livello globale**. Questa è la configurazione di archiviazione predefinita e si applica all'intera distribuzione. Viene creato quando si distribuisce Skype for Business Server e, per impostazione predefinita, disabilita l'archiviazione sia per le comunicazioni interne che per le comunicazioni esterne. Non è possibile eliminare questa opzione. Se si sceglie l'opzione di eliminazione, l'opzione globale viene reimpostata alle impostazioni predefinite.
    
- **Opzioni a livello di sito**. È possibile abilitare o disabilitare l'archiviazione per uno o più siti specifici creando e configurando un'opzione di archiviazione a livello di sito per il sito. È possibile eliminare qualsiasi opzione di archiviazione a livello di sito creata. Un'opzione di archiviazione a livello di sito sostituisce l'opzione globale, ma solo per il sito specificato nell'opzione. 
    
    Ad esempio, se si abilita l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale e si crea una configurazione di sito in cui si disabilita l'archiviazione per le comunicazioni esterne, per tale sito verranno archiviate solo le comunicazioni interne. Se ad esempio si abilita l'archiviazione solo per la messaggistica istantanea nella configurazione globale e si crea una configurazione di sito in cui si abilita l'archiviazione sia per la messaggistica istantanea che per le conferenze, le conferenze verranno archiviate solo per il sito e non per il resto dell'organizzazione.
    
- **Opzioni a livello di pool**. È possibile specificare le impostazioni di archiviazione per uno o più pool specifici creando e configurando una configurazione a livello di pool per il singolo pool. Una configurazione di archiviazione a livello di pool esiste solo se viene creata. È possibile modificare ed eliminare qualsiasi configurazione di archiviazione a livello di pool. Una configurazione di archiviazione a livello di pool ha la precedenza sulla configurazione globale e su qualsiasi configurazione di archiviazione siti creata. 
    
    Si supponga, ad esempio, di abilitare l'archiviazione per la messaggistica istantanea solo nella configurazione globale, quindi di creare una configurazione a livello di sito in cui abilitare l'archiviazione sia per la messaggistica istantanea che per le conferenze e quindi di creare una configurazione a livello di pool in cui abilitare l'archiviazione solo per la messaggistica istantanea. Le comunicazioni verranno archiviate sia per la messaggistica istantanea che per le conferenze per tutti gli utenti del sito ad eccezione degli utenti ospitati nel pool specificato nella configurazione a livello di pool. Per tutti gli altri utenti dell'organizzazione, l'archiviazione verrà abilitata solo per la messaggistica istantanea.
    
- **Criteri di archiviazione degli utenti**. È possibile abilitare o disabilitare l'archiviazione per uno o più utenti e gruppi di utenti specifici creando, configurando e applicando criteri di archiviazione a livello di utente per gli utenti e i gruppi di utenti specificati. È possibile eliminare qualsiasi criterio di archiviazione a livello di utente creato e modificare gli utenti e i gruppi di utenti a cui si applica il criterio di archiviazione. I criteri di archiviazione a livello di utente hanno la precedenza sul criterio globale e su tutti i criteri del sito, ma solo per gli utenti e i gruppi di utenti a cui viene applicato il criterio. 
    
    Si supponga, ad esempio, di disabilitare l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale, di creare un criterio a livello di sito in cui abilitare l'archiviazione per le comunicazioni interne ed esterne e quindi di creare un criterio a livello di utente in cui disabilitare l'archiviazione per le comunicazioni esterne. Le comunicazioni verranno archiviate sia per le comunicazioni esterne che interne per tutti gli utenti del sito ad eccezione degli utenti a cui si applica il criterio a livello di utente. Per questi utenti verranno archiviate solo le comunicazioni interne.
    
Per informazioni dettagliate su come configurare le configurazioni di archiviazione iniziali quando si distribuisce [l'archiviazione,](../../deploy/deploy-archiving/deploy-archiving.md)vedere Deploy archiving for Skype for Business Server . Per informazioni dettagliate sulla gestione dell'archiviazione dopo la [distribuzione,](../../manage/archiving/archiving.md)vedere Manage archiving in Skype for Business Server . 
  
## <a name="archiving-configuration-tools"></a>Strumenti di configurazione dell'archiviazione

 Puoi controllare la maggior parte delle opzioni di archiviazione usando il Skype for Business Server pannello di controllo. Tuttavia, esistono alcune opzioni disponibili solo utilizzando Skype for Business Server Management Shell. Queste opzioni includono l'archiviazione dei messaggi duplicati e l'esportazione dei dati archiviati. Per ulteriori informazioni sull'utilizzo del Pannello di controllo di Skype for Business Server e di Skype for Business Server Management Shell per gestire i criteri di archiviazione, vedere [Manage archiving in Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accedere ai dati archiviati

La modalità di accesso ai dati archiviati dipende dalla posizione dei dati stessi: 
  
- **Microsoft Exchange archiviazione**. Se si sceglie l'opzione di integrazione di Exchange, Skype for Business Server deposita il contenuto di archiviazione nell'archivio Exchange per tutti gli utenti ospitati in Exchange e che hanno messo le cassette postali In-Place Archiviazione. I dati archiviati vengono archiviati nella cartella Elementi ripristinabili delle cassette postali degli utenti, in genere invisibile agli utenti, e possono essere ricercati solo dagli utenti con un ruolo gestione individuazione **Exchange.** Exchange la ricerca federata e l'individuazione, insieme SharePoint, se viene distribuita. Per ulteriori informazioni sull'archiviazione, la conservazione e l'individuazione dei dati archiviati in Exchange, vedere la documentazione Exchange e SharePoint.
    
- **Skype for Business Server archiviazione .** Se si configurano database di archiviazione di Skype for Business Server, Skype for Business Server deposita il contenuto di archiviazione nei database di archiviazione di Skype for Business Server per tutti gli utenti non ospitati in Exchange e che non dispongono di cassette postali in archiviazione In-Place. Non è possibile sottoporre questi dati a ricerca, ma è possibile esportarli nei formati di altri strumenti di ricerca. Per informazioni dettagliate sull'esportazione dei dati archiviati nei database di archiviazione, vedere [Export archived data in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sull'archiviazione, vedere i seguenti argomenti:
  
- [Distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gestire l'archiviazione in Skype for Business Server](../../manage/archiving/archiving.md)
    
Per ulteriori informazioni su come Skype for Business Server e Exchange, vedere [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

