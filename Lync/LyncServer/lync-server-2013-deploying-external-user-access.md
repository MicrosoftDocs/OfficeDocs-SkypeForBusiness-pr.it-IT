---
title: "Lync Server 2013: Distribuzione dell'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba083650b9a068d48e28bf8af0c51b4b25b5c227
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c74ec-102">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74ec-103">_**Argomento Ultima modifica:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="c74ec-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="c74ec-104">La distribuzione di componenti Edge per Microsoft Lync Server 2013 consente agli utenti esterni che non hanno eseguito l'accesso alla rete interna dell'organizzazione, inclusi utenti remoti autenticati e anonimi, partner federati (inclusi i partner XMPP) client mobili e utenti di servizi di messaggistica istantanea pubblici per comunicare con altri utenti dell'organizzazione tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c74ec-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="c74ec-105">I processi di distribuzione e configurazione per Lync Server 2013 non sono significativamente diversi da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c74ec-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="c74ec-106">Gli strumenti per l'installazione e l'amministrazione sono molto simili a quelli di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c74ec-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c74ec-107">L'installazione e la&nbsp;configurazione di Microsoft Lync Server 2013 Edge Server possono essere un processo complesso che richiede una pianificazione e un coordinamento potenzialmente significativi con i team interni, inclusi, ad esempio, la sicurezza, la rete, il firewall, il DNS (Domain Name System), il servizio di bilanciamento del carico e le considerazioni sull'infrastruttura a chiave pubblica (PKI).</span><span class="sxs-lookup"><span data-stu-id="c74ec-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="c74ec-108">È consigliabile rivedere e usare il processo di pianificazione e la documentazione forniti prima di distribuire i componenti di Access esterni.</span><span class="sxs-lookup"><span data-stu-id="c74ec-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="c74ec-109">Questo aiuterà a limitare il numero e la frequenza delle modifiche e dei problemi indesiderati durante il processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c74ec-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="c74ec-110">Per informazioni sulla pianificazione dell'accesso degli utenti esterni, vedere <A href="lync-server-2013-planning-for-external-user-access.md">pianificazione per l'accesso degli utenti esterni in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c74ec-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c74ec-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c74ec-111">In This Section</span></span>

  - [<span data-ttu-id="c74ec-112">Elenco di controllo di distribuzione per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="c74ec-113">Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="c74ec-114">Preparazione dell'installazione dei server nella rete perimetrale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="c74ec-115">Creazione di una topologia di server perimetrali e server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="c74ec-116">[Configurazione del Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c74ec-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="c74ec-117">Configurazione di server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="c74ec-118">Configurare server proxy inversi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="c74ec-119">Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="c74ec-120">Guida al provisioning della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="c74ec-121">Configurazione di federazione SIP, federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="c74ec-122">Distribuzione delle funzionalità per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="c74ec-123">Verifica della distribuzione dei componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ec-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

