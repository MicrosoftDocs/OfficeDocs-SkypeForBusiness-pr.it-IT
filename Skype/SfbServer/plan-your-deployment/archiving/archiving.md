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
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810146"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Pianificare l'archiviazione in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come pianificare l'archiviazione in Skype for Business Server.
  
Grandi aziende e altre organizzazioni sono soggette a un numero crescente di norme di settore e legislative che richiedono la conservazione di specifici tipi di comunicazioni. Se l'organizzazione dispone di tali requisiti, è possibile utilizzare l'archiviazione in Skype for Business Server per archiviare le comunicazioni di messaggistica istantanea e di conferenza (riunioni) per supportare alcuni dei requisiti di conformità.
  
## <a name="archiving-components"></a>Componenti di archiviazione

Skype for Business Server utilizza i seguenti componenti di archiviazione:
  
- **Agenti di archiviazione**. Gli agenti di archiviazione (noti anche come agenti di raccolta dati unificati) sono installati e attivati automaticamente su ogni pool Enterprise Edition front end e server Standard Edition. Anche se gli agenti di archiviazione vengono attivati automaticamente, nessun messaggio viene effettivamente acquisito fino a quando l'archiviazione non è abilitata e configurata in modo appropriato. Per impostazione predefinita, l'archiviazione è disattivata.
    
- **Archivio dati di archiviazione**. L'archiviazione dei dati per Skype for Business Server può essere implementata come database di SQL Server in Skype for Business Server o, se si dispone di una distribuzione di Exchange, integrata con l'archiviazione di Exchange. 
    
L'archiviazione richiede anche l'archiviazione dei file, ma l'archiviazione utilizza lo stesso file di archiviazione dei Front End Server o del server Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Determinare i requisiti dell'organizzazione per l'archiviazione

Per implementare l'archiviazione, è necessario decidere come soddisfare i requisiti dell'organizzazione per l'archiviazione determinando quanto segue:
  
- **Opzione di archiviazione da utilizzare**. È possibile implementare l'archiviazione in uno dei due modi o utilizzare una combinazione di entrambi:
    
  - **Archiviazione di Exchange.** Se si dispone di una distribuzione di Exchange, è possibile integrare Skype for Business Server e l'archiviazione di Exchange in modo che i dati archiviati in Skype for Business Server e Exchange siano archiviati insieme in Exchange. Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate sul server Exchange utilizzano l'archiviazione di Exchange per i dati archiviati, ma solo se le cassette postali sono state inserite In-Place blocco. Per impostazione predefinita, l'integrazione di Microsoft Exchange non è abilitata.
    
  - **Archiviazione di Skype for Business Server.** Se si dispone di utenti che non sono ospitati in Exchange o che non dispongono di cassette postali inserite In-Place o che non si desidera utilizzare l'integrazione di Microsoft Exchange per uno o tutti gli utenti nella distribuzione, è possibile distribuire i database di archiviazione di Skype for Business Server tramite SQL Server.
    
- **Quando si distribuisce l'archiviazione**. È possibile distribuire l'archiviazione come parte della distribuzione iniziale di Skype for Business Server oppure aggiungerla a una distribuzione esistente. Per utilizzare l'archivio di archiviazione di Skype for Business Server (database di SQL Server), è possibile utilizzare Generatore di topologie per aggiungere i database alla topologia e quindi pubblicare di nuovo la topologia. Se tutti gli utenti sono ospitati in Exchange e le cassette postali vengono inserite In-Place, non è necessario aggiornare la topologia, ma è sufficiente abilitare l'integrazione di Microsoft Exchange per archiviare i dati archiviati in Exchange. 
    
- **Quali siti e utenti dell'organizzazione richiedono l'archiviazione**. È possibile configurare le impostazioni di archiviazione per l'intera organizzazione e, facoltativamente, per i siti, i pool, gli utenti e i gruppi di utenti specifici.
    
- **Contenuto che deve essere archiviato**. Se si specifica l'archiviazione a livello globale o per siti e utenti specifici, a ognuno di questi livelli si specifica se abilitare i tipi di contenuto seguenti: 
    
  - Messaggi istantanei peer-to-peer
    
  - Conferenze (riunioni), che corrispondono in pratica a messaggi istantanei tra più utenti
    
  - Contenuto di conferenze, compreso il contenuto caricato (ad esempio, stampati) e correlato agli eventi (ad esempio, accesso, uscita, caricamento in condivisione e modifiche della visibilità)
    
  - Lavagne e sondaggi condivisi durante una conferenza
    
