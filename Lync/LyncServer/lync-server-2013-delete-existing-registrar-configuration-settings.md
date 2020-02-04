---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione del registrar esistenti'
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
ms.openlocfilehash: 960d0dd055ccf2f380b1ebf8124432da8daf6563
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7744e-102">Eliminare le impostazioni di configurazione del registrar esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7744e-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7744e-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7744e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7744e-104">Seguire questa procedura per eliminare un registrar.</span><span class="sxs-lookup"><span data-stu-id="7744e-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="7744e-105">Per eliminare le impostazioni di configurazione del registrar</span><span class="sxs-lookup"><span data-stu-id="7744e-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="7744e-106">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7744e-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7744e-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7744e-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7744e-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7744e-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7744e-109">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="7744e-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="7744e-110">Nella pagina **registrar** e nel campo di ricerca digitare tutto o parte del nome del registrar che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="7744e-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="7744e-111">Nell'elenco fare clic sul registrar desiderato, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="7744e-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="7744e-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7744e-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7744e-113">Rimozione delle impostazioni di configurazione del registrar tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7744e-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7744e-114">Per eliminare le impostazioni di configurazione del registrar, è possibile usare Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7744e-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="7744e-115">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7744e-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7744e-116">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="7744e-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="7744e-117">Per rimuovere un set specifico di impostazioni di sicurezza del registrar</span><span class="sxs-lookup"><span data-stu-id="7744e-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="7744e-118">Il comando seguente rimuove le impostazioni di sicurezza del registrar applicate alla atl-edge-011.litwareinc.com di Edge Server:</span><span class="sxs-lookup"><span data-stu-id="7744e-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="7744e-119">Per rimuovere tutte le impostazioni di sicurezza del registrar applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="7744e-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="7744e-120">Il comando seguente rimuove tutte le impostazioni di sicurezza del registrar applicate al servizio Registrar:</span><span class="sxs-lookup"><span data-stu-id="7744e-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="7744e-121">Per rimuovere tutte le impostazioni di sicurezza del registrar che consentono l'autenticazione NTLM</span><span class="sxs-lookup"><span data-stu-id="7744e-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="7744e-122">Il comando seguente elimina tutte le impostazioni di sicurezza del registrar che consentono l'uso di NTLM per l'autenticazione client:</span><span class="sxs-lookup"><span data-stu-id="7744e-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="7744e-123">Per informazioni dettagliate, vedere [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7744e-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

