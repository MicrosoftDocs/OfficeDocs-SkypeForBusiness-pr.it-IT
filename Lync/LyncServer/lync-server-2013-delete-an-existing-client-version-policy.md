---
title: 'Lync Server 2013: eliminare un criterio di versione client esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0adc3ab47b3b441eff900c6a9202a782e524c22c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="cf6f1-102">Eliminare un criterio di versione client esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf6f1-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6f1-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cf6f1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cf6f1-104">Se si vuole eliminare un criterio di versione client configurato in precedenza, è possibile eliminarlo dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="cf6f1-105">Per eliminare i criteri di versione client tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cf6f1-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cf6f1-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cf6f1-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf6f1-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf6f1-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf6f1-109">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri di versione client** .</span><span class="sxs-lookup"><span data-stu-id="cf6f1-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="cf6f1-110">Nella pagina **criteri di versione client** selezionare i criteri di versione client o i criteri che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cf6f1-111">Eliminazione dei criteri di versione client con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf6f1-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cf6f1-112">È possibile eliminare i criteri di versione client usando il cmdlet **Remove-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="cf6f1-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="cf6f1-113">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cf6f1-114">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="cf6f1-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="cf6f1-115">Per rimuovere un criterio di versione client specifico</span><span class="sxs-lookup"><span data-stu-id="cf6f1-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="cf6f1-116">Questo comando Elimina il criterio di versione client applicato al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="cf6f1-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="cf6f1-117">Per rimuovere tutti i criteri di versione client applicati all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="cf6f1-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="cf6f1-118">Questo comando rimuove tutti i criteri di versione client configurati nell'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="cf6f1-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="cf6f1-119">Per rimuovere i criteri di versione client che non includono un agente utente specifico</span><span class="sxs-lookup"><span data-stu-id="cf6f1-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="cf6f1-120">Questo comando rimuove tutti i criteri di versione client che non includono una regola per l'agente utente di Lync (WPLync) di Windows Phone:</span><span class="sxs-lookup"><span data-stu-id="cf6f1-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="cf6f1-121">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="cf6f1-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

