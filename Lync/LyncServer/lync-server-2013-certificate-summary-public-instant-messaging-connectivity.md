---
title: 'Lync Server 2013: riepilogo dei certificati-connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcbcb7d00eb21f4dcbce2c8d632df44c10a43a26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b5f2c-102">Riepilogo dei certificati-connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5f2c-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5f2c-103">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b5f2c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b5f2c-104">Per configurare i certificati per la connettività per la messaggistica istantanea pubblica, è necessario prima di tutto notare che non vi è nulla di diverso da altri tipi di federazione SIP o persino certificati standard del server perimetrale, tranne per il fatto che America Online (AOL) richiede un'unica configurazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="b5f2c-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="b5f2c-105">Oltre al consueto utilizzo della chiave avanzata del server (EKU), in America Online è necessario che il certificato o i certificati (nel caso di un pool perimetrale) contengano anche l'EKU client.</span><span class="sxs-lookup"><span data-stu-id="b5f2c-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="b5f2c-106">L'EKU client è un'aggiunta al certificato e fa parte del certificato pubblico esterno assegnato al server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="b5f2c-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b5f2c-107">Riepilogo dei certificati - Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="b5f2c-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5f2c-108">Componente</span><span class="sxs-lookup"><span data-stu-id="b5f2c-108">Component</span></span></th>
<th><span data-ttu-id="b5f2c-109">Nome soggetto</span><span class="sxs-lookup"><span data-stu-id="b5f2c-109">Subject name</span></span></th>
<th><span data-ttu-id="b5f2c-110">Ordine/voci nomi alternativi del soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="b5f2c-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="b5f2c-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="b5f2c-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5f2c-112">Perimetro esterno/Access Edge</span><span class="sxs-lookup"><span data-stu-id="b5f2c-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="b5f2c-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5f2c-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b5f2c-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5f2c-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="b5f2c-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b5f2c-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="b5f2c-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b5f2c-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="b5f2c-117">Il certificato deve provenire da un'autorità di certificazione pubblica e deve disporre del server EKU e del client EKU se è necessario distribuire la connettività di messaggistica istantanea pubblica con AOL.</span><span class="sxs-lookup"><span data-stu-id="b5f2c-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="b5f2c-118">Il certificato viene assegnato alle interfacce del server perimetrale esterno per:</span><span class="sxs-lookup"><span data-stu-id="b5f2c-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="b5f2c-119">Servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="b5f2c-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="b5f2c-120">Servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="b5f2c-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="b5f2c-121">Servizio A/V Edge</span><span class="sxs-lookup"><span data-stu-id="b5f2c-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="b5f2c-p103">Si noti che i SAN vengono aggiunti automaticamente al certificato in base alle definizioni fornite nel Generatore di topologie. Le voci SAN vengono aggiunte in base alle esigenze per i domini SIP aggiuntivi e per altre voci di cui è richiesto il supporto. Il nome soggetto viene replicato nel SAN e deve essere presente per il funzionamento corretto.</span><span class="sxs-lookup"><span data-stu-id="b5f2c-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5f2c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5f2c-125">See Also</span></span>


[<span data-ttu-id="b5f2c-126">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5f2c-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

