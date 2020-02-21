---
title: 'Lync Server 2013: dettagli della tabella del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e103fa03aa747e0c04a680507fe6d57bd6de04d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="94dc3-102">Dettagli della tabella del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94dc3-103">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="94dc3-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="94dc3-104">Negli argomenti seguenti vengono descritte le colonne di ogni tabella dello schema del database di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="94dc3-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94dc3-105">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="94dc3-105">In This Section</span></span>

  - [<span data-ttu-id="94dc3-106">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="94dc3-107">tblPrincipalMemberDifference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="94dc3-108">tblADUpdates in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="94dc3-109">tblPrincipalMembers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="94dc3-110">tblPrincipalMeta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="94dc3-111">tblSkippedAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="94dc3-112">PrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="94dc3-113">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="94dc3-114">tblPrincipalAffiliations in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="94dc3-115">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="94dc3-116">tblRoleType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="94dc3-117">tblScopePrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="94dc3-118">tblPrincipalRole in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="94dc3-119">tblSiopWhiteList in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="94dc3-120">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="94dc3-121">Nella in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="94dc3-122">tblPrincipalInvites in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="94dc3-123">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="94dc3-124">tblLastInviteId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="94dc3-125">LastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="94dc3-126">tblPreference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="94dc3-127">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="94dc3-128">Tabella tblServerIdentity in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="94dc3-129">tblAdminLock in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="94dc3-130">tblSystemRevision in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="94dc3-131">tblActivePeers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="94dc3-132">tblConfig in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="94dc3-133">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="94dc3-134">ComplianceFanout in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="94dc3-135">tblComplianceParticipant in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="94dc3-136">tblComplianceState in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94dc3-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

