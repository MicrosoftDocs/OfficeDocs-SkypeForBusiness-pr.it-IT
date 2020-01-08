---
title: 'Lync Server 2013: riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b21c8b09d93f8d2788424f2c8f440e1dec66b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="71b58-102">Riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71b58-102">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b58-103">_**Argomento Ultima modifica:** 2012-12-23_</span><span class="sxs-lookup"><span data-stu-id="71b58-103">_**Topic Last Modified:** 2012-12-23_</span></span>

<span data-ttu-id="71b58-104">I requisiti di certificato per l'abilitazione e la creazione di comunicazioni con i partner del protocollo XMPP (Extensible Messaging and Presence Protocol) richiedono il record aggiuntivo dei domini XMPP.</span><span class="sxs-lookup"><span data-stu-id="71b58-104">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require the additional record of your XMPP domains.</span></span> <span data-ttu-id="71b58-105">Il record incluso nel certificato come nome alternativo soggetto (SAN) sarà il dominio che può partecipare alle comunicazioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="71b58-105">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="71b58-106">Il dominio può essere il dominio a livello di radice (ad esempio contoso.com) se si vuole abilitare XMPP per l'intero dominio oppure i domini figlio selezionati, ad esempio corp.contoso.com, finance.contoso.com, se si Abilita XMPP per un sottoinsieme di utenti.</span><span class="sxs-lookup"><span data-stu-id="71b58-106">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="71b58-107">Riepilogo del certificato per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="71b58-107">Certificate Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71b58-108">Componente</span><span class="sxs-lookup"><span data-stu-id="71b58-108">Component</span></span></th>
<th><span data-ttu-id="71b58-109">Nome oggetto</span><span class="sxs-lookup"><span data-stu-id="71b58-109">Subject name</span></span></th>
<th><span data-ttu-id="71b58-110">Nomi alternativi oggetto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="71b58-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="71b58-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="71b58-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71b58-112">Assegna a servizio Edge di Access di Edge Server o pool di Edge</span><span class="sxs-lookup"><span data-stu-id="71b58-112">Assign to Access Edge service of Edge Server or Edge pool</span></span></p></td>
<td><p><span data-ttu-id="71b58-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71b58-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71b58-114">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71b58-114">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="71b58-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71b58-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="71b58-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="71b58-116">sip.fabrikam.com</span></span></p>
<p><span data-ttu-id="71b58-117">contoso.com</span><span class="sxs-lookup"><span data-stu-id="71b58-117">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71b58-118">Le prime tre voci SAN sono le normali voci di SAN per un server perimetrale completo.</span><span class="sxs-lookup"><span data-stu-id="71b58-118">The first three SAN entries are the normal SAN entries for a full Edge Server.</span></span> <span data-ttu-id="71b58-119">Contoso.com è la voce necessaria per la Federazione con il partner XMPP a livello di dominio radice.</span><span class="sxs-lookup"><span data-stu-id="71b58-119">The contoso.com is the entry required for federation with the XMPP partner at the root domain level.</span></span> <span data-ttu-id="71b58-120">Questa voce consentirà XMPP per tutti i domini con il suffisso contoso.com.</span><span class="sxs-lookup"><span data-stu-id="71b58-120">This entry will allow XMPP for all domains with the suffix contoso.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71b58-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71b58-121">See Also</span></span>


[<span data-ttu-id="71b58-122">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="71b58-122">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="71b58-123">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71b58-123">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  


[<span data-ttu-id="71b58-124">Configurare i certificati perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71b58-124">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
[<span data-ttu-id="71b58-125">Request-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="71b58-125">Request-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[<span data-ttu-id="71b58-126">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="71b58-126">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

