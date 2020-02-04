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
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Funzionamento dell'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-04_

L'archiviazione di Lync Server 2013 offre opzioni utili per soddisfare le esigenze di conformità. Per implementare e gestire in modo più efficace i requisiti della propria organizzazione, è necessario comprendere:

  - Quali informazioni possono essere archiviate.

  - Come abilitare e disabilitare l'archiviazione nella distribuzione.

  - Opzioni di archiviazione che è possibile configurare per controllare la modalità di implementazione dell'archiviazione.

<div>

## <a name="what-information-can-be-archived"></a>Quali informazioni possono essere archiviate?

I tipi di contenuto seguenti possono essere archiviati:

  - Messaggi istantanei peer-to-peer

  - Conferenze (riunioni), che sono messaggi istantanei a più parti

  - Contenuto della conferenza, incluso il contenuto caricato, ad esempio gli stampati, e il contenuto correlato agli eventi (ad esempio, partecipazione, uscita, caricamento della condivisione e modifica della visibilità)

  - Lavagne e sondaggi condivisi durante una conferenza

I tipi di contenuto seguenti non vengono archiviati:

  - Trasferimenti di file peer-to-peer

  - Audio/video per i messaggi istantanei e le conferenze peer-to-peer

  - Condivisione di desktop e applicazioni per i messaggi istantanei e le conferenze peer-to-peer

Lync Server non archivia inoltre le conversazioni di chat persistenti. Per archiviare le conversazioni di chat persistenti, è necessario abilitare e configurare il servizio di conformità, che è un componente che può essere distribuito con Microsoft Lync Server 2013, il server di chat persistente. Per informazioni dettagliate, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>Come si inizia a usare l'archiviazione?

L'archiviazione viene automaticamente installata in ogni server front-end quando si distribuisce il server, ma l'archiviazione non è abilitata finché non viene configurata. Il modo in cui viene configurata è determinato dalla modalità di distribuzione dell'archiviazione:

  - **Archiviazione con l'integrazione di Microsoft Exchange.** Se si hanno utenti residenti in Exchange 2013 e le relative cassette postali sono state inserite in blocco sul posto, è possibile selezionare l'opzione per integrare lo spazio di archiviazione di Lync Server 2013 con lo spazio di archiviazione di Exchange. Se si sceglie l'opzione di integrazione di Microsoft Exchange, è possibile usare i criteri e le configurazioni di Exchange 2013 per controllare l'archiviazione dei dati di Lync Server 2013 per tali utenti.

  - **Archiviazione con i database di archiviazione di Lync Server.** Se si hanno utenti non residenti in Exchange 2013 o che non hanno inserito le cassette postali sul posto o se non si vuole usare l'integrazione di Microsoft Exchange per uno o tutti gli utenti della distribuzione, è possibile distribuire i database di archiviazione di Lync Server tramite SQL Server  per archiviare i dati di archiviazione per tali utenti. In questo caso, i criteri e le configurazioni di archiviazione di Lync Server 2013 determinano se l'archiviazione è abilitata e come viene implementata. Per usare Lync Server 2013, è necessario aggiungere i database di SQL Server appropriati alla topologia e pubblicare la topologia.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Archiviazione della configurazione quando si usa l'integrazione di Microsoft Exchange

Se gli utenti sono ospitati in Exchange 2013 e le cassette postali sono state inserite in blocco sul posto, è possibile scegliere l'opzione di **integrazione di Microsoft Exchange** (come descritto più avanti in questa sezione) per archiviare Lync Server 2013 per gli utenti e quindi controllare l'archiviazione per tali utenti specificando i criteri e le impostazioni di blocco sul posto e le configurazioni di Lync Server per controllare quanto segue:

  - Se archiviare messaggi istantanei, servizi di conferenza o entrambi.

  - Se implementare la modalità critica per la distribuzione di Lync Server.

  - Selezione dell'opzione di integrazione di Microsoft Exchange per l'uso di Exchange 2013 per l'archiviazione dei dati archiviati.

