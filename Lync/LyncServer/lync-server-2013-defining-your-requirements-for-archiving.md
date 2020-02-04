---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per l'archiviazione"
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
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Se l'organizzazione deve seguire le regole di conformità, è possibile distribuire l'archiviazione per consentire l'archiviazione del supporto per la messaggistica istantanea e le conferenze (riunioni) di Lync Server 2013. Per informazioni dettagliate sul tipo di contenuto che è possibile archiviare, vedere [Panoramica dell'archiviazione in Lync Server 2013](lync-server-2013-overview-of-archiving.md) nella documentazione relativa alla pianificazione.

Per implementare l'archiviazione, è necessario decidere prima di tutto come soddisfare i requisiti dell'organizzazione per l'archiviazione. Ciò richiede la determinazione di quanto segue:

  - **Quando distribuire l'archiviazione**. È possibile distribuire l'archiviazione come parte della distribuzione iniziale di Lync Server 2013 oppure aggiungerla a una distribuzione esistente. L'archiviazione viene distribuita tramite Generatore di topologia per aggiungerla alla topologia e quindi pubblicare la topologia.

  - **Se archiviare comunicazioni interne o esterne**. È possibile abilitare l'archiviazione per le comunicazioni interne (comunicazioni tra utenti interni), le comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna) o entrambe. Puoi specificare queste opzioni per l'intera organizzazione oppure puoi specificarle per siti e pool specifici. Per impostazione predefinita, nessuna opzione è abilitata.
    
    <div>
    

    > [!NOTE]  
    > Se si usa l'integrazione di Microsoft Exchange per archiviare i dati archiviati, le impostazioni di Exchange controllano se le comunicazioni Lync sono archiviate. Se la distribuzione include più foreste, è necessario sincronizzare le impostazioni tra Lync Server e Exchange. Il controllo dell'archiviazione per comunicazioni interne o esterne è disponibile solo per i criteri di Lync. Per l'archiviazione integrata in Exchange, entrambe verranno archiviate o non archiviate.

    
    </div>

  - **Perché abilitare l'archiviazione**. È possibile abilitare e disabilitare l'archiviazione per l'intera distribuzione a livello globale ed è possibile abilitare e disabilitare l'archiviazione per siti e utenti specifici. In ognuno di questi livelli, devi specificare se abilitare l'archiviazione delle sessioni di messaggistica istantanea (peer-to-peer), le conferenze (riunioni, che sono sessioni multiparte) o entrambe. Per impostazione predefinita, l'archiviazione è disabilitata.

  - **Modalità di archiviazione critica per gli utenti dell'organizzazione**. Se l'archiviazione è fondamentale per l'organizzazione, è possibile specificare che Lync Server 2013 viene eseguito in modalità critica, che blocca le sessioni di messaggistica istantanea e di conferenza se l'archiviazione non riesce. Ad esempio:
    
      - Se il servizio archiviazione non è temporaneamente in grado di inviare un messaggio alla coda del database o di inserire un messaggio nel database, le funzionalità di messaggistica istantanea e di conferenza sono bloccate nella distribuzione finché non viene ripristinato il supporto per l'archiviazione.
    
      - Se un utente dei servizi di conferenza carica un file, ma il file non può essere copiato nell'archivio file di archiviazione, la funzionalità di conferenza viene bloccata nella distribuzione finché il problema non viene risolto, ma la funzionalità di messaggistica istantanea non viene bloccata.
    
    Questa opzione può essere configurata a livello globale, livello di sito e livello di pool. Per impostazione predefinita, la modalità critica non è abilitata.

  - **Se usare l'integrazione di Microsoft Exchange**. Questa opzione consente di integrare lo spazio di archiviazione con lo spazio di archiviazione di Exchange 2013, in modo che i dati archiviati in Lync Server e Exchange 2013 vengano archiviati insieme in Exchange. È possibile usare l'integrazione di Microsoft Exchange per l'archiviazione dei dati di archiviazione per gli utenti residenti in Exchange 2013, se le cassette postali sono state inserite in blocco sul posto. Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarla o se si hanno utenti di Lync non residenti in Exchange 2013, è possibile distribuire database di archiviazione distinti tramite SQL Server per archiviare i dati archiviati dalle comunicazioni di Lync. È possibile configurare l'opzione di integrazione di Microsoft Exchange a livello globale, livello di sito e livello di pool. Per impostazione predefinita, l'integrazione di Microsoft Exchange non è abilitata.

  - **Modalità di gestione dei dati archiviati**. Il database di archiviazione non è progettato per la conservazione a lungo termine e Lync Server 2013 non offre una soluzione di individuazione e (ricerca) per i dati archiviati, pertanto i dati devono essere spostati in un altro spazio di archiviazione. Lync Server offre uno strumento di esportazione della sessione che puoi usare per esportare i dati archiviati e che crea trascrizioni ricercabili dei dati archiviati. Per i criteri globali e per ogni criterio di sito e utente creato, è possibile abilitare l'eliminazione dei dati e specificare una delle opzioni seguenti:
    
      - Eliminare i dati di archiviazione esportati e i dati archiviati dopo un determinato numero di giorni. Il numero minimo di giorni che puoi specificare è un giorno. Il numero massimo di giorni che puoi specificare è di 2562 giorni.
    
      - Eliminare solo i dati di archiviazione esportati. Questa opzione consente di eliminare tutti i record esportati e contrassegnati come sicuri per l'eliminazione tramite lo strumento di esportazione della sessione.
    
    Questa opzione può essere configurata a livello globale, livello di sito e livello di pool. Per impostazione predefinita, l'eliminazione non è abilitata.

