---
title: Eliminare una raccolta esistente di impostazioni di configurazione della versione client
description: Eliminare una raccolta esistente di impostazioni di configurazione della versione client.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a7d384bdfd84a1a6e04041988c16788a116626
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572882"
---
# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6a476-103">Eliminare una raccolta esistente di impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a476-103">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a476-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6a476-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6a476-105">Se si desidera rimuovere le impostazioni di configurazione del client precedentemente configurate per un sito, è possibile rimuovere le impostazioni dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a476-105">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="6a476-106">Per rimuovere le impostazioni di configurazione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6a476-106">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6a476-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6a476-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a476-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a476-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a476-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a476-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a476-110">Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .</span><span class="sxs-lookup"><span data-stu-id="6a476-110">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6a476-111">Selezionare il sito, fare clic su **modifica**, scegliere **Elimina**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a476-111">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a476-112">Rimozione delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a476-112">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a476-113">Per eliminare le impostazioni di configurazione della versione client, è possibile utilizzare il cmdlet **Remove-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6a476-113">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="6a476-114">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a476-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a476-115">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="6a476-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="6a476-116">Per rimuovere una raccolta specificata di impostazioni di configurazione della versione client</span><span class="sxs-lookup"><span data-stu-id="6a476-116">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="6a476-117">Con il comando seguente vengono rimosse le impostazioni di configurazione della versione client applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="6a476-117">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="6a476-118">Per rimuovere tutte le impostazioni di configurazione della versione client applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="6a476-118">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="6a476-119">Questo comando rimuove tutte le impostazioni di configurazione della versione client configurate nell'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="6a476-119">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="6a476-120">Per rimuovere tutte le impostazioni di configurazione della versione client in base al valore della proprietà DefaultAction</span><span class="sxs-lookup"><span data-stu-id="6a476-120">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="6a476-121">Questo comando rimuove tutte le impostazioni di configurazione della versione client in cui l'azione predefinita è stata impostata su "blocca":</span><span class="sxs-lookup"><span data-stu-id="6a476-121">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="6a476-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="6a476-122">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

