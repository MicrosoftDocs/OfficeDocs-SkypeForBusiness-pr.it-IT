---
title: Abilitazione o disabilitazione dell'archiviazione delle sessioni di messaggistica istantanea o di conferenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f2d9f08ade88a3c19dd861457a46200e7517a34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515513"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="da088-102">Abilitazione o disabilitazione dell'archiviazione delle sessioni di messaggistica istantanea o di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da088-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da088-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="da088-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="da088-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per abilitare e disabilitare l'archiviazione delle sessioni di messaggistica istantanea, di conferenza o entrambe.</span><span class="sxs-lookup"><span data-stu-id="da088-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="da088-105">Sono incluse le configurazioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="da088-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="da088-106">Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da088-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="da088-107">Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="da088-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="da088-108">Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="da088-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="da088-109">Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="da088-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="da088-110">Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi gli utenti ospitati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da088-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="da088-111">Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne.</span><span class="sxs-lookup"><span data-stu-id="da088-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="da088-112">Prima di abilitare l'archiviazione nei criteri, è consigliabile specificare le configurazioni di archiviazione appropriate per la distribuzione e facoltativamente per siti e pool specifici, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="da088-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="da088-113">Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="da088-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="da088-114">Se si decide dopo la distribuzione dell'archiviazione che si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server Exchange 2013 e tutti gli utenti sono ospitati nei server Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="da088-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="da088-115">Per eseguire questa operazione, è necessario utilizzare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="da088-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="da088-116">Per ulteriori informazioni, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni del database di archiviazione in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="da088-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="da088-117">Per abilitare o disabilitare l'archiviazione delle sessioni di messaggistica istantanea o di conferenza</span><span class="sxs-lookup"><span data-stu-id="da088-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="da088-118">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="da088-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da088-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da088-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="da088-120">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="da088-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da088-121">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="da088-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="da088-122">Selezionare la configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da088-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="da088-123">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.</span><span class="sxs-lookup"><span data-stu-id="da088-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="da088-124">Per abilitare l'archiviazione per le sessioni di messaggistica istantanea e le conferenze, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.</span><span class="sxs-lookup"><span data-stu-id="da088-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="da088-125">Per disabilitare l'archiviazione per il criterio, fare clic su **Disabilita archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="da088-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="da088-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="da088-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da088-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da088-127">See Also</span></span>


[<span data-ttu-id="da088-128">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="da088-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="da088-129">Configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da088-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

