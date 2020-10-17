---
title: Eliminare una raccolta esistente di impostazioni di configurazione delle riunioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf416af31b219c07691790b88d672d26768104d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514663"
---
# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="80c4e-102">Eliminare una raccolta esistente di impostazioni di configurazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80c4e-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80c4e-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="80c4e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="80c4e-p101">È possibile eliminare una configurazione utente o sito. La configurazione globale non può essere rimossa. Se si elimina la configurazione globale, essa viene automaticamente reimpostata sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="80c4e-p101">You can delete a site or user configuration. The global configuration cannot be removed. If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="80c4e-107">Per eliminare una configurazione utente o sito per le riunioni</span><span class="sxs-lookup"><span data-stu-id="80c4e-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="80c4e-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="80c4e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="80c4e-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80c4e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="80c4e-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="80c4e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="80c4e-111">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="80c4e-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="80c4e-112">Nell'elenco delle configurazioni delle riunioni, fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="80c4e-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="80c4e-113">Rimozione delle impostazioni di configurazione delle riunioni tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80c4e-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="80c4e-114">Le impostazioni delle riunioni possono essere eliminate utilizzando Windows PowerShell e il cmdlet Remove-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="80c4e-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="80c4e-115">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80c4e-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="80c4e-116">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="80c4e-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="80c4e-117">Per rimuovere una raccolta specificata di impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="80c4e-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="80c4e-118">Questo comando rimuove le impostazioni di configurazione delle riunioni applicati al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="80c4e-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="80c4e-119">Per rimuovere tutte le impostazioni di configurazione delle riunioni applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="80c4e-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="80c4e-120">Questo comando rimuove tutte le impostazioni di configurazione delle riunioni applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="80c4e-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="80c4e-121">Per rimuovere tutte le impostazioni di configurazione delle riunioni che ammettono gli utenti anonimi per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="80c4e-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="80c4e-122">Questo rimuove tutte le impostazioni che consentono agli utenti anonimi di essere ammessi per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="80c4e-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="80c4e-123">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="80c4e-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