Per controllare l'archiviazione, è possibile usare i metodi seguenti:

  - **Criteri di archiviazione**. Si usano uno o più criteri di archiviazione per abilitare e disabilitare l'archiviazione delle comunicazioni interne ed esterne. Per impostazione predefinita, non è abilitato l'archiviazione. Puoi abilitare o disabilitare l'archiviazione per comunicazioni interne, comunicazioni esterne o entrambe nella distribuzione usando i criteri globali predefiniti. Non è possibile eliminare il criterio globale. È possibile specificare uno o più criteri di sito facoltativi per abilitare o disabilitare l'archiviazione per le comunicazioni interne ed esterne per siti specifici. È anche possibile specificare uno o più criteri utente per abilitare o disabilitare l'archiviazione per utenti e gruppi utente specifici. I criteri a livello di utente eseguono l'override dei criteri del sito. I criteri a livello di sito eseguono l'override dei criteri a livello globale. I criteri a livello di utente vengono implementati solo per gli utenti specifici configurati per l'uso dei criteri. Raggruppare i messaggi istantanei e le conferenze vengono archiviati solo se un criterio per almeno uno dei partecipanti è configurato per consentire l'archiviazione.
    
    <div>
    

    > [!NOTE]  
    > Se si usa l'integrazione di Microsoft Exchange, i criteri di Exchange 2013 eseguono l'override dei criteri di archiviazione di Lync Server per tutti gli utenti residenti nei server Exchange 2013.

    
    </div>

  - **Configurazioni di archiviazione**. È possibile usare una o più configurazioni di archiviazione per specificare la maggior parte delle opzioni di archiviazione descritte in precedenza in questo argomento, ad eccezione dell'attivazione dell'archiviazione delle comunicazioni interne ed esterne (configurate con i criteri di archiviazione, come descritto nella sezione punto elenco precedente). Le configurazioni di archiviazione includono la configurazione globale predefinita e le configurazioni del sito e del pool facoltative. Non è possibile eliminare la configurazione globale. Le configurazioni a livello di pool eseguono l'override delle configurazioni a livello di sito. Le configurazioni a livello di sito eseguono l'override della configurazione a livello globale.

Come parte dell'analisi dei requisiti, devi determinare come configurare la configurazione globale dell'archiviazione e i criteri di archiviazione globale. Devi anche determinare i requisiti per tutte le configurazioni di archiviazione a livello di sito, le configurazioni di archiviazione a livello di pool, i criteri di archiviazione a livello di sito e i criteri di archiviazione a livello di utente.

Se si distribuisce l'archiviazione per un pool Front-end o un server Standard Edition, è consigliabile abilitarlo per tutti gli altri pool Front end e i server Standard Edition nella distribuzione. È necessario eseguire questa operazione perché gli utenti le cui comunicazioni sono necessarie per l'archiviazione possono essere invitati a una conversazione di messaggistica istantanea di gruppo o a riunioni ospitate in un pool diverso. Se l'archiviazione non è abilitata nel pool in cui è ospitata la conversazione o la riunione, non è possibile archiviare tutti i dati della conferenza. L'archiviazione continuerà a funzionare per l'archiviazione degli utenti abilitati e di tutti i messaggi di messaggistica istantanea, ma il contenuto e gli eventi di conferenza potrebbero non essere archiviati.

<div>


> [!NOTE]  
> Per abilitare la delega delle attività amministrative mantenendo gli standard di sicurezza dell'organizzazione, Lync Server&nbsp;2013 usa il controllo di accesso basato sui ruoli (RBAC). Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti i ruoli amministrativi predefiniti. Per configurare i criteri di archiviazione e le configurazioni di archiviazione di Lync, l'utente deve essere assegnato al ruolo CsArchivingAdministrator, a meno che la configurazione non venga eseguita direttamente nel server in cui è distribuita l'archiviazione, anziché in remoto da un altro computer. Per informazioni dettagliate su RBAC, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Per un elenco dei diritti utente, le autorizzazioni e i ruoli necessari per l'archiviazione della distribuzione, vedere elenco di <A href="lync-server-2013-deployment-checklist-for-archiving.md">controllo della distribuzione per l'archiviazione in Lync Server 2013</A>, disponibile sia nella documentazione relativa alla pianificazione che nella documentazione relativa alla distribuzione.<BR>Se si usa l'integrazione di Microsoft Exchange, la configurazione dei criteri di Exchange richiede diritti e autorizzazioni di amministratore appropriati. Per informazioni dettagliate, vedere la documentazione di Exchange 2013.



</div>

</div>

<span> </span>

</div>

</div>

</div>

