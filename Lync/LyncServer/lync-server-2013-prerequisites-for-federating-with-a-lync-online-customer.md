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
ms.openlocfilehash: 337189476cf7c2767b359086014944715afbd623
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="1f2c3-102">Prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f2c3-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f2c3-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1f2c3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1f2c3-104">Per eseguire la Federazione con un cliente di Lync Online 2010, è necessario avere già completato la distribuzione e la configurazione iniziali di Lync Server 2013 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="1f2c3-105">Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f2c3-105">This includes the following:</span></span>

  - <span data-ttu-id="1f2c3-106">Distribuzione di almeno un server Standard Edition o un pool Front-end Enterprise Edition nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="1f2c3-107">Per informazioni dettagliate sulla distribuzione di server interni, vedere [distribuzione di Lync server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1f2c3-108">Abilitazione degli account utente interni per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="1f2c3-109">Per informazioni dettagliate, vedere [disabilitare o riattivare l'account utente per Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) nella documentazione relativa alla distribuzione o nella documentazione sulle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="1f2c3-110">Distribuzione di almeno un server perimetrale e gli altri componenti necessari per supportare l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="1f2c3-111">Per informazioni dettagliate, vedere [gestione della Federazione e accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="1f2c3-112">Abilitazione del supporto federativo all'interno dell'organizzazione e configurazione del metodo appropriato per il controllo dell'accesso da parte di domini federati.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="1f2c3-113">Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) e [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="1f2c3-114">Abilitazione dell'accesso utente esterno per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="1f2c3-115">Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) e nella documentazione relativa alla documentazione o alle operazioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1f2c3-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

