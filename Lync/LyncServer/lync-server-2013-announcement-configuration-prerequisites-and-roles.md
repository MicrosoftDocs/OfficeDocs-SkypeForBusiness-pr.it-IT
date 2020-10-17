---
title: 'Lync Server 2013: prerequisiti e ruoli per la configurazione degli annunci'
description: 'Lync Server 2013: prerequisiti e ruoli per la configurazione degli annunci.'
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
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561892"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="f4b9e-103">Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9e-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4b9e-104">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f4b9e-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f4b9e-105">Annuncio è una funzionalità di gestione delle chiamate vocali di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="f4b9e-106">In questo argomento vengono descritte le operazioni necessarie per poter configurare l'annuncio e le assegnazioni di ruolo necessarie per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="f4b9e-107">In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa all'annuncio (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="f4b9e-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="f4b9e-108">Prerequisiti per la configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="f4b9e-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="f4b9e-109">L'applicazione annuncio richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4b9e-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="f4b9e-110">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="f4b9e-110">Application service</span></span>

  - <span data-ttu-id="f4b9e-111">Applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="f4b9e-111">Response Group application</span></span>

  - <span data-ttu-id="f4b9e-112">Archivio file, per la memorizzazione dei file audio</span><span class="sxs-lookup"><span data-stu-id="f4b9e-112">File Store, to hold audio files</span></span>

<span data-ttu-id="f4b9e-113">Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="f4b9e-114">Ruoli di configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="f4b9e-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="f4b9e-115">È possibile utilizzare gli strumenti di amministrazione seguenti per configurare gli annunci:</span><span class="sxs-lookup"><span data-stu-id="f4b9e-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="f4b9e-116">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f4b9e-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="f4b9e-117">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f4b9e-117">Lync Server Management Shell</span></span>

<span data-ttu-id="f4b9e-118">La configurazione dell'applicazione annuncio richiede uno dei ruoli amministrativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4b9e-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="f4b9e-119">**CsVoiceAdministrator**     Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali, incluse le impostazioni degli annunci.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="f4b9e-120">**CsServerAdministrator**     Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi, nonché configurare tutte le impostazioni degli annunci.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="f4b9e-121">**CsAdministrator**     Questo ruolo di amministratore è in grado di eseguire tutte le attività amministrative e di modificare tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="f4b9e-122">**CsViewOnlyAdministrator**     Questo ruolo di amministratore può visualizzare la distribuzione per monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4b9e-123">Per informazioni dettagliate sui diritti utente amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f4b9e-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4b9e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4b9e-124">See Also</span></span>


[<span data-ttu-id="f4b9e-125">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9e-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="f4b9e-126">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4b9e-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

