---
title: 'Lync Server 2013: configurazione delle opzioni di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 243414dea5b7ca411e4511c3a82f269c9981147e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a><span data-ttu-id="f5b18-102">Configurazione delle opzioni di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b18-102">Configuring Archiving options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5b18-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f5b18-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f5b18-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per specificare la modalità di implementazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-104">In Lync Server 2013 Control Panel, you use Archiving configurations to specify how archiving is implemented.</span></span> <span data-ttu-id="f5b18-105">Sono incluse le configurazioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5b18-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="f5b18-106">Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b18-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="f5b18-107">Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="f5b18-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="f5b18-108">Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="f5b18-109">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **Configurazione archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire le configurazioni a livello globale, a livello di sito e a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="f5b18-109">In Lync Server 2013 Control Panel, you can use the **Archiving Configuration** page of the **Archiving and Monitoring** group to manage configurations at the global level, site level, and pool level.</span></span> <span data-ttu-id="f5b18-110">Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="f5b18-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="f5b18-111">Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione, vedere [Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="f5b18-111">For details about how to manage configurations after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5b18-112">Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi gli utenti ospitati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b18-112">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="f5b18-113">Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne.</span><span class="sxs-lookup"><span data-stu-id="f5b18-113">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="f5b18-114">Prima di abilitare l'archiviazione nei criteri, è consigliabile specificare le configurazioni di archiviazione appropriate per la distribuzione e facoltativamente per siti e pool specifici, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-114">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f5b18-115">Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-115">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="f5b18-116">Se non si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi.</span><span class="sxs-lookup"><span data-stu-id="f5b18-116">If you do not use Microsoft Exchange integration for all users in your deployment, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="f5b18-117">Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne per l'archiviazione dei dati quando si utilizzano i database di archiviazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5b18-117">By default, archiving is not enabled for either internal or external communications for archiving of data when using Lync Server 2013 Archiving databases.</span></span> <span data-ttu-id="f5b18-118">Prima di abilitare l'archiviazione in qualsiasi criterio, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione corrente e, facoltativamente, per siti e pool specifici, come illustrato in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-118">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="f5b18-119">Per informazioni dettagliate sull'abilitazione dell'archiviazione per l'utilizzo con i database di archiviazione di Lync Server 2013, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f5b18-119">For details about enabling Archiving for use with Lync Server 2013 Archiving databases, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5b18-120">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f5b18-120">In This Section</span></span>

  - [<span data-ttu-id="f5b18-121">Configurazione delle opzioni di archiviazione a livello globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b18-121">Configuring Archiving options at the global level in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [<span data-ttu-id="f5b18-122">Configurazione delle opzioni di archiviazione per un sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b18-122">Configuring Archiving options for a site in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [<span data-ttu-id="f5b18-123">Configurazione delle opzioni di archiviazione per un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5b18-123">Configuring Archiving options for a pool in Lync Server 2013</span></span>](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

