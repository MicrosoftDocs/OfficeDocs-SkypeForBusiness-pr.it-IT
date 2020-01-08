---
title: 'Lync Server 2013: Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fdc8e5f13687d2bed0e0c35609187c57d11592
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="e7757-102">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="e7757-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7757-103">_**Argomento Ultima modifica:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="e7757-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7757-104">Il riferimento ai cmdlet di Skype for business è stato spostato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e7757-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="e7757-105">Facendo clic sui collegamenti seguenti si accede alla nuova pagina di docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e7757-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="e7757-106">Il contenuto è ora aperto e disponibile per i contributi della community tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="e7757-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="e7757-107">Vuoi contribuire?</span><span class="sxs-lookup"><span data-stu-id="e7757-107">Interested in contributing?</span></span> <span data-ttu-id="e7757-108">Vedere il file README nel repository qui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="e7757-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="e7757-109">Microsoft Lync Server 2010 ha introdotto una vasta gamma di funzionalità nuove e migliorate rispetto a quelle disponibili in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e7757-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="e7757-110">Un miglioramento è il modo in cui Gestisci l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="e7757-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="e7757-111">Ad esempio, c'è una nuova interfaccia utente, chiamata il pannello di controllo di Lync Server, che rappresenta un grande cambiamento rispetto a quello usato dalla maggior parte delle persone con Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="e7757-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="e7757-112">L'altro importante miglioramento della gestibilità è l'inclusione di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7757-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="e7757-113">Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e7757-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="e7757-114">Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo.</span><span class="sxs-lookup"><span data-stu-id="e7757-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="e7757-115">Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows in ritardo in 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e7757-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="e7757-116">Da questo punto ha continuato a crescere ed è stato incorporato nella maggior parte dei prodotti Microsoft Server, il più recente dei quali è Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7757-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e7757-117">Lync Server 2010 ha introdotto vicino a 550 cmdlet specifici del prodotto che è possibile usare per gestire ogni aspetto della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7757-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="e7757-118">Nelle sezioni seguenti è disponibile un elenco dei cmdlet e relative descrizioni.</span><span class="sxs-lookup"><span data-stu-id="e7757-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="e7757-119">Queste informazioni sono disponibili anche direttamente dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e7757-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="e7757-120">Digitare semplicemente quanto segue al prompt dei comandi di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e7757-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="e7757-121">Per recuperare le informazioni della Guida dal prompt dei comandi nel cmdlet **New-CsVoicePolicy**, ad esempio, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7757-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="e7757-122">Informazioni da sapere su Windows PowerShell in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e7757-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="e7757-123">Per eseguire i cmdlet di Lync Server, aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e7757-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e7757-124">Se si apre una finestra di Windows PowerShell anziché Lync Server Management Shell, per impostazione predefinita non sarà possibile eseguire i cmdlet di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7757-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="e7757-125">Per eseguire i cmdlet di Lync Server da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7757-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="e7757-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="e7757-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="e7757-127">Lync Server Management Shell viene installato automaticamente in tutti i server front-end di Lync Server Enterprise Edition o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e7757-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="e7757-128">Le informazioni nuove e aggiornate, gli script di esempio e la guida per l'introduzione e per saperne di più sui cmdlet di Windows PowerShell e Microsoft Lync Server 2013 sono disponibili nel Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)di Lync Server di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7757-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

