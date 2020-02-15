---
title: "Lync Server 2013: funzionamento dell'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24181e9e72228afb380d8e6e50d70f5e3c95e41e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Funzionamento dell'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-04_

Lync Server 2013 Archiving fornisce opzioni che consentono di soddisfare le esigenze di conformità. Per implementare e gestire l'archiviazione in modo da soddisfare i requisiti dell'organizzazione nel modo più efficiente, è necessario comprendere:

  - Quali informazioni possono essere archiviate.

  - Come abilitare e disabilitare l'archiviazione nella distribuzione in uso.

  - Quali opzioni di archiviazione possono essere configurate per controllare la modalità di implementazione dell'archiviazione.

<div>

## <a name="what-information-can-be-archived"></a>Quali informazioni possono essere archiviate?

È possibile archiviare i tipi di contenuto seguenti:

  - Messaggi istantanei peer-to-peer

  - Conferenze (riunioni), che corrispondono in pratica a messaggi istantanei tra più utenti

  - Contenuto di conferenze, compreso il contenuto caricato (ad esempio, stampati) e correlato agli eventi (ad esempio, accesso, uscita, caricamento in condivisione e modifiche della visibilità)

  - Lavagne e sondaggi condivisi durante una conferenza

Non vengono archiviati i tipi di contenuto seguenti:

  - Trasferimenti di file peer-to-peer

  - Audio e video per messaggi istantanei peer-to-peer e conferenze

  - Condivisione di desktop e applicazioni per messaggi istantanei peer-to-peer e conferenze

Lync Server inoltre non archivia le conversazioni di chat persistente. Per archiviare le conversazioni di chat persistente, è necessario abilitare e configurare il servizio di conformità, che è un componente che può essere distribuito con Microsoft Lync Server 2013, il server Chat persistente. Per informazioni dettagliate, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Come si inizia a usare la funzionalità di archiviazione?

L'installazione della funzionalità di archiviazione avviene automaticamente in ogni Front End Server durante la distribuzione del server. L'abilitazione della funzionalità, tuttavia, avviene solo al momento della configurazione. La modalità di configurazione dell'archiviazione è determinata dalla modalità di distribuzione usata:

  - **Archiviazione tramite l'integrazione di Microsoft Exchange.** Se si dispone di utenti ospitati in Exchange 2013 e le relative cassette postali sono state inserite in archiviazione sul posto, è possibile selezionare l'opzione per l'integrazione dell'archivio Lync Server 2013 con l'archivio di Exchange. Se si sceglie l'opzione di integrazione di Microsoft Exchange, è possibile utilizzare i criteri e le configurazioni di Exchange 2013 per controllare l'archiviazione dei dati di Lync Server 2013 per tali utenti.

  - **Archiviazione tramite i database di archiviazione di Lync Server.** Se si dispone di utenti che non sono ospitati in Exchange 2013 o che non dispongono di cassette postali in blocco sul posto o che non si desidera utilizzare l'integrazione di Microsoft Exchange per uno o tutti gli utenti nella distribuzione, è possibile distribuire i database di archiviazione di Lync Server tramite SQL Server  per archiviare i dati di archiviazione per tali utenti. In questo caso, i criteri e le configurazioni di archiviazione di Lync Server 2013 determinano se l'archiviazione è abilitata e come viene implementata. Per utilizzare Lync Server 2013, è necessario aggiungere i database di SQL Server adeguati alla topologia e pubblicare la topologia.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Configurazione dell'archiviazione quando si utilizza l'integrazione di Microsoft Exchange

Se gli utenti sono ospitati in Exchange 2013 e le relative cassette postali sono state inserite in archiviazione sul posto, è possibile scegliere l'opzione di **integrazione di Microsoft Exchange** (come descritto più avanti in questa sezione) per archiviare Lync Server 2013 per tali utenti, quindi controllare l'archivio per tali utenti specificando i criteri e le impostazioni del blocco sul posto di Exchange, nonché le configurazioni di Lync Server

  - Archiviazione dei messaggi istantanei, delle conferenze o di entrambi.

  - Se implementare la modalità critica per la distribuzione di Lync Server.

  - Selezione dell'opzione di integrazione di Microsoft Exchange per l'utilizzo di Exchange 2013 per l'archiviazione dei dati archiviati.

