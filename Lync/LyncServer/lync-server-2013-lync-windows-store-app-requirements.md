---
title: "Lync Server 2013: requisiti dell'app Lync di Windows Store"
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
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="68fee-102">Requisiti dell'app Lync di Windows Store per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fee-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68fee-103">_**Argomento Ultima modifica:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="68fee-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="68fee-104">Le organizzazioni con una distribuzione locale di Lync Server devono soddisfare i requisiti seguenti per supportare l'app Lync di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="68fee-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68fee-105">Per Lync Server 2010, eseguire l'aggiornamento cumulativo per Lync Server 2010:2012 febbraio (disponibile su <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) o versione successiva in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="68fee-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="68fee-106">Per consentire agli utenti di partecipare a riunioni, eseguire l'aggiornamento cumulativo per Lync Server 2010: ottobre 2012 (disponibile all'indirizzo <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) nei server.</span><span class="sxs-lookup"><span data-stu-id="68fee-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="68fee-107">Abilitare l'individuazione automatica, Lync Web App e i servizi di ticket web nel server.</span><span class="sxs-lookup"><span data-stu-id="68fee-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="68fee-108">Abilitare l'autenticazione dei certificati nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="68fee-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="68fee-109">Il processo di registrazione dell'utente nel server front-end o nel pool Front-end viene spesso indicato come registrar. Per informazioni dettagliate, vedere [creare impostazioni di configurazione del registrar in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="68fee-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="68fee-110">Pubblicare i record di risorse DNS alias (CNAME) per il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="68fee-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="68fee-111">Non è più necessario verificare che il punto di distribuzione dell'elenco di revoche di certificati (CRL) del certificato rilasciato a Lync Server punti a una risorsa HTTP invece che a una risorsa LDAP.</span><span class="sxs-lookup"><span data-stu-id="68fee-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="68fee-112">Verificare tuttavia che i computer client abbiano installato gli aggiornamenti più recenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="68fee-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="68fee-113">Configurare i proxy HTTP nell'organizzazione per consentire il traffico HTTP correlato a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68fee-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="68fee-114">Se necessario, aggiungere eccezioni per i servizi di individuazione automatica, Lync Web App e webticket.</span><span class="sxs-lookup"><span data-stu-id="68fee-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="68fee-115">Nei client installare Windows 8,1 e la versione più recente dell'app Lync di Windows Store per risolvere un problema di accesso che si verifica in genere quando si usano più domini, ad esempio quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**.</span><span class="sxs-lookup"><span data-stu-id="68fee-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="68fee-116">Se l'organizzazione sottoscrive Lync Online o Office 365 e si usa il proprio nome di dominio, è necessario eseguire alcuni passaggi aggiuntivi per configurare la rete per l'individuazione automatica dei server Lync.</span><span class="sxs-lookup"><span data-stu-id="68fee-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="68fee-117">I requisiti di configurazione della rete sono gli stessi per l'app Lync di Windows Store e Lync nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="68fee-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="68fee-118">Seguire le istruzioni "configurare la rete" nell'articolo wiki di Office 365 "configurare i dispositivi mobili Lync" disponibile all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="68fee-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="68fee-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68fee-119">See Also</span></span>


[<span data-ttu-id="68fee-120">Distribuzione dell'app Lync di Windows Store in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fee-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

