---
title: "Lync Server 2013: definizione dei requisiti per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110423897de0d4d8e280a44cd51c645ab479241a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definizione dei requisiti per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Se l'organizzazione deve rispettare le normative di conformità, è possibile distribuire l'archiviazione per abilitare il supporto per l'archiviazione per Lync Server 2013 Instant Messaging (chat) e le conferenze (riunioni). Per informazioni dettagliate sul tipo di contenuto che può essere archiviato, vedere [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) nella documentazione relativa alla pianificazione.

Per implementare l'archiviazione, è necessario innanzitutto decidere come soddisfare i requisiti dell'organizzazione per l'archiviazione. Per questo è necessario determinare quanto segue:

  - **Quando si distribuisce l'archiviazione**. È possibile distribuire l'archiviazione come parte della distribuzione iniziale di Lync Server 2013 oppure è possibile aggiungerla a una distribuzione esistente. È possibile distribuire l'archiviazione tramite Generatore di topologie per aggiungerla alla topologia e quindi pubblicare la topologia.

  - **Se archiviare le comunicazioni interne o esterne**. È possibile abilitare l'archiviazione per le comunicazioni interne (comunicazioni tra gli utenti interni), le comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna) o entrambe. È possibile specificare queste opzioni per l'intera organizzazione oppure è possibile specificarle per siti e pool specifici. Per impostazione predefinita, nessuna opzione è abilitata.
    
    <div>
    

    > [!NOTE]  
    > Se si utilizza l'integrazione di Microsoft Exchange per archiviare i dati archiviati, le impostazioni di Exchange controllano se le comunicazioni di Lync sono archiviate. Se la distribuzione include più foreste, è necessario sincronizzare le impostazioni tra Lync Server e Exchange. Il controllo dell'archiviazione per le comunicazioni interne o esterne è disponibile solo per i criteri di Lync. Per l'archiviazione integrata in Exchange, entrambe verranno archiviate o non archiviate.

    
    </div>

  - **Perché abilitare l'archiviazione**. È possibile abilitare e disabilitare l'archiviazione per l'intera distribuzione a livello globale ed è possibile abilitare e disabilitare l'archiviazione per siti e utenti specifici. A ognuno di questi livelli, è possibile specificare se abilitare l'archiviazione delle sessioni di messaggistica istantanea (peer-to-peer), le conferenze (riunioni, che sono sessioni con più partecipanti) o entrambe. Per impostazione predefinita, l'archiviazione è disattivata.

  - **La modalità di archiviazione critica per gli utenti dell'organizzazione**. Se l'archiviazione è di importanza cruciale nell'organizzazione, è possibile specificare che Lync Server 2013 viene eseguito in modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza se l'archiviazione ha esito negativo. Ad esempio:
    
      - Se il servizio di archiviazione non è temporaneamente in grado di inviare un messaggio alla coda del database o di inserire un messaggio nel database, vengono bloccate sia la funzionalità di messaggistica istantanea che quella di conferenza nella distribuzione fino a quando non viene ripristinato il supporto dell'archiviazione.
    
      - Se un utente di conferenza carica un file, ma il file non può essere copiato nell'archivio file, la funzionalità di conferenza viene bloccata nella distribuzione fino alla risoluzione del problema, ma la funzionalità di messaggistica istantanea non viene bloccata.
    
    Questa opzione può essere configurata a livello globale, a livello di sito e a livello di pool. Per impostazione predefinita, la modalità critica non è abilitata.

  - **Se utilizzare l'integrazione di Microsoft Exchange**. Questa opzione integra l'archiviazione di archiviazione con l'archiviazione di Exchange 2013, in modo che i dati archiviati in Lync Server e i dati archiviati in Exchange 2013 siano archiviati insieme in Exchange. È possibile utilizzare l'integrazione di Microsoft Exchange per l'archiviazione dei dati di archiviazione per gli utenti ospitati in Exchange 2013, se le cassette postali sono state inserite nel blocco sul posto. Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarlo o se sono presenti utenti di Lync che non sono ospitati in Exchange 2013, è possibile distribuire database di archiviazione distinti mediante SQL Server per archiviare i dati archiviati dalle comunicazioni di Lync. È possibile configurare l'opzione di integrazione di Microsoft Exchange a livello globale, a livello di sito e a livello di pool. Per impostazione predefinita, l'integrazione di Microsoft Exchange non è abilitata.

  - **Modalità di gestione dei dati archiviati**. Il database di archiviazione non è progettato per la conservazione a lungo termine e Lync Server 2013 non fornisce una soluzione e-Discovery (ricerca) per i dati archiviati, pertanto i dati devono essere spostati in un altro spazio di archiviazione. Lync Server fornisce uno strumento di esportazione della sessione che è possibile utilizzare per esportare i dati archiviati e che consente di creare trascrizioni di ricerca dei dati archiviati. Per il criterio globale e per ogni criterio di sito e utente creato, è possibile abilitare l'eliminazione dei dati e specificare una delle opzioni seguenti:
    
      - Eliminare sia i dati di archiviazione esportati che i dati di archiviazione memorizzati dopo un numero specifico di giorni. Il numero minimo di giorni supportato è un giorno. Il numero massimo è 2562 giorni.
    
      - Eliminare solo i dati di archiviazione esportati. Questa opzione consente di eliminare tutti i record esportati e contrassegnati come sicuri per l'eliminazione dallo strumento di esportazione delle sessioni.
    
    Questa opzione può essere configurata a livello globale, a livello di sito e a livello di pool. Per impostazione predefinita, l'eliminazione non è abilitata.