Queste opzioni di configurazione di archiviazione di Lync Server 2013 sono descritte più avanti in questa sezione. Per informazioni su come configurare i criteri e le impostazioni per il blocco sul posto di Exchange per il supporto dell'archiviazione, vedere la documentazione del prodotto Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Impostazione della funzionalità di archiviazione per l'uso con database di archiviazione di Lync Server

Se si desidera utilizzare i database di archiviazione di Lync Server (utilizzando i database di SQL Server) per archiviare i dati per tutti gli utenti nella distribuzione, è possibile configurare i criteri di archiviazione di Lync Server per controllare se l'archiviazione è abilitata per tali utenti. Nei criteri di archiviazione è possibile abilitare o disabilitare la funzionalità per uno o entrambi i tipi di comunicazione seguenti:

  - Comunicazioni interne

  - Comunicazioni esterne

Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o le comunicazioni esterne nei criteri di archiviazione di Lync Server. È possibile abilitare e disabilitare le comunicazioni utilizzando il pannello di controllo di Lync Server 2013 o utilizzando i cmdlet in Lync Server 2013 Management Shell.

I criteri di archiviazione di Lync Server 2013 includono gli elementi seguenti:

  - **Criteri di archiviazione globale**. Questi criteri di archiviazione sono predefiniti e si applicano all'intera distribuzione. Viene creato quando si distribuisce Lync Server 2013 e, per impostazione predefinita, Disabilita l'archiviazione per le comunicazioni interne ed esterne. Non è possibile eliminare questi criteri. Se si sceglie l'opzione di eliminazione, per i criteri globali vengono ripristinate le impostazioni predefinite.

  - **Criteri di archiviazione a livello di sito**. Facoltativamente è possibile abilitare o disabilitare l'archiviazione per uno o più siti specifici creando e configurando criteri di archiviazione a livello di sito per i siti interessati. Quando si creano criteri di archiviazione a livello di sito, per impostazione predefinita l'archiviazione è disabilitata. È possibile eliminare i criteri di archiviazione a livello di sito creati. I criteri di archiviazione a livello di sito forzano i criteri globali, ma solo per il sito specificato nei criteri stessi. Se ad esempio si abilita l'archiviazione per le comunicazioni interne ed esterne nei criteri globali e si creano criteri a livello di sito in cui si disabilita l'archiviazione per le comunicazioni esterne, per il sito in questione verranno archiviate solo le comunicazioni interne.

  - **Criteri di archiviazione a livello di utente**. Facoltativamente è possibile abilitare o disabilitare l'archiviazione per uno o più utenti e gruppi di utenti specifici creando, configurando e applicando criteri di archiviazione a livello di utente per gli utenti e i gruppi di utenti specificati. Quando si creano criteri di archiviazione a livello di utente, per impostazione predefinita l'archiviazione è disabilitata. È possibile eliminare i criteri di archiviazione a livello di utente creati e cambiare gli utenti e i gruppi di utenti a cui applicare tali criteri. I criteri di archiviazione a livello di utente forzano i criteri globali e i criteri sito, ma solo per gli utenti e i gruppi di utenti a cui i criteri a livello di utente sono applicati. Se ad esempio si disabilita l'archiviazione per le comunicazioni interne ed esterne nei criteri globali, si creano criteri a livello di sito con cui si abilita l'archiviazione delle comunicazioni interne ed esterne e quindi si creano criteri a livello di utente con cui si disabilita l'archiviazione per le comunicazioni esterne, l'archiviazione verrà eseguita per le comunicazioni esterne e interne per gli utenti di tutti i siti ad eccezione degli utenti a cui si applicano i criteri a livello di utente, per i quali verranno archiviate solo le comunicazioni interne.

