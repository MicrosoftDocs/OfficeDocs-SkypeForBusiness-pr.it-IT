---
title: Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ac1b54f03463972c49b2e4584f1b9f72d16c03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="f3156-102">Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3156-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3156-103">_**Ultimo argomento modificato:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f3156-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f3156-104">Le conferenze telefoniche con accesso esterno sono un componente facoltativo del carico di lavoro Lync Server 2013 Conferencing.</span><span class="sxs-lookup"><span data-stu-id="f3156-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="f3156-105">I componenti che è necessario installare prima di poter configurare le conferenze telefoniche con accesso esterno vengono distribuiti quando si utilizza il generatore di topologie per progettare la topologia e quindi configurare il pool Front end o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3156-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="f3156-106">In questo argomento vengono descritte le operazioni necessarie prima di poter configurare le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f3156-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="f3156-107">In questa sezione si presuppone che siano state lette le sezioni di pianificazione relative al carico di lavoro per le conferenze e alle conferenze telefoniche con accesso esterno in particolare.</span><span class="sxs-lookup"><span data-stu-id="f3156-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="f3156-108">Prerequisiti per la configurazione delle conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="f3156-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="f3156-109">Per le conferenze telefoniche con accesso esterno sono necessari i componenti di Lync Server 2013 seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3156-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="f3156-110">Unified Communications Application Service (unificate) (denominato *servizio applicazione*)</span><span class="sxs-lookup"><span data-stu-id="f3156-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="f3156-111">Applicazione Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="f3156-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="f3156-112">Applicazione Annuncio conferenza</span><span class="sxs-lookup"><span data-stu-id="f3156-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="f3156-113">Pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="f3156-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="f3156-114">Almeno un Mediation Server Lync Server 2013 e almeno un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f3156-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="f3156-115">Questi componenti vengono distribuiti quando si utilizza il generatore di topologie per definire e pubblicare la topologia e quindi distribuire un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3156-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f3156-116">Se si sta distribuendo VoIP aziendale, è consigliabile distribuirlo prima di configurare le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f3156-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="f3156-117">Se non si sta distribuendo VoIP aziendale, è possibile distribuire un Mediation Server e un gateway PSTN (Public Switched Telephone Network) quando si distribuisce il pool Front end o il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3156-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f3156-118">Se si esegue l'aggiornamento da Office Communications Server 2007 R2 a Lync Server 2013, distribuire le conferenze telefoniche con accesso esterno in ogni pool che si intende utilizzare per ospitare le conferenze di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3156-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="f3156-119">Per informazioni dettagliate sulla migrazione delle conferenze telefoniche con accesso esterno, vedere <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f3156-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f3156-120">In questa sezione si presuppone che siano state eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3156-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="f3156-121">Applicati gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2, se si esegue la migrazione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3156-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="f3156-122">Utilizzato generatore di topologie per progettare e configurare la topologia.</span><span class="sxs-lookup"><span data-stu-id="f3156-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="f3156-123">Durante la specifica del carico di lavoro per le conferenze, è stata selezionata l'opzione conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f3156-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="f3156-124">Per informazioni dettagliate sulla definizione della topologia, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f3156-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="f3156-125">Pubblicazione della topologia e configurazione del pool Front end o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f3156-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="f3156-126">Per informazioni dettagliate sulla pubblicazione della topologia e sull'installazione di Lync Server 2013, vedere [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f3156-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f3156-127">Quando si installa la topologia pubblicata, la pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno è installata nel server front end server o Standard Edition come parte dei servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="f3156-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f3156-128">Se si modifica il percorso dell'archivio file in Generatore di topologie dopo la distribuzione di Lync Server 2013, è necessario riavviare l'operatore conferenza e le applicazioni di annuncio per le conferenze per utilizzare il nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="f3156-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="f3156-129">Distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f3156-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="f3156-130">Se non si sta distribuendo VoIP aziendale, è stato collocato un Mediation Server nel server Enterprise Edition front end o nel server Standard Edition oppure è stato distribuito un Mediation Server autonomo ed è stato distribuito un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f3156-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="f3156-131">Per informazioni dettagliate sulla distribuzione di VoIP aziendale, vedere [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f3156-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="f3156-132">Per informazioni dettagliate sull'installazione di un Mediation Server autonomo e di un gateway PSTN, vedere [Deploying Mediation Servers and define Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f3156-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f3156-133">Nel diagramma di flusso seguente sono illustrati i passaggi che è necessario eseguire prima di poter configurare le conferenze telefoniche con accesso esterno e i passaggi da eseguire per configurare le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f3156-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="f3156-134">**Distribuzione di servizi di conferenza telefonica con accesso esterno**</span><span class="sxs-lookup"><span data-stu-id="f3156-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="f3156-135">![Diagramma di flusso di distribuzione delle conferenze telefoniche con accesso esterno](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagramma di flusso di distribuzione delle conferenze telefoniche con accesso esterno")</span><span class="sxs-lookup"><span data-stu-id="f3156-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="f3156-136">Autorizzazioni per le conferenze telefoniche con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="f3156-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="f3156-137">Per configurare le conferenze telefoniche con accesso esterno, è necessario utilizzare gli strumenti di amministrazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3156-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="f3156-138">Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3156-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="f3156-139">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f3156-139">Lync Server Management Shell</span></span>

<span data-ttu-id="f3156-140">È possibile utilizzare questi strumenti di amministrazione per configurare le impostazioni delle conferenze telefoniche con accesso esterno e i dial plan, i criteri e le altre impostazioni necessarie per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f3156-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="f3156-141">La configurazione delle conferenze telefoniche con accesso esterno richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:</span><span class="sxs-lookup"><span data-stu-id="f3156-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="f3156-142">**CsVoiceAdministrator**   questo ruolo di amministratore è in grado di creare, configurare e gestire le impostazioni e i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="f3156-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="f3156-143">**CsUserAdministrator**   questo ruolo di amministratore può abilitare e disabilitare gli utenti per Lync Server e assegnare criteri esistenti, ad esempio i criteri di conferenza e i criteri PIN, agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f3156-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="f3156-144">**CsAdministrator**   questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f3156-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3156-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3156-145">See Also</span></span>


[<span data-ttu-id="f3156-146">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3156-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

