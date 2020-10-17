---
title: Configurazione dell'individuazione automatica per i dispositivi mobili con distribuzioni ibride
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3b0617094c9dcab6b6eee0cf634440fea63cf16
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502163"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="7e75d-102">Configurazione dell'individuazione automatica in Lync Server 2013 per dispositivi mobili con distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="7e75d-102">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e75d-103">_**Ultimo argomento modificato:** 2014-06-18_</span><span class="sxs-lookup"><span data-stu-id="7e75d-103">_**Topic Last Modified:** 2014-06-18_</span></span>

<span data-ttu-id="7e75d-104">Le distribuzioni ibride sono configurazioni che utilizzano sia il servizio cloud di Microsoft Lync Online sia la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="7e75d-104">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="7e75d-105">In questo tipo di configurazione, il servizio di individuazione automatica deve essere in grado di individuare l'effettiva posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7e75d-105">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="7e75d-106">Vale a dire che gli aiuti di individuazione automatica nella ricerca dell'account utente e in cui il server che ospita l'account dell'utente sono, indipendentemente dal modo in cui si trova nella distribuzione locale o nella distribuzione di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="7e75d-106">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="7e75d-107">Ad esempio, se l'account di un utente è ospitato in un server di Lync Online, il tentativo di individuare l'utente avverrà come indicato di seguito, in un processo noto come *individuabilità*:</span><span class="sxs-lookup"><span data-stu-id="7e75d-107">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="7e75d-108">L'utente avvia un tentativo di connessione alla distribuzione locale, **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="7e75d-108">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="7e75d-109">Il tentativo viene inviato a lyncdiscover.contoso.com, il nome DNS associato al servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="7e75d-109">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="7e75d-110">Il servizio di individuazione automatica si riferisce al pool di registrazione presunto nella distribuzione di contoso.com in locale e vengono fornite informazioni sul server principale effettivo dell'utente ospitato in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="7e75d-110">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="7e75d-111">A questo punto, il servizio di individuazione automatica invia all'utente una segnalazione al servizio di individuazione automatica online **lync.com**.</span><span class="sxs-lookup"><span data-stu-id="7e75d-111">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="7e75d-112">L'utente avvia un tentativo di connessione ai servizio di individuazione automatica online lync.com ed è in grado di individuare l'account utente e il server principale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7e75d-112">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="7e75d-p103">Per abilitare i client mobili per l'individuazione della distribuzione in cui si trova il server principale dell'utente, configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). Eseguire la procedura seguente per configurare il servizio di configurazione automatica.</span><span class="sxs-lookup"><span data-stu-id="7e75d-p103">To enable mobile clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL). Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="7e75d-115">Configurazione del servizio di individuazione automatica per le distribuzione ibride</span><span class="sxs-lookup"><span data-stu-id="7e75d-115">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="7e75d-116">Utilizzare Get-CsHostingProvider per recuperare il valore dell'attributo ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="7e75d-116">You use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="7e75d-117">Da Lync Server Management Shell, digitare</span><span class="sxs-lookup"><span data-stu-id="7e75d-117">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    <span data-ttu-id="7e75d-118">Dove \[ Identity \] viene sostituita con il nome di dominio dello spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="7e75d-118">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e75d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e75d-119">See Also</span></span>


<span data-ttu-id="7e75d-120">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7e75d-120">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>  
<span data-ttu-id="7e75d-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7e75d-121">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

