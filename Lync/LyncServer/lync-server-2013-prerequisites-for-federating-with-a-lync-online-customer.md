---
title: 'Lync Server 2013: prerequisiti per la Federazione con un cliente di Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a562331ea1672e380a095fc32eba5ea27275465
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506753"
---
# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="a2e04-102">Prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e04-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e04-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a2e04-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a2e04-104">Per la Federazione con un cliente di Lync Online 2010, è necessario avere già completato la distribuzione iniziale e la configurazione di Lync Server 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2e04-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="a2e04-105">Sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2e04-105">This includes the following:</span></span>

  - <span data-ttu-id="a2e04-106">Distribuzione di almeno un server Standard Edition o un pool Enterprise Edition front end nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2e04-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="a2e04-107">Per informazioni dettagliate sulla distribuzione di server interni, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a2e04-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a2e04-108">Abilitazione degli account utente interni per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2e04-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="a2e04-109">Per ulteriori informazioni, vedere [disabilitare o riabilitare l'account utente per Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a2e04-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="a2e04-110">Distribuzione di almeno un server perimetrale e gli altri componenti necessari per il supporto dell'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="a2e04-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="a2e04-111">Per informazioni dettagliate, vedere [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a2e04-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a2e04-112">Abilitazione del supporto per la federazione nell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="a2e04-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="a2e04-113">Per ulteriori informazioni, vedere [abilitare o disabilitare l'accesso degli utenti remoti in Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) e [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a2e04-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="a2e04-114">Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2e04-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="a2e04-115">Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) e nella documentazione relativa alla distribuzione o alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a2e04-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

