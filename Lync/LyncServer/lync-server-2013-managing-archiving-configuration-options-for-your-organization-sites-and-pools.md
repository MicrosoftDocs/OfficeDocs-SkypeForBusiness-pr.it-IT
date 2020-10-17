---
title: "Lync Server 2013: gestione delle opzioni di configurazione dell'archiviazione per l'organizzazione, i siti e i pool"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498363"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per specificare la modalità di implementazione dell'archiviazione. Sono incluse le configurazioni di archiviazione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.

Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione. Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **Configurazione archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire le configurazioni a livello globale, a livello di sito e a livello di pool. Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per tutti gli utenti ospitati in Lync Server 2013. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Se si utilizza l'integrazione di Microsoft Exchange, è necessario abilitare e configurare Exchange 2013 per supportare l'archiviazione per tutti gli utenti ospitati in Exchange 2013 che hanno le cassette postali inserite In-Place blocco.<BR>Prima di abilitare Archiviazione, è necessario specificare le configurazioni di Archiviazione appropriate per la distribuzione e, facoltativamente, per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

**Per visualizzare le informazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell**

  - È possibile visualizzare le informazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet **Get-CsArchivingConfiguration** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    In Lync Server Management Shell, utilizzare il seguente comando per visualizzare le informazioni su tutte le impostazioni di configurazione dell'archiviazione:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Creazione di una configurazione di archiviazione in Lync Server 2013 per la gestione dell'archiviazione per siti o pool specifici](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Abilitazione o disabilitazione dell'archiviazione delle sessioni di messaggistica istantanea o di conferenza in Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Abilitazione o disabilitazione della modalità critica in Lync Server 2013 per bloccare o consentire le sessioni di messaggistica istantanea e Web Conferencing se l'archiviazione ha esito negativo](lync-server-2013-enable-disable-critical-mode.md)

  - [Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con l'archiviazione di Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

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

