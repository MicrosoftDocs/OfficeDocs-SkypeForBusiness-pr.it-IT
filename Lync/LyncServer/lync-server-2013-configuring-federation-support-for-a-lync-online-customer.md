---
title: 'Lync Server 2013: configurazione del supporto federativo per un cliente di Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76582be324977d5466d234a37e4352806dd6d92f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="12972-102">Configurazione del supporto federativo per un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12972-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12972-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12972-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12972-104">È possibile specificare i servizi di comunicazione per gli utenti dell'organizzazione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12972-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="12972-105">La distribuzione di Lync Server 2013 nell'organizzazione (noti come *Servizi locali*) e la configurazione degli account utente di Lync 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12972-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="12972-106">Configurare un account del cliente di Microsoft Lync Online 2010 con un provider di hosting e configurare gli account utente con il provider di hosting (noto come *servizi online*).</span><span class="sxs-lookup"><span data-stu-id="12972-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="12972-107">Se si distribuisce Lync 2013 nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti di Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="12972-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="12972-108">Per abilitare la Federazione tra gli utenti della distribuzione locale di Lync 2013 e gli utenti di un cliente di Lync Online 2010, è necessario configurare il supporto per il dominio e gli utenti del cliente di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="12972-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12972-109">Questa documentazione descrive solo le procedure per la configurazione dell'organizzazione in modo da supportare la Federazione con un cliente di Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="12972-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="12972-110">Questa documentazione non descrive le procedure per la configurazione del cliente di Lync Online 2010 per supportare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="12972-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="12972-111">Per informazioni dettagliate sui servizi Lync Online, vedere Lync Online <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="12972-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12972-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="12972-112">In This Section</span></span>

  - [<span data-ttu-id="12972-113">Prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12972-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="12972-114">Configurare il supporto federativo per un dominio Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12972-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="12972-115">Configurare l'accesso degli utenti per la Federazione con un cliente Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12972-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="12972-116">Verificare le comunicazioni con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12972-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

