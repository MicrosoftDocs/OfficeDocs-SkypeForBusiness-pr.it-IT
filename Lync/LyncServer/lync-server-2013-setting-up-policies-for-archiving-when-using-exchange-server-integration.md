---
title: Impostazione dei criteri per l'archiviazione quando si utilizza l'integrazione di Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac425f08e3522c4ed885036c144c4c0f12e37b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="2c385-102">Impostazione dei criteri per l'archiviazione in Lync Server 2013 quando si utilizza l'integrazione di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2c385-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c385-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2c385-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2c385-104">Se gli utenti ospitati su Exchange 2013 dispongono delle cassette postali in blocco sul posto, i criteri di conservazione sul posto di Exchange controllano l'archiviazione per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="2c385-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="2c385-105">Se si utilizza l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange 2013 eseguono l'override dei criteri di archiviazione di Lync Server per gli utenti che si trovano in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2c385-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="2c385-106">Per informazioni sulla configurazione dei criteri di archiviazione di Exchange, vedere la documentazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2c385-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="2c385-107">Per informazioni dettagliate sulla configurazione dei criteri utente per gli utenti ospitati in Lync Server 2013, vedere [impostazione dei criteri utente per l'archiviazione in Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2c385-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="2c385-108">Per informazioni dettagliate sul funzionamento dei criteri, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2c385-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2c385-109">Se si distribuisce Exchange 2013 e Lync Server 2013 nella stessa foresta, i criteri di conservazione sul posto di Exchange 2013 sono archiviati per il controllo dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2c385-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="2c385-110">Se si distribuisce Exchange 2013 e Lync Server 2013 in foreste separate, vedere "Deploying Lync Server and Microsoft Exchange in different forests" nell' <A href="lync-server-2013-deployment-checklist-for-archiving.md">elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c385-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

