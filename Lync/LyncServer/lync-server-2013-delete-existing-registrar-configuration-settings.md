---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione esistenti per il registrar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c6b7238ab13c00289c5de1049163137d8cce71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f3356-102">Eliminare le impostazioni di configurazione di registrazione esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3356-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3356-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f3356-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f3356-104">Eseguire la procedura seguente per eliminare una funzione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f3356-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="f3356-105">Per eliminare le impostazioni di configurazione del servizio di registrazione</span><span class="sxs-lookup"><span data-stu-id="f3356-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="f3356-106">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f3356-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f3356-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3356-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3356-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3356-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3356-109">Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="f3356-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="f3356-110">Nella pagina **Funzione di registrazione** digitare il nome della funzione di registrazione che si desidera eliminare nel campo di ricerca, per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="f3356-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="f3356-111">Nell'elenco fare clic sulla funzione di registrazione desiderata, fare clic su **Modifica**, quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f3356-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="f3356-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3356-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f3356-113">Rimozione delle impostazioni di configurazione del servizio di registrazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3356-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f3356-114">È possibile eliminare le impostazioni di configurazione del servizio di registrazione utilizzando Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f3356-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="f3356-115">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3356-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f3356-116">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="f3356-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="f3356-117">Per rimuovere un set specifico di impostazioni di sicurezza della funzione di registrazione</span><span class="sxs-lookup"><span data-stu-id="f3356-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="f3356-118">Il comando seguente rimuove le impostazioni di sicurezza della funzione di registrazione applicate al server perimetrale atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="f3356-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="f3356-119">Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="f3356-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="f3356-120">Il comando seguente rimuove tutte le impostazioni di sicurezza della funzione di registrazione applicate al servizio di registrazione:</span><span class="sxs-lookup"><span data-stu-id="f3356-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="f3356-121">Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'autenticazione NTLM</span><span class="sxs-lookup"><span data-stu-id="f3356-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="f3356-122">Il comando seguente elimina tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'utilizzo di NTLM per l'autenticazione client:</span><span class="sxs-lookup"><span data-stu-id="f3356-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="f3356-123">Per informazioni dettagliate, vedere [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f3356-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