Per informazioni dettagliate su come configurare i criteri di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'utilizzo dei criteri di archiviazione per abilitare e disabilitare le comunicazioni dopo la distribuzione, vedere [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) nella documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Se si implementano entrambi i database di archiviazione di Lync Server 2013 e si attiva l'integrazione di Microsoft Exchange, i criteri di Exchange 2013 eseguono l'override dei criteri di archiviazione di Lync Server, ma solo per gli utenti che si trovano in Exchange 2013 e che dispongono di cassette postali in blocco sul posto. . L'archiviazione Lync dipende solo dal criterio di blocco sul posto di Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quali sono le opzioni disponibili per la configurazione dell'archiviazione?

Oltre a utilizzare i criteri e per abilitare e disabilitare l'archiviazione, sono disponibili altre opzioni di archiviazione che possono essere configurate per l'intera distribuzione e, facoltativamente, per siti e pool specifici. È possibile controllare la maggior parte delle opzioni di archiviazione utilizzando una o più configurazioni di archiviazione, disponibili nel pannello di controllo di Lync Server 2013, ma anche un'altra opzione disponibile solo per la configurazione tramite Lync Server 2013 Management Shell.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opzioni di configurazione dell'archiviazione disponibili nel Pannello di controllo di Lync Server 2013

Per ciascuna configurazione di archiviazione sono disponibili le opzioni seguenti:

La configurazione a livello globale viene creata automaticamente quando si distribuisce la funzionalità di archiviazione e può essere configurata, ma non eliminata. Se si seleziona l'opzione di eliminazione della configurazione globale, per le impostazioni vengono ripristinati i valori predefiniti. È possibile creare più configurazioni a livello di sito e di pool che, insieme alla configurazione globale, consentono di controllare le impostazioni di archiviazione. Per la configurazione globale e la configurazione a livello di ogni sito e di ogni pool sono disponibili le opzioni seguenti:

  - Disabilitare l'archiviazione, abilitare l'archiviazione solo per la messaggistica istantanea o abilitarla sia per la messaggistica istantanea che per le conferenze.

  - Configurare la modalità critica per bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Lync Server. Gli errori possono riguardare:
    
      - **Messaggistica istantanea**. Un problema con il servizio di archiviazione di Lync Server. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
      - **Conferenze**, nel caso di una condivisione file non disponibile o di un problema del servizio di archiviazione. In questo caso, tutte le conferenze attive ospitate nel pool al momento dell'errore passano in modalità limitata e non è possibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.

  - Specificare l'utilizzo dell'integrazione di Microsoft Exchange Server 2013 per l'utilizzo di Exchange 2013 per l'archiviazione dei dati archiviati, anziché la configurazione di database SQL Server separati per l'archiviazione dei dati di archiviazione di Lync Server 2013.

  - Configurare opzioni di eliminazione per i dati archiviati. Questa opzione consente di specificare quando eliminare i dati archiviati, scegliendo tra le alternative seguenti:
    
      - Dopo il numero di giorni specificato
    
      - Dopo l'esportazione dei dati di archiviazione (che include i dati caricati in Exchange, se si Abilita l'integrazione di Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Se si Abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange 2013 e le cassette postali inserite in archiviazione sul posto è controllata da Exchange. L'unica qualifica è per i file di conferenza, che sono archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione.

    
    </div>

Per impostazione predefinita, non sono abilitate opzioni di archiviazione. È possibile gestire le configurazioni di archiviazione utilizzando il pannello di controllo di Lync Server 2013.

