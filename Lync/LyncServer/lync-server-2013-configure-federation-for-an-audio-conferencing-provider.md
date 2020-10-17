---
title: 'Lync Server 2013: configurare la Federazione per un provider di servizi di audioconferenza'
description: 'Lync Server 2013: configurare la Federazione per un provider di servizi di audioconferenza.'
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
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553322"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="0046d-103">Configurare la Federazione per un provider di servizi di audioconferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0046d-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0046d-104">_**Ultimo argomento modificato:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="0046d-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="0046d-105">Se si desidera utilizzare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (Lync Server locale con Lync Online), è necessario configurare la Federazione tra la distribuzione di Lync locale e il partner ACP come server partner consentito.</span><span class="sxs-lookup"><span data-stu-id="0046d-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="0046d-106">È possibile configurare la Federazione aggiungendo il dominio del partner ACP e il server perimetrale (può anche essere denominato proxy di accesso) all'elenco dei domini federati per la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="0046d-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="0046d-107">Il partner ACP deve quindi aggiungere il nome FQDN del pool di server perimetrali locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="0046d-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="0046d-108">Contattare il provider ACP per ulteriori detailsYour partner ACP è quindi necessario aggiungere il nome di dominio completo del pool di server perimetrali locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="0046d-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="0046d-109">**Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**</span><span class="sxs-lookup"><span data-stu-id="0046d-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="0046d-110">Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire la procedura illustrata in [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="0046d-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="0046d-111">Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP.</span><span class="sxs-lookup"><span data-stu-id="0046d-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="0046d-112">Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere definito dal proprio ACP come proxy di accesso.</span><span class="sxs-lookup"><span data-stu-id="0046d-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="0046d-113">**Specificare il nome di dominio completo del pool di server perimetrali per il partner ACP**</span><span class="sxs-lookup"><span data-stu-id="0046d-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="0046d-114">È necessario che il partner ACP configuri la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo l'FQDN del pool di server perimetrali come dominio federato consentito.</span><span class="sxs-lookup"><span data-stu-id="0046d-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

