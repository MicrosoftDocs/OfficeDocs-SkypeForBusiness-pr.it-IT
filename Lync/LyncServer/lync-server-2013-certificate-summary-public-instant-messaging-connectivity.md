---
title: 'Lync Server 2013: riepilogo del certificato-connettività di messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="5b2b4-102">Riepilogo del certificato-connettività di messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b2b4-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b2b4-103">_**Argomento Ultima modifica:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="5b2b4-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="5b2b4-104">Per configurare i certificati per la connettività di messaggistica istantanea pubblica, è necessario prima di tutto notare che non c'è niente di diverso dagli altri tipi di federazione SIP o anche da certificati standard del server Edge, ad eccezione del fatto che America Online (AOL) richiede un unico configurazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="5b2b4-105">Oltre al consueto utilizzo della chiave avanzata per server (EKU), America Online richiede il certificato o i certificati (nel caso di un pool di bordi) che contengano anche l'EKU client.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="5b2b4-106">L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5b2b4-107">Riepilogo del certificato-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="5b2b4-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b2b4-108">Componente</span><span class="sxs-lookup"><span data-stu-id="5b2b4-108">Component</span></span></th>
<th><span data-ttu-id="5b2b4-109">Nome oggetto</span><span class="sxs-lookup"><span data-stu-id="5b2b4-109">Subject name</span></span></th>
<th><span data-ttu-id="5b2b4-110">Nomi alternativi oggetto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="5b2b4-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="5b2b4-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="5b2b4-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b2b4-112">Esterno/bordo di accesso</span><span class="sxs-lookup"><span data-stu-id="5b2b4-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="5b2b4-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b2b4-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b2b4-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b2b4-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="5b2b4-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b2b4-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="5b2b4-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5b2b4-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5b2b4-117">Il certificato deve provenire da una CA pubblica e deve avere il server EKU e il client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="5b2b4-118">Il certificato viene assegnato alle interfacce di Edge Server esterne per:</span><span class="sxs-lookup"><span data-stu-id="5b2b4-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b2b4-119">Access Edge Services</span><span class="sxs-lookup"><span data-stu-id="5b2b4-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="5b2b4-120">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="5b2b4-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="5b2b4-121">A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="5b2b4-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="5b2b4-122">Tieni presente che i SANs vengono aggiunti automaticamente al certificato in base alle tue definizioni in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="5b2b4-123">Si aggiungono le voci SAN in base alle esigenze per altri domini SIP e altre voci che è necessario supportare.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="5b2b4-124">Il nome del soggetto viene replicato nella SAN e deve essere presente per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="5b2b4-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b2b4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b2b4-125">See Also</span></span>


[<span data-ttu-id="5b2b4-126">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b2b4-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

