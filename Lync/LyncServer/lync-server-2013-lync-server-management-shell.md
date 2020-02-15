---
title: 'Lync Server 2013: Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d8ba2330e59d4f352407d94c6e73f96a5fff816
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="d95c4-102">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="d95c4-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d95c4-103">_**Ultimo argomento modificato:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="d95c4-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d95c4-104">La Guida di riferimento ai cmdlet di Skype for business è stata spostata in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d95c4-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="d95c4-105">Facendo clic sui collegamenti riportati di seguito, è possibile utilizzare la nuova pagina di docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d95c4-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="d95c4-106">Il contenuto è ora Open Source e disponibile per i contributi comunitari tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="d95c4-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="d95c4-107">Interessati a contribuire?</span><span class="sxs-lookup"><span data-stu-id="d95c4-107">Interested in contributing?</span></span> <span data-ttu-id="d95c4-108">Consultare il file README nel repo qui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="d95c4-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="d95c4-109">Microsoft Lync Server 2010 è stata introdotta una serie di funzionalità nuove e migliorate rispetto a quelle disponibili in Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d95c4-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="d95c4-110">Uno di questi miglioramenti riguarda la modalità di gestione dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="d95c4-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="d95c4-111">Ad esempio, è presente una nuova interfaccia utente, denominata Pannello di controllo di Lync Server, che rappresenta un grande cambiamento rispetto a quello utilizzato per la maggior parte delle persone con Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="d95c4-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="d95c4-112">L'altro importante miglioramento della gestibilità è l'inclusione di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d95c4-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="d95c4-113">Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d95c4-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="d95c4-114">Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo.</span><span class="sxs-lookup"><span data-stu-id="d95c4-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="d95c4-115">Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows alla fine del 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="d95c4-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="d95c4-116">Da quel momento ha continuato a crescere ed è stato incorporato nella maggior parte dei prodotti Microsoft Server, il più recente dei quali è Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d95c4-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d95c4-117">In Lync Server 2010 sono stati introdotti quasi 550 cmdlet specifici per il prodotto che è possibile utilizzare per gestire tutti gli aspetti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d95c4-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="d95c4-118">Nelle sezioni seguenti è disponibile un elenco dei cmdlet e relative descrizioni.</span><span class="sxs-lookup"><span data-stu-id="d95c4-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="d95c4-119">Queste informazioni sono disponibili anche direttamente dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d95c4-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="d95c4-120">Basta digitare quanto segue al prompt dei comandi di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d95c4-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="d95c4-121">Per recuperare le informazioni della Guida dal prompt dei comandi nel cmdlet **New-CsVoicePolicy**, ad esempio, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d95c4-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="d95c4-122">Aspetti da sapere su Windows PowerShell in Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d95c4-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="d95c4-123">Per eseguire i cmdlet di Lync Server, aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d95c4-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d95c4-124">Se si apre una finestra di Windows PowerShell anziché Lync Server Management Shell, per impostazione predefinita non sarà possibile eseguire i cmdlet di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d95c4-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="d95c4-125">Per eseguire i cmdlet di Lync Server da Windows PowerShell, digitare il comando seguente al prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d95c4-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="d95c4-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="d95c4-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="d95c4-127">Lync Server Management Shell viene installato automaticamente in ogni server Lync Server Enterprise Edition Front End Server o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d95c4-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="d95c4-128">Le informazioni nuove e aggiornate, gli script di esempio e la guida per iniziare e saperne di più sui cmdlet di Windows PowerShell e Microsoft Lync Server 2013 sono disponibili nel Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)di Windows PowerShell per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d95c4-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

