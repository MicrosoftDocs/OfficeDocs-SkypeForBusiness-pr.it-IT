---
title: Controllo di ammissione di chiamata con un PBX o un gateway PSTN di terze parti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="51ec8-102">Controllo di ammissione di chiamata in Lync Server 2013 con un PBX o un gateway PSTN di terze parti</span><span class="sxs-lookup"><span data-stu-id="51ec8-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51ec8-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="51ec8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="51ec8-104">Questo argomento descrive alcuni esempi di come il controllo di ammissione di chiamata (CAC) può essere distribuito sul collegamento tra l'interfaccia gateway di Mediation Server e un gateway PSTN (Public Branch Exchange Network) di terze parti o un PBX privato.</span><span class="sxs-lookup"><span data-stu-id="51ec8-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="51ec8-105">Caso 1: CAC tra il Mediation Server e un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="51ec8-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="51ec8-106">CAC può essere distribuito sul collegamento WAN dall'interfaccia gateway di Mediation Server a un gateway PBX o PSTN di terze parti.</span><span class="sxs-lookup"><span data-stu-id="51ec8-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="51ec8-107">**Caso 1: CAC tra il Mediation Server e un gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="51ec8-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="51ec8-108">![Caso 1: controllo di ammissione di chiamata tra il Mediation Server e un gateway PSTN](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: controllo di ammissione di chiamata tra il Mediation Server e un gateway PSTN")</span><span class="sxs-lookup"><span data-stu-id="51ec8-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="51ec8-109">In questo esempio, CAC viene applicato tra il Mediation Server e un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="51ec8-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="51ec8-110">Se un utente client di Lync nel sito di rete 1 inserisce una chiamata PSTN tramite il gateway PSTN nel sito di rete 2, il file multimediale passa attraverso il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="51ec8-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="51ec8-111">Vengono pertanto eseguiti due controlli CAC per ogni sessione PSTN:</span><span class="sxs-lookup"><span data-stu-id="51ec8-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="51ec8-112">Tra l'applicazione client Lync e il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="51ec8-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="51ec8-113">Tra il Mediation Server e il gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="51ec8-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="51ec8-114">Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un'applicazione client nel sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51ec8-115">Verificare che la subnet IP a cui appartiene il gateway PSTN sia configurata e associata al sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="51ec8-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="51ec8-116">Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="51ec8-117">Per informazioni dettagliate, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51ec8-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="51ec8-118">Caso 2: CAC tra il Mediation Server e un PBX di terze parti con il punto di terminazione multimediale</span><span class="sxs-lookup"><span data-stu-id="51ec8-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="51ec8-119">Questa configurazione è simile al caso 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="51ec8-120">In entrambi i casi, il Mediation Server sa quale dispositivo termina il contenuto multimediale all'estremità opposta del collegamento WAN e l'indirizzo IP del gateway PSTN o del PBX con il punto di terminazione multimediale (MTP) è configurato nel server Mediation come hop successivo.</span><span class="sxs-lookup"><span data-stu-id="51ec8-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="51ec8-121">**Caso 2: CAC tra il Mediation Server e un PBX di terze parti con MTP**</span><span class="sxs-lookup"><span data-stu-id="51ec8-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="51ec8-122">![Caso 2: controllo di ammissione di chiamata tra il Mediation Server e un PBX con MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: controllo di ammissione di chiamata tra il Mediation Server e un PBX con MTP")</span><span class="sxs-lookup"><span data-stu-id="51ec8-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="51ec8-123">In questo esempio, CAC viene applicato tra il Mediation Server e il PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="51ec8-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="51ec8-124">Se un utente di Lync client nel sito di rete 1 effettua una chiamata PSTN tramite il PBX/MTP situato nel sito di rete 2, il contenuto multimediale passa attraverso il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="51ec8-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="51ec8-125">Pertanto, per ogni sessione PSTN vengono eseguiti due controlli CAC:</span><span class="sxs-lookup"><span data-stu-id="51ec8-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="51ec8-126">Tra l'applicazione client Lync e il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="51ec8-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="51ec8-127">Tra il Mediation Server e il PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="51ec8-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="51ec8-128">Questo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un client nel sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51ec8-129">Verificare che la subnet IP a cui appartiene il MTP sia configurata e associata al sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="51ec8-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="51ec8-130">Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="51ec8-131">Per informazioni dettagliate, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51ec8-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="51ec8-132">Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza un punto di interruzione multimediale</span><span class="sxs-lookup"><span data-stu-id="51ec8-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="51ec8-133">Il caso 3 è leggermente diverso dai primi due casi.</span><span class="sxs-lookup"><span data-stu-id="51ec8-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="51ec8-134">Se non c'è un MTP nel PBX di terze parti, per una richiesta di sessione in uscita al PBX di terze parti, il Mediation Server non sa dove verranno terminati i contenuti multimediali nel limite del PBX.</span><span class="sxs-lookup"><span data-stu-id="51ec8-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="51ec8-135">In questo caso, il contenuto multimediale passa direttamente tra il Mediation Server e il dispositivo endpoint di terze parti.</span><span class="sxs-lookup"><span data-stu-id="51ec8-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="51ec8-136">**Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza MTP**</span><span class="sxs-lookup"><span data-stu-id="51ec8-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="51ec8-137">![Caso 3: controllo di ammissione di chiamata tra il Mediation Server e un PBX senza MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: controllo di ammissione di chiamata tra il Mediation Server e un PBX senza MTP")</span><span class="sxs-lookup"><span data-stu-id="51ec8-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="51ec8-138">In questo esempio, se un utente client di Lync nel sito di rete 1 effettua una chiamata a un utente tramite il PBX, il Mediation Server è in grado di eseguire i controlli CAC solo sulla gamba del proxy (tra l'applicazione client Lync e il Mediation Server).</span><span class="sxs-lookup"><span data-stu-id="51ec8-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="51ec8-139">Poiché il Mediation Server non contiene informazioni sul dispositivo endpoint durante la richiesta della sessione, non è possibile eseguire controlli CAC sul collegamento WAN (tra il Mediation Server e l'endpoint di terze parti) prima di chiamare establishment.</span><span class="sxs-lookup"><span data-stu-id="51ec8-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="51ec8-140">Dopo aver stabilito la sessione, tuttavia, il Mediation Server facilita la contabilizzazione della larghezza di banda usata nel trunk.</span><span class="sxs-lookup"><span data-stu-id="51ec8-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="51ec8-141">Per le chiamate che derivano dall'endpoint di terze parti, le informazioni relative al dispositivo endpoint sono disponibili al momento della richiesta di sessione e il controllo CAC può essere eseguito su entrambi i lati del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="51ec8-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51ec8-142">Verificare che la subnet IP a cui appartengono i dispositivi endpoint sia configurata e associata al sito di rete 2.</span><span class="sxs-lookup"><span data-stu-id="51ec8-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="51ec8-143">Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.</span><span class="sxs-lookup"><span data-stu-id="51ec8-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="51ec8-144">Per informazioni dettagliate, vedere <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51ec8-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

