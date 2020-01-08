---
title: 'Lync Server 2013: visualizzare le informazioni sulla configurazione di CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa03ab1ce52c98746657c0314760c902f295589
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a><span data-ttu-id="bd989-102">Visualizzare le informazioni di configurazione CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd989-102">View CDR configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd989-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bd989-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bd989-104">La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.</span><span class="sxs-lookup"><span data-stu-id="bd989-104">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="bd989-105">Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.</span><span class="sxs-lookup"><span data-stu-id="bd989-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="bd989-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="bd989-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="bd989-107">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="bd989-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="bd989-108">Per visualizzare le impostazioni di configurazione CDR in uso nell'organizzazione, è possibile usare il pannello di controllo di Lync Server o il cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="bd989-108">You can view the CDR configuration settings in use in your organization by using Lync Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="bd989-109">Per visualizzare le informazioni di configurazione CDR tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bd989-109">To view CDR configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bd989-110">Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="bd989-110">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="bd989-111">Nella scheda **registrazione dettagli chiamata** verrà visualizzato un elenco di tutte le impostazioni di configurazione CDR. per ogni raccolta di impostazioni verrà visualizzato il **nome**della raccolta; indipendentemente dal fatto che CDR sia stato abilitato (la proprietà **CDR** ); e indipendentemente dal fatto che l'eliminazione sia stata abilitata (la proprietà **cancellazione CDR** ).</span><span class="sxs-lookup"><span data-stu-id="bd989-111">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property).</span></span> <span data-ttu-id="bd989-112">Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta oppure selezionare la raccolta appropriata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="bd989-112">To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="bd989-113">Tieni presente che puoi visualizzare solo informazioni dettagliate per una singola raccolta di impostazioni di configurazione CDR alla volta.</span><span class="sxs-lookup"><span data-stu-id="bd989-113">Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bd989-114">Visualizzazione delle informazioni di configurazione CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd989-114">Viewing CDR Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bd989-115">Per visualizzare le impostazioni di configurazione CDR, è possibile usare Windows PowerShell e il cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="bd989-115">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="bd989-116">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd989-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bd989-117">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="bd989-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="bd989-118">Per visualizzare le informazioni sulla configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="bd989-118">To view CDR configuration information</span></span>

  - <span data-ttu-id="bd989-119">Per visualizzare informazioni su tutte le impostazioni di configurazione CDR, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="bd989-119">To view information about all your CDR configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsCdrConfiguration
    
    <span data-ttu-id="bd989-120">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="bd989-120">That will return information similar to this:</span></span>
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

<span data-ttu-id="bd989-121">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="bd989-121">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

