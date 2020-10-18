---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione del servizio Web esistenti'
description: 'Lync Server 2013: eliminare le impostazioni di configurazione del servizio Web esistenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a28197f26a447112e29b6e4a831585dd49a9854
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575852"
---
# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="90338-103">Eliminare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90338-103">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90338-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="90338-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="90338-105">Eseguire la procedura seguente per eliminare le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="90338-105">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="90338-106">Per eliminare le impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="90338-106">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="90338-107">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90338-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="90338-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90338-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90338-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90338-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90338-110">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="90338-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="90338-111">Nella pagina **Servizio Web** digitare il nome dei criteri che si desidera eliminare nel campo di ricerca, per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="90338-111">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="90338-112">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="90338-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="90338-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90338-113">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90338-114">Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90338-114">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90338-115">È possibile eliminare le impostazioni di configurazione del servizio Web utilizzando Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="90338-115">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="90338-116">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90338-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="90338-117">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="90338-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="90338-118">Per eliminare una raccolta specifica di impostazioni di configurazione di servizi Web</span><span class="sxs-lookup"><span data-stu-id="90338-118">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="90338-119">Con il comando seguente vengono rimosse le impostazioni di sicurezza di servizi Web applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="90338-119">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="90338-120">Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="90338-120">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="90338-121">Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web applicate nell'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="90338-121">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="90338-122">Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="90338-122">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="90338-123">Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web che consentono l'utilizzo dell'autenticazione basata sui certificati:</span><span class="sxs-lookup"><span data-stu-id="90338-123">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="90338-124">Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="90338-124">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90338-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90338-125">See Also</span></span>


[<span data-ttu-id="90338-126">Configurazione dell'autenticazione nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90338-126">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

