---
title: 'Lync Server 2013: Prerequisiti e ruoli per la configurazione degli annunci'
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
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="620f5-102">Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f5-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="620f5-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="620f5-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="620f5-104">L'annuncio è una caratteristica di gestione delle chiamate vocali aziendali.</span><span class="sxs-lookup"><span data-stu-id="620f5-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="620f5-105">Questo argomento descrive le informazioni necessarie prima di poter configurare l'annuncio e le assegnazioni di ruolo necessarie per eseguire attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="620f5-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="620f5-106">In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa all'annuncio (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="620f5-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="620f5-107">Prerequisiti per la configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="620f5-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="620f5-108">L'applicazione di annuncio richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="620f5-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="620f5-109">Servizio applicazione</span><span class="sxs-lookup"><span data-stu-id="620f5-109">Application service</span></span>

  - <span data-ttu-id="620f5-110">Response Group Application</span><span class="sxs-lookup"><span data-stu-id="620f5-110">Response Group application</span></span>

  - <span data-ttu-id="620f5-111">Archivio file per contenere i file audio</span><span class="sxs-lookup"><span data-stu-id="620f5-111">File Store, to hold audio files</span></span>

<span data-ttu-id="620f5-112">Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="620f5-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="620f5-113">Ruoli di configurazione degli annunci</span><span class="sxs-lookup"><span data-stu-id="620f5-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="620f5-114">È possibile usare gli strumenti di amministrazione seguenti per configurare gli annunci:</span><span class="sxs-lookup"><span data-stu-id="620f5-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="620f5-115">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="620f5-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="620f5-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="620f5-116">Lync Server Management Shell</span></span>

<span data-ttu-id="620f5-117">La configurazione dell'applicazione di annunci richiede uno dei ruoli amministrativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="620f5-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="620f5-118">**CsVoiceAdministrator**   questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri relativi alla voce, incluse le impostazioni degli annunci.</span><span class="sxs-lookup"><span data-stu-id="620f5-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="620f5-119">**CsServerAdministrator**   questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi e configurare tutte le impostazioni di annuncio.</span><span class="sxs-lookup"><span data-stu-id="620f5-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="620f5-120">**CsAdministrator**   questo ruolo di amministratore può eseguire tutte le attività amministrative e modificare tutte le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="620f5-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="620f5-121">**CsViewOnlyAdministrator**   questo ruolo di amministratore può visualizzare la distribuzione per monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="620f5-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="620f5-122">Per informazioni dettagliate sui diritti degli utenti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="620f5-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="620f5-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="620f5-123">See Also</span></span>


[<span data-ttu-id="620f5-124">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f5-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="620f5-125">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f5-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