- **Contenuto che non è possibile archiviare**. Non è possibile archiviare i tipi di contenuto seguenti: 
    
  - Trasferimenti di file peer-to-peer
    
  - Audio e video per messaggi istantanei peer-to-peer e conferenze
    
  - Condivisione di desktop e applicazioni per messaggi istantanei peer-to-peer e conferenze
    
    Anche Skype for Business Server non archivia le conversazioni di chat persistente. Per archiviare le conversazioni di chat persistente, è necessario abilitare e configurare il servizio di conformità, che è un componente che può essere distribuito con il server Chat persistente. Per ulteriori informazioni, vedere [Plan for Persistent Chat Server in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
    
- **La durata di conservazione dei materiali archiviati**. Il database di archiviazione non è progettato per la conservazione a lungo termine e Skype for Business Server non fornisce una soluzione e-Discovery (ricerca) per i dati archiviati, pertanto i dati devono essere spostati in un altro archivio. Skype for Business Server fornisce uno strumento di esportazione della sessione che è possibile utilizzare per esportare i dati archiviati e che consente di creare trascrizioni di ricerca dei dati archiviati. 
    
     Per il criterio globale e per ogni sito e criterio utente creato, è possibile specificare quando eliminare i dati archiviati ed esportati. Per ulteriori informazioni sull'eliminazione dei dati, vedere [Manage purging of Archived data in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Per ulteriori informazioni sull'utilizzo dello strumento di esportazione della sessione, vedere [Export Archived data in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Se archiviare le comunicazioni interne o esterne**. È possibile abilitare l'archiviazione per le comunicazioni interne (comunicazioni tra gli utenti interni), le comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna) o entrambe. È possibile specificare queste opzioni per l'intera organizzazione oppure è possibile specificarle per siti e pool specifici. Per impostazione predefinita, nessuna opzione è abilitata.
    
    > [!NOTE]
    > Il controllo dell'archiviazione per le comunicazioni interne o esterne è disponibile solo per i criteri di Skype for business. Per l'archiviazione integrata in Exchange, le comunicazioni interne ed esterne sono archiviate o non archiviate. 
  
- **Se implementare la modalità critica**. Se l'archiviazione è un requisito per la propria organizzazione, la configurazione della modalità critica bloccherà le sessioni di messaggistica istantanea e di conferenza nel caso di un errore del server Skype for business che impedisse l'archiviazione. Ad esempio: 
    
  - Un problema con il servizio di archiviazione di Skype for Business Server. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - Una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Scegliere la distribuzione e le opzioni di configurazione per l'archiviazione

L'archiviazione viene automaticamente installata su ogni Front End Server quando si distribuisce il server, ma l'archiviazione non è abilitata fino a quando non viene configurata. La modalità di configurazione dell'archiviazione è determinata dalla modalità di distribuzione. È possibile distribuire l'archiviazione in uno dei modi seguenti:
  
- Utilizzare lo spazio di archiviazione di Microsoft Exchange
    
- Utilizzare lo spazio di archiviazione di Skype for Business Server
    
> [!NOTE]
> Se si implementano entrambi i database di archiviazione di Skype for Business Server e si attiva l'integrazione di Microsoft Exchange, i criteri di Exchange eseguono l'override dei criteri di archiviazione di Skype for Business Server, ma solo per gli utenti ospitati in Exchange e hanno le cassette postali inserite In-Place. L'archiviazione di Skype for business dipende dal criterio di blocco In-Place di Microsoft Exchange. 
  
Se si distribuisce l'archiviazione per un pool Front end o un server Standard Edition, è necessario abilitarla per tutti gli altri pool Front end e i server Standard Edition della distribuzione. Se l'archiviazione non è abilitata nel pool in cui è ospitata una conversazione o una riunione, è possibile che non vengano archiviati tutti i dati della conferenza. L'archiviazione continuerà a funzionare per i messaggi di messaggistica istantanea, ma è possibile che i contenuti e gli eventi per le conferenze non vengano archiviati.
  
> [!NOTE]
> Per abilitare la delega delle attività amministrative mantenendo gli standard di sicurezza dell'organizzazione, in Skype for Business Server viene utilizzato il controllo di accesso basato sui ruoli (RBAC). Con RBAC, i privilegi amministrativi vengono concessi assegnando gli utenti ai ruoli amministrativi predefiniti. Per configurare i criteri e le configurazioni di archiviazione di Skype for business, è necessario che l'utente sia assegnato al ruolo CsArchivingAdministrator, a meno che la configurazione non venga eseguita direttamente sul server in cui è distribuita l'archiviazione anziché in remoto da un altro computer. Per un elenco dei diritti utente, le autorizzazioni e i ruoli necessari per la distribuzione di archiviazione, vedere [deploy Archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Se si utilizza l'integrazione di Microsoft Exchange, la configurazione dei criteri di Exchange richiede autorizzazioni e diritti di amministratore adeguati. Per informazioni dettagliate, vedere la documentazione di Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Archiviazione di Microsoft Exchange

 Se si sceglie l'integrazione di Microsoft Exchange, è possibile utilizzare i criteri e le configurazioni di Exchange per controllare l'archiviazione di Skype for Business Server. È possibile configurare l'opzione di integrazione di Microsoft Exchange a livello globale, a livello di sito e a livello di pool. Se la distribuzione include più foreste, è necessario sincronizzare le impostazioni tra Skype for Business Server ed Exchange. Sarà necessario determinare:
  
- Se archiviare la messaggistica istantanea, le conferenze o entrambe
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server 
    
- Selezione dell'opzione di integrazione di Microsoft Exchange per l'utilizzo di Exchange per l'archiviazione dei dati archiviati
    
Per informazioni su come configurare i criteri e le impostazioni di Exchange In-Place Hold per supportare l'archiviazione, vedere la documentazione del prodotto Exchange.
  
### <a name="skype-for-business-server-storage"></a>Archiviazione di Skype for Business Server

Se si sceglie l'archiviazione di Skype for Business Server, è possibile utilizzare i criteri e le configurazioni di archiviazione di Skype for Business Server per controllare la modalità di abilitazione e implementazione dell'archiviazione. Lo spazio di archiviazione di Skype for Business Server utilizza i database di SQL Server, pertanto sarà necessario aggiungere i database di SQL Server necessari alla topologia, quindi configurare i criteri di archiviazione. 
  
### <a name="add-storage-databases-to-your-topology"></a>Aggiungere database di archiviazione alla topologia

Quando si aggiungono database di archiviazione di SQL Server alla topologia, è possibile scegliere di collocare i database di archiviazione con uno dei seguenti elementi:
  
- Database di monitoraggio
    
- Database back-end di un pool Enterprise Edition Front End
    
> [!NOTE]
> Il server che ospita il database di archiviazione può ospitare altri database. Se, tuttavia, si desidera collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo non è consigliabile collocare il database di archiviazione con il database back-end. 
  
Se si colloca il database di archiviazione con il database di monitoraggio, database back-end o entrambi i database, è possibile utilizzare una singola istanza di SQL per uno o per tutti i database oppure è possibile utilizzare un'istanza SQL separata per ogni database, con la seguente limitazione: ogni istanza di SQL può contenere solo un singolo database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.
  
Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [nozioni di base sulla topologia per Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Per informazioni dettagliate sull'aggiornamento della topologia in modo da includere i database di archiviazione, vedere [creare e pubblicare una nuova topologia in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Determinare le opzioni di archiviazione e i criteri utente

Sarà necessario determinare:
  
- Se abilitare o disabilitare l'archiviazione per le comunicazioni interne ed esterne
    
- Se archiviare la messaggistica istantanea, le conferenze o entrambe
    
- Se implementare la modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server 
    
- Se abilitare i criteri per utenti e gruppi specifici
    
È possibile specificare le opzioni di archiviazione di Skype for Business Server ai livelli seguenti. 
  
- **Opzione livello globale**. Questa è la configurazione di archiviazione predefinita e si applica all'intera distribuzione. Viene creato quando si distribuisce Skype for Business Server e, per impostazione predefinita, Disabilita l'archiviazione per le comunicazioni interne ed esterne. Non è possibile eliminare questa opzione. Se si sceglie l'opzione Elimina, l'opzione globale viene reimpostata sulle impostazioni predefinite.
    
- **Opzioni a livello di sito**. È possibile abilitare o disabilitare l'archiviazione per uno o più siti specifici mediante la creazione e la configurazione di un'opzione di archiviazione a livello di sito per il sito. È possibile eliminare qualsiasi opzione di archiviazione a livello di sito creata. Un'opzione di archiviazione a livello di sito sostituisce l'opzione globale, ma solo per il sito specificato nell'opzione. 
    
    Ad esempio, se si Abilita l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale e si crea una configurazione di sito in cui si disattiva l'archiviazione per le comunicazioni esterne, verranno archiviate solo le comunicazioni interne per il sito. Per un altro esempio, se si Abilita l'archiviazione solo per messaggistica istantanea nella configurazione globale e si crea una configurazione di sito in cui si Abilita l'archiviazione sia per la messaggistica istantanea sia per le conferenze, le conferenze verranno archiviate solo per il sito, non per il resto dell'organizzazione.
    
- **Opzioni a livello di pool**. È possibile specificare le impostazioni di archiviazione per uno o più pool specifici creando e configurando una configurazione a livello di pool per il singolo pool. Una configurazione di archiviazione a livello di pool esiste solo se la si crea. È possibile modificare ed eliminare qualsiasi configurazione di archiviazione a livello di pool. Una configurazione di archiviazione a livello di pool sostituisce la configurazione globale e qualsiasi configurazione di archiviazione dei siti che potrebbe essere stata creata. 
    
    Si supponga, ad esempio, di abilitare l'archiviazione per la messaggistica istantanea solo nella configurazione globale, quindi creare una configurazione a livello di sito in cui sia possibile abilitare l'archiviazione sia per la messaggistica istantanea sia per le conferenze e quindi creare una configurazione a livello di pool in cui abilitare l'archiviazione solo per la messaggistica istantanea. Le comunicazioni vengono archiviate sia per la messaggistica istantanea sia per le conferenze per tutti gli utenti del sito, ad eccezione degli utenti ospitati nel pool specificato nella configurazione a livello di pool. Per tutti gli altri utenti dell'organizzazione, l'archiviazione verrebbe abilitata solo per la messaggistica istantanea.
    
- **Criteri di archiviazione degli utenti**. È possibile abilitare o disabilitare l'archiviazione per uno o più utenti e gruppi di utenti specifici mediante la creazione, la configurazione e l'applicazione di criteri di archiviazione a livello di utente per gli utenti e i gruppi di utenti specificati. È possibile eliminare tutti i criteri di archiviazione a livello di utente creati ed è possibile modificare gli utenti e i gruppi di utenti a cui si applica il criterio di archiviazione. I criteri di archiviazione a livello di utente eseguono l'override dei criteri globali e degli eventuali criteri sito, ma solo per gli utenti e i gruppi di utenti a cui è applicato il criterio. 
    
    Si supponga, ad esempio, di disabilitare l'archiviazione per le comunicazioni interne ed esterne nella configurazione globale, creare un criterio a livello di sito in cui abilitare l'archiviazione per le comunicazioni interne ed esterne e quindi creare un criterio a livello di utente in cui disabilitare l'archiviazione per le comunicazioni esterne. Le comunicazioni vengono archiviate per le comunicazioni sia esterne che interne per tutti gli utenti del sito, ad eccezione degli utenti a cui si applica il criterio a livello di utente, per questi utenti verranno archiviati solo le comunicazioni interne.
    
Per informazioni dettagliate su come configurare le configurazioni di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [deploy Archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Per informazioni dettagliate sulla gestione dell'archiviazione dopo la distribuzione, vedere [Manage Archiving in Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Strumenti di configurazione di archiviazione

 È possibile controllare la maggior parte delle opzioni di archiviazione utilizzando il pannello di controllo di Skype for Business Server. Tuttavia, esistono alcune opzioni disponibili solo tramite Skype for Business Server Management Shell. Queste opzioni includono l'archiviazione dei messaggi duplicati e l'esportazione dei dati archiviati. Per ulteriori informazioni sull'utilizzo del pannello di controllo di Skype for Business Server e di Skype for Business Server Management Shell per gestire i criteri di archiviazione, vedere [Manage Archiving in Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accedere ai dati archiviati

La modalità di accesso ai dati archiviati dipende dalla posizione dei dati stessi: 
  
- **Archiviazione di Microsoft Exchange**. Se si sceglie l'opzione di integrazione di Exchange, in Skype for Business Server i contenuti di archiviazione vengono depositati nell'archivio di Exchange per tutti gli utenti ospitati in Exchange e per i quali le cassette postali sono state inserite In-Place. I dati archiviati vengono archiviati nella cartella degli elementi ripristinabili delle cassette postali degli utenti, che in genere sono invisibili all'utente, e possono essere ricercate solo dagli utenti con un ruolo di **gestione di individuazione** di Exchange. Exchange consente la ricerca federata e l'individuazione, insieme a SharePoint, se viene distribuita. Per ulteriori informazioni sull'archiviazione, la conservazione e l'individuazione dei dati archiviati in Exchange, vedere la documentazione di Exchange e SharePoint.
    
- **Archiviazione di archiviazione di Skype for Business Server**. Se si configurano i database di archiviazione di Skype for Business Server, Skype for Business Server deposita il contenuto di archiviazione nei database di archiviazione di Skype for Business Server per tutti gli utenti non ospitati in Exchange e che non dispongono di cassette postali inserite In-Place. Non è possibile sottoporre questi dati a ricerca, ma è possibile esportarli nei formati di altri strumenti di ricerca. Per informazioni dettagliate sull'esportazione dei dati archiviati nei database di archiviazione, vedere [esportare i dati archiviati in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sull'archiviazione, vedere i seguenti argomenti:
  
- [Distribuire l'archiviazione per Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gestione dell'archiviazione in Skype for Business Server](../../manage/archiving/archiving.md)
    
Per ulteriori informazioni su come funzionano insieme Skype for Business Server e Exchange, vedere [pianificare l'integrazione di Skype for business e Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

