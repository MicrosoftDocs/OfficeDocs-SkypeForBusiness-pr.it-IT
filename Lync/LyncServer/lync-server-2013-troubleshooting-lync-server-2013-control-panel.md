---
title: 'Lync Server 2013: risoluzione dei problemi relativi al pannello di controllo di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="1a1c2-102">Risoluzione dei problemi relativi al pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1c2-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a1c2-103">_**Argomento Ultima modifica:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="1a1c2-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="1a1c2-104">Questo argomento fornisce informazioni e procedure che consentono di risolvere i problemi di accesso al pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="1a1c2-105">Requisiti per i browser Internet</span><span class="sxs-lookup"><span data-stu-id="1a1c2-105">Internet Browser Requirements</span></span>

<span data-ttu-id="1a1c2-106">Il pannello di controllo di Lync Server richiede che il plug-in del browser di Microsoft Silverlight sia installato versione 4.0.50524.0 o ultima versione.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="1a1c2-107">Se Silverlight non è installato o se è installata una versione precedente, seguire le istruzioni del messaggio per installare la versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a1c2-108">Altri requisiti software per il pannello di controllo di Lync Server riguardano il sistema operativo in cui è possibile installare il pannello di controllo di Lync Server e tutti gli altri strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="1a1c2-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-server-and-tools-operating-system-support.md">supporto dei sistemi operativi server e strumenti in Lync server 2013</A> nella documentazione relativa al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="1a1c2-110">Se il browser Internet blocca l'installazione di Silverlight a causa di considerazioni sulla sicurezza, aggiungere l'URL (Uniform Resource Locator) che apre il pannello di controllo di Lync Server all'elenco dei siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="1a1c2-111">Nelle impostazioni di sicurezza di Internet Explorer verificare che i **controlli ActiveX e i plug-** in siano impostati su **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="1a1c2-112">Per informazioni dettagliate, [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)vedere.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="1a1c2-113">Verificare inoltre che il browser sia configurato per l'uso di SSL 3,0.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="1a1c2-114">Se il browser Internet è configurato per l'uso di un server proxy, verificare che il browser sia configurato per ignorare il server proxy per i siti che vengono rilevati automaticamente come siti interni.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="1a1c2-115">In alternativa, aggiungere l'indirizzo all'elenco delle eccezioni del browser nelle impostazioni di configurazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="1a1c2-116">Requisiti per i record DNS e i certificati per l'URL di accesso amministrativo</span><span class="sxs-lookup"><span data-stu-id="1a1c2-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="1a1c2-117">Se è stato configurato un semplice URL per accedere al pannello di controllo di Lync Server, è anche stato configurato il record di risorse DNS (Domain Name System) (A) statico e il certificato necessario per l'uso di tale URL di accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="1a1c2-118">Se si modifica l'URL di base in qualsiasi momento, assicurarsi che la modifica venga applicata al record DNS appropriato e al certificato e che si esegua *Enable-CsComputer* su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="1a1c2-119">Per informazioni dettagliate, vedere gli argomenti seguenti nella documentazione relativa alla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="1a1c2-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="1a1c2-120">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1c2-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="1a1c2-121">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1c2-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="1a1c2-122">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1c2-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="1a1c2-123">Per le procedure dettagliate per la configurazione dell'URL di accesso amministrativo, vedere [modificare o configurare URL semplici in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="1a1c2-124">Requisiti di Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="1a1c2-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="1a1c2-125">Il pannello di controllo di Lync Server è uno dei componenti di Lync Server 2013 che richiedono Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1a1c2-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="1a1c2-126">In particolare, assicurati che il reindirizzamento HTTP e le caratteristiche di autenticazione di Windows siano abilitati e che il servizio pubblicazione sul Web (W3SVC) sia in uso.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="1a1c2-127">Dipendenza del servizio di pubblicazione in tutto il mondo (servizio Windows)</span><span class="sxs-lookup"><span data-stu-id="1a1c2-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="1a1c2-128">Quando il servizio pubblicazione sul Web viene interrotto, non è possibile accedere al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="1a1c2-129">Puoi riavviare il servizio usando Microsoft Management Console (MMC) di Windows Services.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="1a1c2-130">**Per avviare il servizio pubblicazione sul Web**</span><span class="sxs-lookup"><span data-stu-id="1a1c2-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="1a1c2-131">Accedere al computer in cui è installato il servizio pubblicazione sul Web come parte di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1a1c2-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="1a1c2-132">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="1a1c2-133">Fare clic con il pulsante destro del mouse su **World Wide Web Publishing Service**e quindi scegliere **Start**.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="1a1c2-134">Modalità pool di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1a1c2-134">Application Pool Mode</span></span>

<span data-ttu-id="1a1c2-135">Configurare IIS in modo che il pool di applicazioni di CsManagementAppPool usi l'account del servizio di rete come identità del modello di processo.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="1a1c2-136">Diritti utente e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1a1c2-136">User Rights and Permissions</span></span>

<span data-ttu-id="1a1c2-137">È necessario accedere al pannello di controllo di Lync Server usando un account di dominio membro del gruppo CsAdministrator o usando un account a cui sono stati delegati i diritti e le autorizzazioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="1a1c2-138">Non è possibile accedere al pannello di controllo di Lync Server usando un account del computer locale.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="1a1c2-139">Per informazioni dettagliate sulla delega delle attività amministrative tramite il controllo di accesso basato sui ruoli (RBAC), vedere [pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="1a1c2-140">Se si usa un URL semplice per accedere al pannello di controllo di Lync Server, verificare che i server Web vengano aggiunti ai gruppi RTCUniversalServerAdmins e RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="1a1c2-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a1c2-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a1c2-141">See Also</span></span>


[<span data-ttu-id="1a1c2-142">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a1c2-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

