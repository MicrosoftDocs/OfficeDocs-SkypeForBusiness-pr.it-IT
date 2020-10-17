---
title: 'Lync Server 2013: visualizzare le regole dei criteri di versione client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a269ff6a90f95d76ddc9c230a3ce8a769977dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506553"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="21fb2-102">Visualizzare le regole dei criteri di versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21fb2-102">View client version policy rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21fb2-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="21fb2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="21fb2-104">Un criterio di versione client è costituito da un insieme di regole dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="21fb2-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="21fb2-105">Queste regole definiscono le azioni da eseguire quando gli utenti tentano di accedere con client e versioni client specifici.</span><span class="sxs-lookup"><span data-stu-id="21fb2-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="21fb2-106">È possibile visualizzare le regole dei criteri di versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="21fb2-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="21fb2-107">Per visualizzare le regole dei criteri di versione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="21fb2-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="21fb2-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="21fb2-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21fb2-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21fb2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21fb2-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21fb2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21fb2-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **criteri versione client** .</span><span class="sxs-lookup"><span data-stu-id="21fb2-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="21fb2-112">Nella pagina **criteri versione client** fare doppio clic su un criterio di versione client che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="21fb2-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="21fb2-113">Le regole vengono visualizzate nella pagina **modifica criteri versione client** .</span><span class="sxs-lookup"><span data-stu-id="21fb2-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="21fb2-114">Per visualizzare i dettagli di una regola, selezionare la regola, quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="21fb2-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21fb2-115">Visualizzazione delle regole dei criteri di versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21fb2-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="21fb2-116">È possibile visualizzare le regole dei criteri di versione client utilizzando Lync Server Management Shell e il cmdlet **Get-CsClientVersionPolicyRule** .</span><span class="sxs-lookup"><span data-stu-id="21fb2-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="21fb2-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21fb2-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="21fb2-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="21fb2-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="21fb2-119">Per visualizzare le regole dei criteri di versione client</span><span class="sxs-lookup"><span data-stu-id="21fb2-119">To view client version policy rules</span></span>

  - <span data-ttu-id="21fb2-120">Per visualizzare le regole dei criteri di versione client, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="21fb2-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="21fb2-121">Che restituirà informazioni simili a queste per ogni regola configurata:</span><span class="sxs-lookup"><span data-stu-id="21fb2-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="21fb2-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="21fb2-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