È possibile controllare l'archiviazione utilizzando i metodi seguenti:

  - **Criteri di archiviazione**. È possibile utilizzare uno o più criteri di archiviazione per abilitare e disabilitare l'archiviazione delle comunicazioni interne ed esterne. Per impostazione predefinita, non è abilitata l'archiviazione. Per abilitare o disabilitare l'archiviazione delle comunicazioni interne, delle comunicazioni esterne o di entrambi nella distribuzione, è possibile utilizzare il criterio globale predefinito. Non è possibile eliminare i criteri globali. È possibile specificare uno o più criteri di sito facoltativi per abilitare o disabilitare l'archiviazione delle comunicazioni interne ed esterne per siti specifici. È inoltre possibile specificare uno o più criteri utente per l'abilitazione o la disabilitazione dell'archiviazione per utenti e gruppi utente specifici. I criteri a livello di utente eseguono l'override di criteri sito. I criteri a livello di sito eseguono l'override dei criteri a livello globale. I criteri a livello di utente vengono implementati solo per gli utenti specifici che sono configurati per l'utilizzo del criterio. I messaggi istantanei e le conferenze di gruppo vengono archiviati solo se un criterio per almeno uno dei partecipanti è configurato per consentire l'archiviazione.
    
    <div>
    

    > [!NOTE]  
    > Se si utilizza l'integrazione di Microsoft Exchange, i criteri di Exchange 2013 eseguono l'override dei criteri di archiviazione di Lync Server per tutti gli utenti ospitati nei server Exchange 2013.

    
    </div>

  - **Configurazioni di archiviazione**. È possibile utilizzare una o più configurazioni di archiviazione per specificare la maggior parte delle opzioni di archiviazione descritte in precedenza in questo argomento, ad eccezione dell'abilitazione dell'archiviazione delle comunicazioni interne ed esterne (configurata utilizzando i criteri di archiviazione, come descritto nella sezione punto elenco precedente). Le configurazioni di archiviazione includono la configurazione globale predefinita e le configurazioni del sito e del pool facoltative. Non è possibile eliminare la configurazione globale. Le configurazioni a livello di pool eseguono l'override delle configurazioni a livello di sito. Le configurazioni a livello di sito sovrascrivono la configurazione a livello globale.

Nell'ambito dell'analisi dei requisiti, è necessario determinare come configurare la configurazione di archiviazione globale e i criteri di archiviazione globale. È inoltre necessario determinare i requisiti per tutte le configurazioni di archiviazione a livello di sito, le configurazioni di archiviazione a livello di pool, i criteri di archiviazione a livello di sito e i criteri di archiviazione a livello di utente.

Se si distribuisce l'archiviazione per un pool Front end o un server Standard Edition, è necessario abilitarla per tutti gli altri pool Front end e i server Standard Edition della distribuzione. Ciò è necessario perché gli utenti di cui viene richiesta l'archiviazione delle comunicazioni possono essere invitati in un gruppo di conversazione di messaggistica istantanea o a riunioni ospitate in un pool diverso. Se l'archiviazione non è abilitata nel pool in cui è ospitata la conversazione o la riunione, è possibile che non vengano archiviati tutti i dati della conferenza. L'archiviazione continuerà a funzionare per l'archiviazione degli utenti abilitati e di tutti i messaggi di messaggistica istantanea, ma i contenuti e gli eventi per le conferenze potrebbero non essere archiviati.

<div>


> [!NOTE]  
> Per abilitare la delega delle attività amministrative mantenendo gli standard di sicurezza dell'organizzazione, Lync Server&nbsp;2013 utilizza il controllo di accesso basato sui ruoli (RBAC). Con RBAC, i privilegi amministrativi vengono concessi assegnando gli utenti ai ruoli amministrativi predefiniti. Per configurare i criteri di archiviazione e le configurazioni di archiviazione di Lync, è necessario che l'utente sia assegnato al ruolo CsArchivingAdministrator, a meno che la configurazione non venga eseguita direttamente sul server in cui è distribuita l'archiviazione anziché in remoto da un altro computer. Per informazioni dettagliate su RBAC, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per un elenco dei diritti utente, le autorizzazioni e i ruoli necessari per la distribuzione di archiviazione, vedere elenco di <A href="lync-server-2013-deployment-checklist-for-archiving.md">controllo di distribuzione per l'archiviazione in Lync Server 2013</A>, disponibile sia nella documentazione relativa alla pianificazione che nella documentazione relativa alla distribuzione.<BR>Se si utilizza l'integrazione di Microsoft Exchange, la configurazione dei criteri di Exchange richiede autorizzazioni e diritti di amministratore adeguati. Per informazioni dettagliate, vedere la documentazione di Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

