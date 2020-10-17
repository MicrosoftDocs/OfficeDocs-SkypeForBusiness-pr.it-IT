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
ms.openlocfilehash: cbb7421f204ded840dc627354b0d66627840c594
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517533"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="d6b29-102">Configurazione del supporto federativo per un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b29-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6b29-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d6b29-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d6b29-104">È possibile fornire servizi di comunicazione agli utenti dell'organizzazione in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6b29-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="d6b29-105">La distribuzione di Lync Server 2013 nell'organizzazione (noti come *Servizi locali*) e la configurazione degli account utente di Lync 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6b29-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="d6b29-106">Configurare un account cliente di Microsoft Lync Online 2010 con un provider di hosting e impostare gli account utente con il provider di hosting (noto come *servizi online*).</span><span class="sxs-lookup"><span data-stu-id="d6b29-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="d6b29-107">Se si distribuisce Lync 2013 nell'organizzazione, è possibile eseguire la Federazione con i domini di uno o più clienti di Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="d6b29-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="d6b29-108">Per abilitare la Federazione tra gli utenti della distribuzione di Lync 2013 locale e gli utenti di un cliente di Lync Online 2010, è necessario configurare il supporto per il dominio e gli utenti del cliente di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d6b29-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6b29-109">In questa documentazione vengono descritte solo le procedure per la configurazione dell'organizzazione per il supporto della Federazione con un cliente di Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="d6b29-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="d6b29-110">In questa documentazione non sono descritte le procedure per la configurazione del cliente Lync Online 2010 per il supporto della Federazione.</span><span class="sxs-lookup"><span data-stu-id="d6b29-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="d6b29-111">Per informazioni dettagliate sui servizi Lync Online, vedere Lync Online all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> .</span><span class="sxs-lookup"><span data-stu-id="d6b29-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6b29-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d6b29-112">In This Section</span></span>

  - [<span data-ttu-id="d6b29-113">Prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b29-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="d6b29-114">Configurare il supporto federativo per un dominio Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b29-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="d6b29-115">Configurare l'accesso utente per la Federazione con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b29-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="d6b29-116">Verificare le comunicazioni con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b29-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