Queste opzioni di configurazione di archiviazione di Lync Server 2013 sono descritte più avanti in questa sezione. Per informazioni su come configurare i criteri e le impostazioni per il blocco sul posto di Exchange per supportare l'archiviazione, vedere la documentazione del prodotto Exchange 2013.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Archiviazione della configurazione quando si usa l'archiviazione di database di archiviazione di Lync Server

Se si vuole usare i database di archiviazione di Lync Server (con i database di SQL Server) per archiviare i dati per tutti gli utenti della distribuzione, è possibile configurare i criteri di archiviazione di Lync Server per controllare se l'archiviazione è abilitata per tali utenti. In ogni criterio di archiviazione è possibile abilitare o disabilitare l'archiviazione per una o entrambe le operazioni seguenti:

  - Comunicazioni interne

  - Comunicazioni esterne

Per impostazione predefinita, l'archiviazione non è abilitata per comunicazioni interne o comunicazioni esterne in qualsiasi criterio di archiviazione di Lync Server. È possibile abilitare e disabilitare le comunicazioni usando il pannello di controllo di Lync Server 2013 o usando i cmdlet in Lync Server 2013 Management Shell.

I criteri di archiviazione di Lync Server 2013 includono i seguenti:

  - **Criteri di archiviazione globale**. Questo è il criterio di archiviazione predefinito e si applica all'intera distribuzione. Viene creato quando si distribuisce Lync Server 2013 e, per impostazione predefinita, disattiva l'archiviazione per le comunicazioni interne ed esterne. Non è possibile eliminare questo criterio. Se si sceglie l'opzione Elimina, il criterio globale viene reimpostato sulle impostazioni predefinite.

  - **Criteri di archiviazione del sito**. Facoltativamente, è possibile abilitare o disabilitare l'archiviazione per uno o più siti specifici creando e configurando un criterio di archiviazione a livello di sito per il sito. Quando si creano criteri di archiviazione a livello di sito, per impostazione predefinita l'archiviazione non è abilitata. Puoi eliminare qualsiasi criterio di archiviazione a livello di sito creato. Un criterio di archiviazione a livello di sito sostituisce il criterio globale, ma solo per il sito specificato nel criterio. Ad esempio, se si Abilita l'archiviazione per le comunicazioni interne ed esterne nel criterio globale e si creano criteri per il sito in cui si disattiva l'archiviazione per le comunicazioni esterne, verranno archiviati solo le comunicazioni interne per il sito.

  - **Criteri di archiviazione degli utenti**. Facoltativamente, è possibile abilitare o disabilitare l'archiviazione per uno o più utenti e gruppi di utenti specifici creando, configurando e applicando un criterio di archiviazione a livello di utente per gli utenti specificati e per quelli utente. Quando si creano criteri di archiviazione a livello di utente, per impostazione predefinita l'archiviazione non è abilitata. Puoi eliminare qualsiasi criterio di archiviazione a livello di utente che crei e puoi modificare gli utenti e il gruppo di utenti a cui si applicano i criteri di archiviazione. Un criterio di archiviazione a livello di utente esegue l'override dei criteri globali e di tutti i criteri del sito, ma solo per gli utenti e gruppi di utenti a cui è applicato il criterio. Ad esempio, se si disattiva l'archiviazione per le comunicazioni interne ed esterne nel criterio globale, creare un criterio a livello di sito in cui abilitare l'archiviazione per le comunicazioni interne ed esterne e quindi creare un criterio a livello di utente in cui disabilitare Archiviazione per comunicazioni esterne, le comunicazioni verranno archiviate sia per le comunicazioni esterne che interne per tutti gli utenti del sito, ad eccezione del fatto che, per gli utenti a cui si applicano i criteri a livello di utente, verranno archiviati solo le comunicazioni interne.

