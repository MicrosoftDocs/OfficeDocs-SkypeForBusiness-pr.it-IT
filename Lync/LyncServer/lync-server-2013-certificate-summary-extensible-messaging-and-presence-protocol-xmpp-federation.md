---
title: 'Lync Server 2013: riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol)'
description: 'Lync Server 2013: riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e2bb593d909c2eec6032dc89c07cc5f5b1a72db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572342"
---
# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="812d5-103">Riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="812d5-103">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="812d5-104">_**Ultimo argomento modificato:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="812d5-104">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="812d5-p101">Tra i requisiti dei certificati per consentire e stabilire le comunicazioni con partner XMPP (Extensible Messaging and Presence Protocol) è previsto il record aggiuntivo dei domini XMPP. Il record incluso nel certificato come nome alternativo del soggetto (SAN) corrisponderà al dominio che può partecipare alle comunicazioni XMPP. Il dominio può essere a livello della radice (ad esempio, contoso.com) se si desidera abilitare XMPP per l'intero dominio oppure può corrispondere a domini figlio selezionati (ad esempio, corp.contoso.com, finance.contoso.com) se si desidera abilitare XMPP per un sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="812d5-p101">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains. The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications. The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="812d5-108">Riepilogo certificati per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="812d5-108">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="812d5-109">Componente</span><span class="sxs-lookup"><span data-stu-id="812d5-109">Component</span></span></th>
<th><span data-ttu-id="812d5-110">Nome soggetto</span><span class="sxs-lookup"><span data-stu-id="812d5-110">Subject name</span></span></th>
<th><span data-ttu-id="812d5-111">Ordine/voci nomi alternativi del soggetto (SAN)</span><span class="sxs-lookup"><span data-stu-id="812d5-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="812d5-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="812d5-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="812d5-113">Assegnare al servizio Access Edge Server perimetrale o pool Edge</span><span class="sxs-lookup"><span data-stu-id="812d5-113">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="812d5-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="812d5-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="812d5-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="812d5-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="812d5-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="812d5-116">sip.contoso.com</span></span></p>
<p><span data-ttu-id="812d5-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="812d5-117">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="812d5-118">contoso.com</span><span class="sxs-lookup"><span data-stu-id="812d5-118">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="812d5-119">Le prime tre voci di SAN sono le normali voci di SAN per un server perimetrale completo.</span><span class="sxs-lookup"><span data-stu-id="812d5-119">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="812d5-120">La voce contoso.com è necessaria per la federazione con il partner XMPP a livello del dominio radice.</span><span class="sxs-lookup"><span data-stu-id="812d5-120">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="812d5-121">Questa voce consentirà XMPP per tutti i domini con il suffisso contoso.com.</span><span class="sxs-lookup"><span data-stu-id="812d5-121">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="812d5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="812d5-122">See Also</span></span>


[<span data-ttu-id="812d5-123">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="812d5-123">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="812d5-124">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="812d5-124">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="812d5-125">Configurare i certificati perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="812d5-125">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="812d5-126">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="812d5-126">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="812d5-127">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="812d5-127">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

