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
ms.openlocfilehash: a85a8ef64d43561a68dca7c850f79cc6a1632fc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="e050f-102">Configurare la Federazione per un provider di servizi di audioconferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e050f-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e050f-103">_**Ultimo argomento modificato:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="e050f-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="e050f-104">Se si desidera utilizzare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (Lync Server locale con Lync Online), è necessario configurare la Federazione tra la distribuzione di Lync locale e il partner ACP come server partner consentito.</span><span class="sxs-lookup"><span data-stu-id="e050f-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="e050f-105">È possibile configurare la Federazione aggiungendo il dominio del partner ACP e il server perimetrale (può anche essere denominato proxy di accesso) all'elenco dei domini federati per la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="e050f-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="e050f-106">Il partner ACP deve quindi aggiungere il nome FQDN del pool di server perimetrali locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="e050f-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="e050f-107">Contattare il provider ACP per ulteriori detailsYour partner ACP è quindi necessario aggiungere il nome di dominio completo del pool di server perimetrali locale all'elenco dei domini federati consentiti.</span><span class="sxs-lookup"><span data-stu-id="e050f-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="e050f-108">**Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**</span><span class="sxs-lookup"><span data-stu-id="e050f-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="e050f-109">Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire la procedura illustrata in [configurare il supporto per i domini esterni consentiti in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="e050f-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="e050f-110">Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP.</span><span class="sxs-lookup"><span data-stu-id="e050f-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="e050f-111">Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere definito dal proprio ACP come proxy di accesso.</span><span class="sxs-lookup"><span data-stu-id="e050f-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="e050f-112">**Specificare il nome di dominio completo del pool di server perimetrali per il partner ACP**</span><span class="sxs-lookup"><span data-stu-id="e050f-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="e050f-113">È necessario che il partner ACP configuri la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo l'FQDN del pool di server perimetrali come dominio federato consentito.</span><span class="sxs-lookup"><span data-stu-id="e050f-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