Per informazioni dettagliate su come configurare i criteri di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [configurazione e assegnazione di criteri di archiviazione in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'uso dei criteri di archiviazione per abilitare e disabilitare le comunicazioni dopo la distribuzione, vedere [gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) nella documentazione Operations.

<div>


> [!NOTE]  
> Se si implementano entrambi i database di archiviazione di Lync Server 2013 e si Abilita l'integrazione di Microsoft Exchange, i criteri di Exchange 2013 eseguono l'override dei criteri di archiviazione di Lync Server, ma solo per gli utenti residenti in Exchange 2013 e hanno inserito le cassette postali sul posto . L'archiviazione di Lync dipende solo dai criteri di blocco sul posto di Microsoft Exchange.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>Quali opzioni sono disponibili per la configurazione dell'archiviazione?

Oltre a usare i criteri e per abilitare e disabilitare l'archiviazione, sono disponibili altre opzioni di archiviazione che possono essere configurate per l'intera distribuzione e, facoltativamente, per siti e pool specifici. È possibile controllare la maggior parte delle opzioni di archiviazione utilizzando una o più configurazioni di archiviazione, disponibili nel pannello di controllo di Lync Server 2013, ma anche un'altra opzione disponibile solo per la configurazione tramite Lync Server 2013 Management Shell.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Opzioni di configurazione dell'archiviazione disponibili nel pannello di controllo di Lync Server 2013

Ogni configurazione di archiviazione offre le opzioni seguenti:

La configurazione a livello globale viene creata automaticamente quando si distribuisce l'archiviazione e può essere configurata, ma non eliminata. Se si seleziona l'opzione per eliminare la configurazione globale, le impostazioni vengono reimpostate sui valori predefiniti. È possibile creare più configurazioni di siti e pool che, insieme alla configurazione globale, controllano le impostazioni di archiviazione. Per la configurazione globale e per ogni configurazione di sito e pool, sono disponibili le opzioni seguenti:

  - Disabilitare l'archiviazione, abilitare l'archiviazione solo per la messaggistica istantanea (IM) o consentire l'archiviazione sia della messaggistica istantanea che della conferenza.

  - Configurare la modalità critica per bloccare le sessioni di messaggistica istantanea e di conferenza in caso di errore di Lync Server. Tra gli errori sono inclusi i seguenti:
    
      - **Messaggistica istantanea**. Un problema con il servizio di archiviazione di Lync Server. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
      - **Servizio di conferenza**. L'errore potrebbe essere provocato da una condivisione file non disponibile o da un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica istantanea che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.

  - Specificare l'uso di Microsoft Exchange Server 2013 Integration per usare Exchange 2013 per l'archiviazione dei dati archiviati, invece di configurare i database di SQL Server separati per l'archiviazione dei dati di archiviazione di Lync Server 2013.

  - Configurare le opzioni di eliminazione per i dati archiviati. Ciò include la specifica quando eliminare i dati archiviati, che possono essere uno dei seguenti:
    
      - Dopo un determinato numero di giorni specificato
    
      - Dopo l'esportazione dei dati di archiviazione (che includono i dati caricati in Exchange, se si Abilita l'integrazione di Microsoft Exchange).
    
    <div>
    

    > [!NOTE]  
    > Se si Abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange 2013 e le cassette postali inserite in blocco sul posto è controllata da Exchange. L'unica qualifica è per i file di conferenza, archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione.

    
    </div>

Per impostazione predefinita, non sono abilitate le opzioni di archiviazione. È possibile gestire le configurazioni di archiviazione tramite il pannello di controllo di Lync Server 2013.

