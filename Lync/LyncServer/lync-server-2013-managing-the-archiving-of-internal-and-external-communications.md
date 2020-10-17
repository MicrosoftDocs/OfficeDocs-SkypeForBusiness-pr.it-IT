---
title: Gestione dell'archiviazione delle comunicazioni interne ed esterne
description: Gestione dell'archiviazione delle comunicazioni interne ed esterne.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564132"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="e3978-103">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3978-103">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3978-104">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e3978-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e3978-105">In Lync Server 2013, è possibile utilizzare i criteri di archiviazione per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne se non si utilizza l'integrazione di Microsoft Exchange o si dispone di utenti che non sono ospitati in Exchange 2013 con le cassette postali inserite In-Place.</span><span class="sxs-lookup"><span data-stu-id="e3978-105">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e3978-106">Sono inclusi i criteri di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3978-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="e3978-107">Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3978-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="e3978-108">Criteri a livello di sito e di utente facoltativi che è possibile creare e utilizzare per specificare la modalità di implementazione dell'archiviazione per siti o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="e3978-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="e3978-109">È inizialmente necessario impostare i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e3978-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="e3978-110">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la pagina **criteri di archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire i criteri a livello globale, a livello di sito e a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="e3978-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="e3978-111">Se si integra l'archiviazione di Lync Server con l'archiviazione di Exchange 2013, i criteri utente di Exchange hanno la precedenza sui criteri di archiviazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3978-111">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="e3978-112">Per informazioni dettagliate sul modo in cui vengono implementati i criteri, inclusa la gerarchia dei criteri, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e3978-112">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e3978-113">Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni di configurazione dell'archiviazione, tra cui l'archiviazione (o meno) di messaggistica istantanea e conferenze, l'utilizzo della modalità critica e le opzioni di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="e3978-113">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="e3978-114">Per impostazione predefinita, nessuna delle opzioni nella configurazione dell'archiviazione globale o a livello di sito o pool è abilitata.</span><span class="sxs-lookup"><span data-stu-id="e3978-114">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="e3978-115">Prima di abilitare l'archiviazione delle comunicazioni interne o esterne nei criteri di archiviazione è necessario specificare tutte le opzioni appropriate nelle configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3978-115">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="e3978-116">Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e3978-116">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="e3978-117">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place.</span><span class="sxs-lookup"><span data-stu-id="e3978-117">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e3978-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e3978-118">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3978-119">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="e3978-119">In This Section</span></span>

  - [<span data-ttu-id="e3978-120">Creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per siti o utenti specifici</span><span class="sxs-lookup"><span data-stu-id="e3978-120">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="e3978-121">Modifica di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per l'organizzazione, i siti o gli utenti</span><span class="sxs-lookup"><span data-stu-id="e3978-121">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="e3978-122">Applicazione di un criterio di archiviazione agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3978-122">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="e3978-123">Impostazione dei criteri per l'archiviazione in Lync Server 2013 quando si utilizza l'integrazione di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e3978-123">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="e3978-124">Eliminazione di un criterio di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3978-124">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

