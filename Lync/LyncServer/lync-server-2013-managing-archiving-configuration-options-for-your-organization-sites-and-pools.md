---
title: "Lync Server 2013: gestione delle opzioni di configurazione dell'archiviazione per l'organizzazione, i siti e i pool"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Nel pannello di controllo di Lync Server 2013 si usano le configurazioni di archiviazione per specificare la modalità di implementazione dell'archiviazione. Sono incluse le configurazioni di archiviazione seguenti:

  - Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e a livello di pool che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o pool specifici.

È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. Nel pannello di controllo di Lync Server 2013 è possibile usare la pagina **Configurazione archiviazione** del gruppo **archiviazione e monitoraggio** per gestire le configurazioni a livello globale, a livello di sito e a livello di pool. Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.

<div>


> [!NOTE]  
> Per usare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per tutti gli utenti ospitati in Lync Server 2013. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Se si usa l'integrazione di Microsoft Exchange, è necessario abilitare e configurare Exchange 2013 per supportare l'archiviazione per tutti gli utenti ospitati in Exchange 2013 che hanno inserito le cassette postali sul posto.<BR>Prima di abilitare l'archiviazione, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione e, facoltativamente, per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione di criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

**Per visualizzare le informazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare le informazioni di configurazione dell'archiviazione tramite Windows PowerShell e il cmdlet **Get-CsArchivingConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.
    
    In Lync Server Management Shell usare il comando seguente per visualizzare informazioni su tutte le impostazioni di configurazione dell'archiviazione:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Creazione di una configurazione di archiviazione in Lync Server 2013 per gestire l'archiviazione per siti o pool specifici](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Abilitazione o disabilitazione dell'archiviazione delle sessioni di messaggistica istantanea o di conferenza in Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Abilitazione o disabilitazione della modalità critica in Lync Server 2013 per bloccare o consentire la messaggistica istantanea e le sessioni di conferenza Web se l'archiviazione non riesce](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con lo spazio di archiviazione di Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Eliminazione di una configurazione di archiviazione in Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione dell'archiviazione in Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

