---
title: 'Lync Server 2013: incluso il desk di sicurezza'
description: 'Lync Server 2013: incluso il desk di sicurezza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a5b01dff5e3db8293944033f1f3b675bbc4d37
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547752"
---
# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="5053d-103">Inclusione del desk di sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5053d-103">Including the security desk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5053d-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5053d-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5053d-p101">Nella propria azienda potrebbe essere necessario coinvolgere il desk di sicurezza in una chiamata di emergenza. Per decidere come integrare il desk di sicurezza nella distribuzione del servizio per chiamate di emergenza E9-1-1, è consigliabile rispondere alle domande riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5053d-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="5053d-107">**Si desidera che il desk di sicurezza riceva notifica in caso di una chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="5053d-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="5053d-108">È possibile configurare il criterio percorso in modo che Lync Server invii avvisi di messaggistica istantanea agli indirizzi SIP Lync di uno o più addetti alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5053d-108">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="5053d-109">Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e consentono al personale della sicurezza di fornire più facilmente assistenza per la situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="5053d-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="5053d-110">**Si desidera invitare il desk di sicurezza in conferenza per ogni chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="5053d-110">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="5053d-p103">Se supportato dal provider dei servizi di emergenza, è possibile configurare i criteri di percorso in modo da includere un numero di richiamata per ogni chiamata di emergenza. Questo numero viene quindi utilizzato dal provider per invitare il personale della sicurezza dell'organizzazione a partecipare in conferenza alle chiamate di emergenza. Nei criteri di percorso, questa funzionalità di conferenza può essere configurata come unidirezionale (solo ascolto) o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="5053d-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5053d-p104">Se lo si desidera, è possibile configurare personale di emergenza diverso per i singoli criteri di percorso. In questo modo è possibile personalizzare la risposta per aree diverse nella società o creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno anziché dall'esterno della rete. Per specificare il personale a cui inviare la notifica, è possibile usare gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5053d-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