Si possono specificare le configurazioni di archiviazione seguenti:

  - **Configurazione di archiviazione globale**. Questa è la configurazione di archiviazione predefinita e si applica all'intera distribuzione. Viene creato quando si distribuisce Lync Server 2013 e, per impostazione predefinita, non attiva la funzionalità di archiviazione. È possibile modificare la configurazione globale, ma non è possibile eliminarla. Se si sceglie l'opzione di eliminazione, per la configurazione globale vengono ripristinate le impostazioni predefinite.

  - **Configurazione di archiviazione a livello di sito**. Facoltativamente è possibile configurare l'archiviazione per uno o più siti specifici creando e impostando una configurazione di archiviazione a livello di sito per un sito singolo. Una configurazione di archiviazione a livello di sito esiste solo se viene creata. È possibile modificare o eliminare le configurazioni di archiviazione a livello di sito. Le configurazioni di archiviazione a livello di sito forzano la configurazione globale, ma solo per il sito specificato nella configurazione a livello di sito. Se, ad esempio, nella configurazione globale si abilita la funzionalità di archiviazione solo per la messaggistica istantanea e si crea una configurazione a livello di sito in cui si abilita l'archiviazione sia per la messaggistica istantanea che per le conferenze, queste ultime verranno archiviate solo per il sito ma non per il resto dell'organizzazione.

  - **Configurazione di archiviazione a livello di pool**. Facoltativamente è possibile specificare impostazioni di archiviazione per uno o più pool specifici creando e impostando una configurazione a livello di pool per un pool singolo. Una configurazione di archiviazione a livello di pool esiste solo se viene creata. È possibile modificare ed eliminare le configurazioni di archiviazione a livello di pool. Le configurazioni di archiviazione a livello di pool forzano la configurazione globale e le eventuali configurazioni di archiviazione a livello di sito create. Se, ad esempio, nella configurazione globale si abilita la funzionalità di archiviazione solo per la messaggistica istantanea, si crea una configurazione a livello di sito in cui è abilitata l'archiviazione sia per la messaggistica istantanea che per le conferenze del sito e quindi si crea una configurazione a livello di pool in cui l'archiviazione è abilitata solo per la messaggistica istantanea, le comunicazioni di messaggistica istantanea e di conferenza verranno archiviate per tutti gli utenti del sito ad eccezione degli utenti disponibili nel pool specificato nella configurazione a livello di pool. Per tutti gli altri utenti dell'organizzazione, l'archiviazione sarà abilitata solo per la messaggistica istantanea.

Per informazioni dettagliate su come configurare le configurazioni di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [configurazione delle opzioni di archiviazione in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'utilizzo dei criteri di archiviazione per abilitare e disabilitare le comunicazioni dopo la distribuzione, vedere [Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) nella documentazione relativa alle operazioni.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opzioni di archiviazione disponibili solo in Windows PowerShell

Utilizzando Lync Server 2013 Management Shell, è possibile utilizzare i cmdlet per implementare le opzioni non disponibili nel pannello di controllo di Lync Server 2013. Queste opzioni sono:

  - **Archiviazione di messaggi duplicati**. Per informazioni dettagliate, vedere [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) e [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) nella documentazione relativa alle operazioni.

  - **Esportazione di dati archiviati**. Per informazioni dettagliate, vedere [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Come si accede ai dati archiviati?

La modalità di accesso ai dati archiviati dipende dalla posizione dei dati stessi:

  - **Archiviazione di Microsoft Exchange**. Se si sceglie l'opzione di integrazione di Exchange, Lync Server depositerà il contenuto di archiviazione nell'archivio di Exchange 2013 per tutti gli utenti che si trovano in Exchange 2013 e le cui cassette postali sono state inserite nel blocco sul posto. I dati archiviati sono archiviati nella cartella degli elementi ripristinabili delle cassette postali degli utenti, che in genere sono invisibili per l'utente, e possono essere ricercate solo dagli utenti con un ruolo di **Gestione individuazione** di Exchange. Exchange consente la ricerca federata e l'individuazione, insieme a SharePoint, se viene distribuita. Per ulteriori informazioni sull'archiviazione, la conservazione e l'individuazione dei dati archiviati in Exchange, vedere la documentazione di Exchange 2013 e SharePoint.

  - **Archiviazione Lync Server**. Se si configurano i database di archiviazione di Lync Server 2013 per l'archiviazione dei dati di Lync Server, Lync Server archivia i contenuti di archiviazione nei database di archiviazione di Lync Server (database di SQL Server) per tutti gli utenti non ospitati in Exchange 2013 e che non hanno le cassette postali inserite Blocco sul posto. Non è possibile sottoporre questi dati a ricerca, ma è possibile esportarli nei formati di altri strumenti di ricerca. Per informazioni dettagliate sull'esportazione dei dati archiviati nei database di archiviazione, vedere [esportazione di dati archiviati da Lync Server 2013](lync-server-2013-exporting-archived-data.md) nella documentazione relativa alle operazioni.

Per ulteriori informazioni su come Lync Server 2013 e Exchange 2013 interagiscono, vedere [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

