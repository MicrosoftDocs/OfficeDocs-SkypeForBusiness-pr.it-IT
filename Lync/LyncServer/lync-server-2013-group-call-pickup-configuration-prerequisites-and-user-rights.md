---
title: Prerequisiti e diritti utente per la configurazione del prelievo delle chiamate di gruppo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498793"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="c8292-102">Prerequisiti di configurazione del prelievo delle chiamate di gruppo e diritti utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8292-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8292-103">_**Ultimo argomento modificato:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c8292-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c8292-104">Prelievo delle chiamate di gruppo è una funzionalità di gestione delle chiamate installata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c8292-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c8292-105">In questo argomento vengono descritte le operazioni necessarie per poter configurare il prelievo delle chiamate di gruppo e i diritti utente necessari per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c8292-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="c8292-106">In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al prelievo delle chiamate di gruppo (vedere [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="c8292-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="c8292-107">Prerequisiti per la configurazione del prelievo delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="c8292-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="c8292-108">Il prelievo delle chiamate di gruppo richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8292-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="c8292-109">Servizio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="c8292-109">Application service</span></span>

  - <span data-ttu-id="c8292-110">Applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="c8292-110">Call Park application</span></span>

<span data-ttu-id="c8292-111">Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c8292-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="c8292-112">Configurazione del prelievo delle chiamate di gruppo diritti utente</span><span class="sxs-lookup"><span data-stu-id="c8292-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="c8292-113">È possibile utilizzare gli strumenti di amministrazione seguenti per configurare il prelievo delle chiamate di gruppo:</span><span class="sxs-lookup"><span data-stu-id="c8292-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="c8292-114">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c8292-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="c8292-115">Strumento del Resource Kit di SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c8292-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="c8292-116">Utilizzo di Lync Server Management Shell per la creazione e la gestione dei gruppi di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8292-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="c8292-117">Utilizzare lo strumento SEFAUtil Resource Kit per assegnare un gruppo di prelievo di chiamata e abilitare il prelievo delle chiamate di gruppo per gli utenti o per disabilitare il prelievo delle chiamate di gruppo per gli utenti</span><span class="sxs-lookup"><span data-stu-id="c8292-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="c8292-118">La configurazione del prelievo delle chiamate di gruppo richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:</span><span class="sxs-lookup"><span data-stu-id="c8292-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="c8292-119">**CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="c8292-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="c8292-120">**CsUserAdministrator:** Questo ruolo di amministratore può abilitare il prelievo delle chiamate di gruppo per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c8292-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="c8292-121">Dispone inoltre dell'accesso per la visualizzazione di sola lettura di tutte le configurazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="c8292-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="c8292-122">**CsServerAdministrator:** Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi.</span><span class="sxs-lookup"><span data-stu-id="c8292-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="c8292-123">**CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c8292-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c8292-124">Per informazioni dettagliate sui diritti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c8292-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8292-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8292-125">See Also</span></span>


[<span data-ttu-id="c8292-126">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8292-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="c8292-127">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8292-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

