---
title: 'Lync Server 2013: configurazione e assegnazione dei criteri di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b4e49bb6ba25fb9c7230cdf171dc7d31433619
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="de2e8-102">Configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2e8-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de2e8-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="de2e8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="de2e8-104">In Lync Server 2013, è possibile utilizzare i criteri per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne per gli utenti ospitati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de2e8-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="de2e8-105">Sono inclusi i criteri di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="de2e8-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="de2e8-106">Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de2e8-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="de2e8-107">Criteri a livello di sito e di utente facoltativi che è possibile creare e utilizzare per specificare la modalità di implementazione dell'archiviazione per siti o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="de2e8-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="de2e8-108">È inizialmente necessario impostare i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="de2e8-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="de2e8-109">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **criteri di archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire i criteri a livello globale, a livello di sito e a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="de2e8-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de2e8-110">Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni di configurazione dell'archiviazione, tra cui l'archiviazione (o meno) di messaggistica istantanea e conferenze, l'utilizzo della modalità critica e le opzioni di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="de2e8-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="de2e8-111">Per impostazione predefinita, nessuna delle opzioni nella configurazione dell'archiviazione globale o a livello di sito o pool è abilitata.</span><span class="sxs-lookup"><span data-stu-id="de2e8-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="de2e8-112">Prima di abilitare l'archiviazione delle comunicazioni interne o esterne nei criteri di archiviazione è necessario specificare tutte le opzioni appropriate nelle configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="de2e8-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="de2e8-113">Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="de2e8-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="de2e8-114">Se si integra l'archiviazione di Lync Server con l'archivio di Exchange 2013, i criteri utente di Exchange hanno la precedenza sui criteri di archiviazione di Lync Server 2013, ma solo per gli utenti che si trovano in Exchange 2013 che hanno le cassette postali inserite in archiviazione sul posto.</span><span class="sxs-lookup"><span data-stu-id="de2e8-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="de2e8-115">Per informazioni dettagliate sul modo in cui vengono implementati i criteri, inclusa la gerarchia dei criteri, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="de2e8-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="de2e8-116">Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="de2e8-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="de2e8-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="de2e8-117">In This Section</span></span>

  - [<span data-ttu-id="de2e8-118">Configurazione dei criteri globali per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2e8-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="de2e8-119">Impostazione dei criteri di sito per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2e8-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="de2e8-120">Configurazione dei criteri di archiviazione per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de2e8-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

