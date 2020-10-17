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
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a><span data-ttu-id="d2505-102">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="d2505-102">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2505-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d2505-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d2505-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per specificare la modalità di implementazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d2505-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="d2505-105">Sono incluse le configurazioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2505-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="d2505-106">Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2505-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="d2505-107">Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="d2505-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="d2505-108">Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d2505-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="d2505-109">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **Configurazione archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire le configurazioni a livello globale, a livello di sito e a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="d2505-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="d2505-110">Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="d2505-110">For details about how Archiving configurations are implemented, including which options you can specify, and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2505-111">Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per tutti gli utenti ospitati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2505-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for all users homed on Lync Server 2013.</span></span> <span data-ttu-id="d2505-112">Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne.</span><span class="sxs-lookup"><span data-stu-id="d2505-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="d2505-113">Se si utilizza l'integrazione di Microsoft Exchange, è necessario abilitare e configurare Exchange 2013 per supportare l'archiviazione per tutti gli utenti ospitati in Exchange 2013 che hanno le cassette postali inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="d2505-113">If you use Microsoft Exchange integration, you must enable and configure Exchange 2013 to support archiving for all users homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span><BR><span data-ttu-id="d2505-114">Prima di abilitare Archiviazione, è necessario specificare le configurazioni di Archiviazione appropriate per la distribuzione e, facoltativamente, per siti e pool specifici, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d2505-114">Prior to enabling Archiving, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="d2505-115">Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d2505-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="d2505-116">**Per visualizzare le informazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d2505-116">**To view archiving configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="d2505-117">È possibile visualizzare le informazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet **Get-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d2505-117">You can view Archiving configuration information by using Windows PowerShell and the **Get-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="d2505-118">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2505-118">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d2505-119">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d2505-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="d2505-120">In Lync Server Management Shell, utilizzare il seguente comando per visualizzare le informazioni su tutte le impostazioni di configurazione dell'archiviazione:</span><span class="sxs-lookup"><span data-stu-id="d2505-120">In the Lync Server Management Shell, use the following command to view information about all of your archiving configuration settings:</span></span>
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a><span data-ttu-id="d2505-121">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d2505-121">In This Section</span></span>

  - [<span data-ttu-id="d2505-122">Creazione di una configurazione di archiviazione in Lync Server 2013 per la gestione dell'archiviazione per siti o pool specifici</span><span class="sxs-lookup"><span data-stu-id="d2505-122">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [<span data-ttu-id="d2505-123">Abilitazione o disabilitazione dell'archiviazione delle sessioni di messaggistica istantanea o di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2505-123">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [<span data-ttu-id="d2505-124">Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2505-124">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [<span data-ttu-id="d2505-125">Abilitazione o disabilitazione della modalità critica in Lync Server 2013 per bloccare o consentire le sessioni di messaggistica istantanea e Web Conferencing se l'archiviazione ha esito negativo</span><span class="sxs-lookup"><span data-stu-id="d2505-125">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>](lync-server-2013-enable-disable-critical-mode.md)

  - [<span data-ttu-id="d2505-126">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2505-126">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="d2505-127">Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con l'archiviazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="d2505-127">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [<span data-ttu-id="d2505-128">Eliminazione di una configurazione di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2505-128">Deleting an Archiving configuration in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2505-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2505-129">See Also</span></span>


[<span data-ttu-id="d2505-130">Gestione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2505-130">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

