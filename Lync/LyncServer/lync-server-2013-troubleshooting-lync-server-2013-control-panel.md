---
title: 'Lync Server 2013: risoluzione dei problemi del pannello di controllo di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da23bc56d18b1b5e6235551f7b99cc15e658fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535933"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="3d3c6-102">Risoluzione dei problemi relativi al Pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3c6-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d3c6-103">_**Ultimo argomento modificato:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="3d3c6-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="3d3c6-104">In questo argomento vengono fornite informazioni e procedure che consentono di risolvere i problemi relativi all'accesso al pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="3d3c6-105">Requisiti per il browser Internet</span><span class="sxs-lookup"><span data-stu-id="3d3c6-105">Internet Browser Requirements</span></span>

<span data-ttu-id="3d3c6-106">Per il pannello di controllo di Lync Server è necessario che sia installato il plug-in del browser Microsoft Silverlight 4.0.50524.0 o versione più recente.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="3d3c6-107">Se Silverlight non è installato o se è installata una versione precedente, seguire le istruzioni riportate nel messaggio per installare la versione desiderata.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d3c6-108">Altri requisiti software per il pannello di controllo di Lync Server sono relativi al sistema operativo in cui è possibile installare il pannello di controllo di Lync Server e tutti gli altri strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="3d3c6-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in Lync server 2013</A> nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="3d3c6-110">Se il browser Internet blocca l'installazione di Silverlight a causa di considerazioni sulla sicurezza, aggiungere l'URL (Uniform Resource Locator) che apre il pannello di controllo di Lync Server all'elenco dei siti attendibili.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="3d3c6-111">Nelle impostazioni di sicurezza di Internet Explorer assicurarsi che l'opzione **Esegui controlli ActiveX e plug-in** sia impostata su **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="3d3c6-112">Per informazioni dettagliate, vedere [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) .</span><span class="sxs-lookup"><span data-stu-id="3d3c6-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="3d3c6-113">Assicurarsi inoltre che il browser sia configurato per l'utilizzo di SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="3d3c6-p104">Se il browser Internet è configurato per l'utilizzo di un server proxy, verificare che il browser sia configurato per il bypass del server proxy per i siti rilevati automaticamente come siti interni. In alternativa aggiungere l'indirizzo all'elenco delle eccezioni del browser nelle impostazioni di configurazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="3d3c6-116">Requisiti per record DNS e certificati per l'URL di accesso amministrativo</span><span class="sxs-lookup"><span data-stu-id="3d3c6-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="3d3c6-117">Se è stato configurato un URL semplice per accedere al pannello di controllo di Lync Server, è necessario configurare anche il record di risorse host DNS (A) e il certificato necessari per l'utilizzo di tale URL di accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="3d3c6-118">Se si modifica l'URL di base in qualsiasi momento, verificare che la modifica venga riflessa nel record e nel certificato DNS appropriato e che venga eseguito il metodo *Enable-CsComputer* in ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="3d3c6-119">Per informazioni dettagliate, vedere gli argomenti seguenti nella documentazione relativa alla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="3d3c6-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="3d3c6-120">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3c6-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="3d3c6-121">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3c6-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="3d3c6-122">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3c6-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="3d3c6-123">Per le procedure dettagliate per la configurazione dell'URL di accesso amministrativo, vedere [Edit or Configure Simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="3d3c6-124">Requisiti relativi a IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="3d3c6-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="3d3c6-125">Il pannello di controllo di Lync Server è uno dei componenti di Lync Server 2013 che richiede Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3d3c6-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="3d3c6-126">In particolare, assicurarsi che siano abilitate le funzionalità di reindirizzamento HTTP e di autenticazione di Windows e che sia in esecuzione il servizio Pubblicazione sul Web (W3SVC).</span><span class="sxs-lookup"><span data-stu-id="3d3c6-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="3d3c6-127">Dipendenze per il servizio Pubblicazione sul Web di Windows</span><span class="sxs-lookup"><span data-stu-id="3d3c6-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="3d3c6-128">Quando il servizio pubblicazione sul Web viene interrotto, non è possibile accedere al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="3d3c6-129">È possibile riavviare il servizio tramite la console MMC (Microsoft Management Console) Servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="3d3c6-130">**Per avviare il servizio Pubblicazione sul Web**</span><span class="sxs-lookup"><span data-stu-id="3d3c6-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="3d3c6-131">Accedere al computer in cui è installato il servizio pubblicazione sul Web come parte di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3d3c6-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="3d3c6-132">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="3d3c6-133">Fare clic con il pulsante destro del mouse su **Servizio Pubblicazione sul Web** e quindi fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="3d3c6-134">Modalità del pool di applicazioni</span><span class="sxs-lookup"><span data-stu-id="3d3c6-134">Application Pool Mode</span></span>

<span data-ttu-id="3d3c6-135">Configurare IIS in modo che il pool di applicazioni CsManagementAppPool utilizzi l'account Servizio di rete come identità del modello di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="3d3c6-136">Diritti utente e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3d3c6-136">User Rights and Permissions</span></span>

<span data-ttu-id="3d3c6-137">Per accedere al pannello di controllo di Lync Server, è necessario utilizzare un account di dominio membro del gruppo CsAdministrator oppure un account a cui sono stati delegati diritti utente e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="3d3c6-138">Non è possibile accedere al pannello di controllo di Lync Server utilizzando un account del computer locale.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="3d3c6-139">Per informazioni dettagliate sulla delega delle attività amministrative tramite il controllo di accesso basato sui ruoli (RBAC), vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="3d3c6-140">Se si utilizza un URL semplice per accedere al pannello di controllo di Lync Server, assicurarsi che i server Web siano stati aggiunti ai gruppi RTCUniversalServerAdmins e RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="3d3c6-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d3c6-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d3c6-141">See Also</span></span>


[<span data-ttu-id="3d3c6-142">Strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3c6-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

