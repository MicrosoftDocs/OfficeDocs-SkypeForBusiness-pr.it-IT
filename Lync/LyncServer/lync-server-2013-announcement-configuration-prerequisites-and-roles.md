---
title: 'Lync Server 2013: prerequisiti e ruoli per la configurazione degli annunci'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531693"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="9e04b-102">Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e04b-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e04b-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9e04b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9e04b-104">Annuncio è una funzionalità di gestione delle chiamate vocali di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9e04b-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="9e04b-105">In questo argomento vengono descritte le operazioni necessarie per poter configurare l'annuncio e le assegnazioni di ruolo necessarie per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9e04b-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="9e04b-106">In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa all'annuncio (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="9e04b-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="9e04b-107">Prerequisiti per la configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="9e04b-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="9e04b-108">L'applicazione annuncio richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e04b-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="9e04b-109">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="9e04b-109">Application service</span></span>

  - <span data-ttu-id="9e04b-110">Applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="9e04b-110">Response Group application</span></span>

  - <span data-ttu-id="9e04b-111">Archivio file, per la memorizzazione dei file audio</span><span class="sxs-lookup"><span data-stu-id="9e04b-111">File Store, to hold audio files</span></span>

<span data-ttu-id="9e04b-112">Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9e04b-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="9e04b-113">Ruoli di configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="9e04b-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="9e04b-114">È possibile utilizzare gli strumenti di amministrazione seguenti per configurare gli annunci:</span><span class="sxs-lookup"><span data-stu-id="9e04b-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="9e04b-115">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="9e04b-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="9e04b-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9e04b-116">Lync Server Management Shell</span></span>

<span data-ttu-id="9e04b-117">La configurazione dell'applicazione annuncio richiede uno dei ruoli amministrativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e04b-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="9e04b-118">**CsVoiceAdministrator**     Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali, incluse le impostazioni degli annunci.</span><span class="sxs-lookup"><span data-stu-id="9e04b-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="9e04b-119">**CsServerAdministrator**     Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi, nonché configurare tutte le impostazioni degli annunci.</span><span class="sxs-lookup"><span data-stu-id="9e04b-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="9e04b-120">**CsAdministrator**     Questo ruolo di amministratore è in grado di eseguire tutte le attività amministrative e di modificare tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9e04b-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="9e04b-121">**CsViewOnlyAdministrator**     Questo ruolo di amministratore può visualizzare la distribuzione per monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9e04b-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e04b-122">Per informazioni dettagliate sui diritti utente amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9e04b-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9e04b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e04b-123">See Also</span></span>


[<span data-ttu-id="9e04b-124">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e04b-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="9e04b-125">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e04b-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

