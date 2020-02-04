---
title: "Lync Server 2013: configurazione dell'individuazione automatica per distribuzioni ibride"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="16366-102">Configurazione dell'individuazione automatica in Lync Server 2013 per distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="16366-102">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16366-103">_**Argomento Ultima modifica:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="16366-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="16366-104">Le distribuzioni ibride sono configurazioni che usano sia il servizio cloud di Microsoft Lync Online che la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="16366-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="16366-105">In questo tipo di configurazione il servizio di individuazione automatica deve essere in grado di individuare la posizione in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="16366-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="16366-106">Vale a dire che l'individuazione automatica aiuta a trovare l'account utente e la posizione in cui il server che ospita l'account dell'utente è, indipendentemente dal fatto che si trovi nella distribuzione locale o nella distribuzione di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="16366-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="16366-107">Ad esempio, se l'account di un utente è ospitato in un server in Lync Online, il tentativo di individuare l'utente avverrà come indicato di seguito, in un processo noto come *individuabilità*:</span><span class="sxs-lookup"><span data-stu-id="16366-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="16366-108">L'utente avvia un tentativo di connessione alla distribuzione locale, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="16366-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="16366-109">Il tentativo viene inviato a lyncdiscover.contoso.com, il nome DNS associato al servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="16366-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="16366-110">L'individuazione automatica si riferisce al pool di registrar assunto presso la contoso.com nella distribuzione locale e viene fornita informazioni sul server Home effettivo dell'utente ospitato in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="16366-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="16366-111">L'individuazione automatica invia quindi all'utente un riferimento al servizio di individuazione automatica di **Lync.com** online.</span><span class="sxs-lookup"><span data-stu-id="16366-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="16366-112">L'utente avvia un tentativo di connessione al servizio di individuazione automatica di lync.com online ed è in grado di individuare l'account dell'utente e il server principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="16366-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="16366-113">Per consentire ai client di individuare la distribuzione in cui si trova il server Home dell'utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator).</span><span class="sxs-lookup"><span data-stu-id="16366-113">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="16366-114">Per configurare il servizio di individuazione automatica, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="16366-114">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="16366-115">Configurazione dell'individuazione automatica per distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="16366-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="16366-116">Nell'argomento [requisiti per il servizio di individuazione automatica per Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md)si usa Get-CsHostingProvider per recuperare il valore dell'attributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="16366-116">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="16366-117">In Lync Server Management Shell digitare</span><span class="sxs-lookup"><span data-stu-id="16366-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="16366-118">Dove \[identità\] viene sostituita con il nome di dominio dello spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="16366-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16366-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16366-119">See Also</span></span>


[<span data-ttu-id="16366-120">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="16366-120">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="16366-121">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="16366-121">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

