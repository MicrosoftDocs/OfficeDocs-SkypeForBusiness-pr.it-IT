---
title: Migrazione della federazione di XMPP
description: Migrazione della Federazione XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543212"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="0e863-103">Migrazione della federazione di XMPP</span><span class="sxs-lookup"><span data-stu-id="0e863-103">Migrating XMPP federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e863-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0e863-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0e863-105">Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="0e863-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="0e863-106">In Lync Server 2013, la funzionalità XMPP può essere distribuita come caratteristica.</span><span class="sxs-lookup"><span data-stu-id="0e863-106">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="0e863-107">La funzionalità XMPP è installata in due parti: come proxy XMPP eseguito sul server perimetrale di Lync Server 2013 e il gateway XMPP in esecuzione nel server front-end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-107">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="0e863-108">Dal punto di vista della migrazione, è possibile spostare un account utente di Lync Server in un pool Lync Server 2013 e continuare a utilizzare il gateway XMPP legacy.</span><span class="sxs-lookup"><span data-stu-id="0e863-108">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="0e863-109">Ciò è possibile solo quando il partner federato XMPP non è configurato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-109">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="0e863-110">In sintesi, se Lync Server 2010 è stato distribuito con il gateway XMPP di Office Communications Server 2007 R2 e la Federazione XMPP è stata abilitata per gli utenti legacy di Lync Server 2010, per eseguire la migrazione della Federazione XMPP a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0e863-110">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="0e863-111">Distribuire un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-111">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="0e863-112">Distribuire un server perimetrale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-112">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="0e863-113">Spostare tutti gli utenti nel pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e863-113">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="0e863-114">Creare criteri di accesso XMPP e certificati per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="0e863-114">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="0e863-115">Abilitare la Federazione XMPP in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-115">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="0e863-116">Aggiornare le voci DNS in modo che puntino al gateway XMPP di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e863-116">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