È possibile specificare le configurazioni di archiviazione seguenti:

  - **Configurazione di archiviazione globale**. Questa è la configurazione di archiviazione predefinita e si applica all'intera distribuzione. Viene creato quando si distribuisce Lync Server 2013 e, per impostazione predefinita, non consente la funzionalità di archiviazione. È possibile modificare la configurazione globale, ma non è possibile eliminarla. Se si sceglie l'opzione Elimina per la configurazione, la configurazione globale viene reimpostata sulle impostazioni predefinite.

  - **Configurazione di archiviazione del sito**. Facoltativamente, è possibile configurare l'archiviazione per uno o più siti specifici creando e configurando una configurazione di archiviazione a livello di sito per un singolo sito. Una configurazione di archiviazione a livello di sito esiste solo se è stata creata. È possibile modificare o eliminare qualsiasi configurazione di archiviazione a livello di sito. Una configurazione di archiviazione a livello di sito sostituisce la configurazione globale, ma solo per il sito specificato nella configurazione a livello di sito. Ad esempio, se si Abilita l'archiviazione solo per la messaggistica istantanea nella configurazione globale e si crea una configurazione del sito in cui è possibile abilitare l'archiviazione sia per la messaggistica istantanea che per i servizi di conferenza, i servizi di conferenza verranno archiviati solo per il sito e non per il resto dell'organizzazione.

  - **Configurazione di archiviazione del pool**. Facoltativamente, è possibile specificare le impostazioni di archiviazione per uno o più pool specifici creando e configurando una configurazione a livello di pool per il singolo pool. Una configurazione di archiviazione a livello di pool esiste solo se è stata creata. È possibile modificare ed eliminare qualsiasi configurazione di archiviazione a livello di pool. Una configurazione di archiviazione a livello di pool sostituisce la configurazione globale e qualsiasi configurazione di archiviazione del sito che potrebbe essere stata creata. Ad esempio, se si Abilita l'archiviazione solo per la messaggistica istantanea nella configurazione globale, creare una configurazione a livello di sito in cui è possibile abilitare l'archiviazione sia per la messaggistica istantanea che per i servizi di conferenza per il sito e quindi creare una configurazione a livello di pool in cui è possibile abilitare l'archiviazione solo per Messaggistica istantanea, le comunicazioni verranno archiviate per la messaggistica istantanea e la conferenza per tutti gli utenti del sito, ad eccezione degli utenti ospitati nel pool specificato nella configurazione a livello di pool. Per tutti gli altri utenti dell'organizzazione, l'archiviazione verrà abilitata solo per la messaggistica istantanea.

Per informazioni dettagliate su come configurare le configurazioni di archiviazione iniziali quando si distribuisce l'archiviazione, vedere [configurazione delle opzioni di archiviazione in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'uso dei criteri di archiviazione per abilitare e disabilitare le comunicazioni dopo la distribuzione, vedere [gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) nella documentazione delle operazioni.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Opzioni di archiviazione disponibili solo in Windows PowerShell

Usando Lync Server 2013 Management Shell, è possibile usare i cmdlet per implementare le opzioni non disponibili nel pannello di controllo di Lync Server 2013. Queste opzioni includono le seguenti:

  - **Archiviare i messaggi duplicati**. Per informazioni dettagliate, vedere [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) e [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) nella documentazione Operations.

  - **Esportare i dati archiviati**. Per informazioni dettagliate, vedere [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>Come si accede ai dati archiviati?

L'accesso ai dati archiviati dipende dalla posizione in cui sono archiviati i dati:

  - **Archiviazione di Microsoft Exchange**. Se si sceglie l'opzione di integrazione di Exchange, Lync Server archivia il contenuto di archiviazione nello Store di Exchange 2013 per tutti gli utenti residenti in Exchange 2013 e che hanno inserito le cassette postali in blocco sul posto. I dati archiviati sono archiviati nella cartella elementi ripristinabili delle cassette postali degli utenti, che in genere sono invisibili per l'utente e possono essere cercati solo dagli utenti con un ruolo di **Gestione individuazione** di Exchange. Exchange consente la ricerca e l'individuazione federate, insieme a SharePoint, se è distribuita. Per ulteriori informazioni sull'archiviazione, la conservazione e l'individuazione dei dati archiviati in Exchange, vedere la documentazione di Exchange 2013 e SharePoint.

  - **Archiviazione Lync Server**. Se si configurano i database di archiviazione di Lync Server 2013 per l'archiviazione dei dati di Lync Server, i depositi di Lync Server archiviano il contenuto nei database di archiviazione di Lync Server (database di SQL Server) per tutti gli utenti non residenti in Exchange 2013 e che non hanno inserito le cassette postali Blocco sul posto. Questi dati non sono ricercabili, ma possono essere esportati in formati ricercabili con altri strumenti. Per informazioni dettagliate sull'esportazione dei dati archiviati nei database di archiviazione, vedere [esportazione di dati archiviati da Lync Server 2013](lync-server-2013-exporting-archived-data.md) nella documentazione Operations.

Per altre informazioni sul funzionamento di Lync Server 2013 e Exchange 2013, vedere [supporto dell'integrazione di Exchange Server e SharePoint in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

