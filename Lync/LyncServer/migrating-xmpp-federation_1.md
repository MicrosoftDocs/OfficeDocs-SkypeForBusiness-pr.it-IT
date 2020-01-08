---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="cf220-102">Migrazione della federazione di XMPP</span><span class="sxs-lookup"><span data-stu-id="cf220-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf220-103">_**Argomento Ultima modifica:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="cf220-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cf220-104">Le versioni precedenti di Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="cf220-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="cf220-105">In Lync Server 2013 la funzionalità XMPP può essere distribuita come caratteristica.</span><span class="sxs-lookup"><span data-stu-id="cf220-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="cf220-106">La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito su Lync Server 2013 Edge Server e il gateway XMPP eseguito nel server front-end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="cf220-107">Da una prospettiva di migrazione, un account utente di Office Communications Server 2007 R2 può essere spostato in un pool di Lync Server 2013 e continuare a usare il gateway XMPP di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cf220-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="cf220-108">Questo è possibile solo quando il partner federato XMPP non è configurato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="cf220-109">In sintesi, se Office Communications Server è stato distribuito con il gateway XMPP di Office Communications Server 2007 R2 e la Federazione XMPP è stata abilitata per gli utenti legacy di Office Communications Server 2007 R2, per eseguire la migrazione della Federazione XMPP a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="cf220-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="cf220-110">Distribuire un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="cf220-111">Distribuire un server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="cf220-112">Trasferire tutti gli utenti nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="cf220-113">Creare criteri di accesso e certificati XMPP per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="cf220-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="cf220-114">Abilitare la Federazione XMPP in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="cf220-115">Aggiornare le voci DNS in punti al gateway XMPP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf220-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

