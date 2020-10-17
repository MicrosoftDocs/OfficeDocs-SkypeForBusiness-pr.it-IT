---
title: 'Lync Server 2013: requisiti delle app di Windows Store per Lync'
description: 'Lync Server 2013: requisiti delle app di Windows Store di Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566502"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="d093c-103">Requisiti delle app di Windows Store di Lync per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d093c-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d093c-104">_**Ultimo argomento modificato:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="d093c-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="d093c-105">Le organizzazioni che dispongono di una distribuzione locale di Lync Server devono soddisfare i requisiti seguenti per supportare l'app Windows Store di Lync.</span><span class="sxs-lookup"><span data-stu-id="d093c-105">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d093c-106">Per Lync Server 2010, eseguire l'aggiornamento cumulativo per Lync Server 2010: febbraio 2012 (disponibile all'indirizzo <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) o versioni successive su tutti i server.</span><span class="sxs-lookup"><span data-stu-id="d093c-106">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="d093c-107">Per consentire agli utenti di partecipare alle riunioni, eseguire l'aggiornamento cumulativo per Lync Server 2010: ottobre 2012 (disponibile all'indirizzo <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) nei server.</span><span class="sxs-lookup"><span data-stu-id="d093c-107">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="d093c-108">Abilitare l'individuazione automatica, Lync Web App e i servizi ticket web sul server.</span><span class="sxs-lookup"><span data-stu-id="d093c-108">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="d093c-109">Abilitare l'autenticazione dei certificati nel front end server o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="d093c-109">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d093c-110">Il processo di registrazione degli utenti nel front end server o nel pool Front End è spesso definito come registrar. Per ulteriori informazioni, vedere [creazione di impostazioni di configurazione di registrazione in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d093c-110">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="d093c-111">Pubblicare i record delle risorse di alias DNS (CNAME) per il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d093c-111">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="d093c-112">Non è più necessario verificare che il punto di distribuzione dell'elenco di revoche di certificati (CRL, Certificate Revocation List) per il certificato emesso in Lync Server punti a una risorsa HTTP invece che a una risorsa LDAP.</span><span class="sxs-lookup"><span data-stu-id="d093c-112">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="d093c-113">Assicurarsi tuttavia che i computer client dispongano degli aggiornamenti di Windows più recenti.</span><span class="sxs-lookup"><span data-stu-id="d093c-113">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="d093c-114">Configurare i proxy HTTP nell'organizzazione per consentire il traffico HTTP relativo a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d093c-114">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="d093c-115">Aggiungere eccezioni per i servizi di individuazione automatica, Lync Web App e webticket, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d093c-115">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="d093c-116">Nei client, installare Windows 8,1 e la versione più recente di Lync Windows Store app per correggere un problema di accesso che si verifica generalmente quando si utilizzano più domini (ad esempio, quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="d093c-116">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="d093c-117">Se l'organizzazione sottoscrive Lync Online o Microsoft 365 e si utilizza il proprio nome di dominio, è necessario eseguire alcuni passaggi aggiuntivi per configurare la rete per l'individuazione automatica dei server Lync.</span><span class="sxs-lookup"><span data-stu-id="d093c-117">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="d093c-118">I requisiti di configurazione della rete sono gli stessi per l'app Lync Windows Store e Lync su dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d093c-118">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d093c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d093c-119">See Also</span></span>


[<span data-ttu-id="d093c-120">Distribuzione di Lync Windows Store app in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d093c-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
