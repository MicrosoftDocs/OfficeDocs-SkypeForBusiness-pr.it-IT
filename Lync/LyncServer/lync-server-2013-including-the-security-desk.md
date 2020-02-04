---
title: 'Lync Server 2013: incluso il servizio di sicurezza'
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
ms.openlocfilehash: d792626a973a790313b2cdc1bd9df9092175f28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="68034-102">Incluso il servizio di sicurezza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68034-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68034-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="68034-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="68034-104">La società può richiedere che il servizio di sicurezza venga coinvolto in una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="68034-104">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="68034-105">Per decidere come integrare il servizio di sicurezza nella distribuzione di E9-1-1, è necessario rispondere alle domande seguenti.</span><span class="sxs-lookup"><span data-stu-id="68034-105">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="68034-106">**Si vuole che il desk di sicurezza venga avvisato quando è presente una chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="68034-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="68034-107">È possibile configurare i criteri di posizione per consentire a Lync Server di inviare avvisi di messaggistica istantanea agli indirizzi SIP di Lync di uno o più addetti alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="68034-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="68034-108">Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e facilitano il personale di sicurezza nell'assistenza per la situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="68034-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="68034-109">**Si vuole eseguire una conferenza sul banco di sicurezza in ogni chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="68034-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="68034-110">Se supportato dal provider del servizio servizi di emergenza, è possibile configurare i criteri di posizione per includere un numero di callback con ogni chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="68034-110">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="68034-111">Questo numero viene quindi usato dal provider per organizzare il personale di sicurezza dell'organizzazione in chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="68034-111">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="68034-112">Questa conferenza può essere configurata nel criterio della posizione in modo unidirezionale (solo in ascolto) o bidirezionale (bidirezionali).</span><span class="sxs-lookup"><span data-stu-id="68034-112">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68034-113">Se lo si desidera, è possibile configurare personale di emergenza diverso per ogni criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="68034-113">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="68034-114">In questo modo, puoi personalizzare la risposta per diverse aree all'interno della tua azienda oppure creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno invece che all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="68034-114">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="68034-115">È possibile usare i gruppi di distribuzione per specificare il personale che si vuole inviare.</span><span class="sxs-lookup"><span data-stu-id="68034-115">You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

