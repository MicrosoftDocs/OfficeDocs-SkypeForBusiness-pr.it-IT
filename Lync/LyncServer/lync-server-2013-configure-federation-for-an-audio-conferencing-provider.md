---
title: 'Lync Server 2013: configurare la Federazione per un provider di servizi di audioconferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="9dc61-102">Configurare la Federazione per un provider di servizi di audioconferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dc61-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc61-103">_**Argomento Ultima modifica:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="9dc61-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="9dc61-104">Se si vuole usare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (Lync Server locale con Lync Online), è necessario configurare la Federazione tra la distribuzione locale di Lync e il partner ACP come server partner consentito.</span><span class="sxs-lookup"><span data-stu-id="9dc61-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="9dc61-105">È possibile configurare la Federazione aggiungendo il dominio partner ACP e il server perimetrale (può anche essere chiamato proxy di accesso) nell'elenco dei domini federati per la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="9dc61-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="9dc61-106">Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="9dc61-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="9dc61-107">Contattare il provider ACP per altri partner di detailsYour ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="9dc61-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="9dc61-108">**Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**</span><span class="sxs-lookup"><span data-stu-id="9dc61-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="9dc61-109">Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire i passaggi descritti in [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="9dc61-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="9dc61-110">Per il server perimetrale, aggiungere il nome di dominio completo del server Edge del partner ACP.</span><span class="sxs-lookup"><span data-stu-id="9dc61-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="9dc61-111">Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio proxy di accesso per i paesi ACP.</span><span class="sxs-lookup"><span data-stu-id="9dc61-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="9dc61-112">**Specificare il nome di dominio completo del pool di Edge Server per il partner ACP**</span><span class="sxs-lookup"><span data-stu-id="9dc61-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="9dc61-113">Il partner ACP deve configurare la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome FQDN del pool di Edge Server come dominio federato consentito.</span><span class="sxs-lookup"><span data-stu-id="9dc61-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

