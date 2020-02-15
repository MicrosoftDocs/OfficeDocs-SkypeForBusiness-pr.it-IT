---
title: Configurare una voce di applicazione attendibile per il controllo delle chiamate remote
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43921fcdeb5ca6e5c74e2c7a82b36bf830cbaa15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="e504c-102">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e504c-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e504c-103">_**Ultimo argomento modificato:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="e504c-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="e504c-104">Il gateway SIP/CSTA deve essere configurato come applicazione attendibile affinché Lync Server applichi una route statica per instradare le chiamate al gateway.</span><span class="sxs-lookup"><span data-stu-id="e504c-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e504c-105">Se si esegue la migrazione di utenti da una versione precedente della distribuzione di Lync Server, assicurarsi di aver rimosso tutte le voci dell'applicazione attendibile esistenti (in precedenza note come voci host autorizzate) create per il gateway SIP/CSTA prima di seguire le procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e504c-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="e504c-106">Per informazioni dettagliate, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized host in Lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="e504c-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="e504c-107">Se si prevede di distribuire un nuovo controllo delle chiamate remote utilizzando una connessione TCP (Transmission Control Protocol), è necessario verificare che l' <STRONG>utilizzo del servizio Limit per gli indirizzi IP selezionati</STRONG> sia impostato su applicazioni e pool attendibili esistenti, se si desidera utilizzare la stessa porta TCP per la nuova applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="e504c-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="e504c-108">Per configurare una voce di applicazione attendibile per il gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="e504c-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="e504c-109">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o di un ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **New-CsTrustedApplicationPool** .</span><span class="sxs-lookup"><span data-stu-id="e504c-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="e504c-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e504c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e504c-111">Per creare una voce di applicazione attendibile, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e504c-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="e504c-112">Per una connessione TLS (Transport Layer Security), al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e504c-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="e504c-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e504c-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="e504c-114">Per una connessione TCP (Transmission Control Protocol), al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e504c-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="e504c-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e504c-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="e504c-116">Per aggiungere l'applicazione attendibile al pool, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e504c-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="e504c-117">Per una connessione TLS, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e504c-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="e504c-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e504c-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="e504c-119">Per una connessione TCP, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e504c-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="e504c-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e504c-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="e504c-121">Per implementare le modifiche pubblicate apportate alla topologia, al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e504c-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e504c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e504c-122">See Also</span></span>


[<span data-ttu-id="e504c-123">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e504c-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="e504c-124">Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e504c-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

