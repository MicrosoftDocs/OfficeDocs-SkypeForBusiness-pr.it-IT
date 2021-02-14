---
title: Skype for Business Server Management Shell
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione dei server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per Skype e i prodotti server Lync legacy.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816536"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="37532-104">Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="37532-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="37532-105">Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione dei server.</span><span class="sxs-lookup"><span data-stu-id="37532-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="37532-106">È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per Skype e i prodotti server Lync legacy.</span><span class="sxs-lookup"><span data-stu-id="37532-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="37532-107">Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="37532-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="37532-108">Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo.</span><span class="sxs-lookup"><span data-stu-id="37532-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="37532-109">Windows PowerShell è stata introdotta come versione scaricabile per il sistema operativo Windows alla fine del 2006 ed è stata incorporata come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="37532-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="37532-110">È stato incorporato nella maggior parte dei prodotti Server Microsoft, inclusi i server Lync e Skype a partire da Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37532-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="37532-111">Sono disponibili più di 700 cmdlet specifici di Lync e Skype in Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="37532-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37532-112">Informazioni di riferimento sul cmdlet di Skype for Business sono spostate in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="37532-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="37532-113">Facendo clic sui collegamenti seguenti verrà visualizzata la nuova docs.microsoft.com pagina.</span><span class="sxs-lookup"><span data-stu-id="37532-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="37532-114">Il contenuto è ora open source e disponibile per i contributi della community tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="37532-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="37532-115">Sei interessato a contribuire?</span><span class="sxs-lookup"><span data-stu-id="37532-115">Interested in contributing?</span></span> <span data-ttu-id="37532-116">Vedere il file README nel repo qui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="37532-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="37532-117">Skype for Business Server viene fornito con più di 700 cmdlet che consentono agli amministratori di gestire Skype for Business Server tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="37532-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="37532-118">È possibile recuperare la Guida per un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="37532-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="37532-119">Il comando precedente consente di recuperare le informazioni complete della Guida per il cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="37532-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="37532-120">Per visualizzare le informazioni della Guida per un altro cmdlet, sostituire **New-CsVoicePolicy** con il nome del cmdlet in questione.</span><span class="sxs-lookup"><span data-stu-id="37532-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="37532-121">Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Skype for Business Server, digitare quanto segue al prompt dei comandi della shell:</span><span class="sxs-lookup"><span data-stu-id="37532-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="37532-122">Informazioni su Windows PowerShell in Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="37532-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="37532-123">Per eseguire i cmdlet di Skype for Business Server, aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="37532-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="37532-124">Se si apre una finestra Windows PowerShell anziché Skype for Business Server Management Shell, per impostazione predefinita potrebbe non essere possibile eseguire i cmdlet skype.</span><span class="sxs-lookup"><span data-stu-id="37532-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="37532-125">Per eseguire i cmdlet di Skype for Business Server dall'Windows PowerShell, al prompt dei comandi Windows PowerShell digitare quanto segue: >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="37532-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="37532-126">Skype for Business Server Management Shell viene installato automaticamente in ogni server Skype for Business Server Enterprise Edition Front End Server o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="37532-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="37532-127">È possibile aggiornare il contenuto della Guida di Skype for Business Server Management Shell eseguendo il cmdlet [Update-Help.](https://technet.microsoft.com/library/hh849720.aspx)</span><span class="sxs-lookup"><span data-stu-id="37532-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="37532-128">Il cmdlet Update-Help scarica e installa i file della Guida più recenti disponibili per tutti i moduli installati nel computer, inclusi gli aggiornamenti per i cmdlet di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="37532-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="37532-129">Per impostazione predefinita, il cmdlet **Update-Help** aggiornerà tutti i moduli installati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="37532-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="37532-130">Se si desidera aggiornare solo determinati moduli, è possibile utilizzare il parametro _Module_ per limitare l'ambito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="37532-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="37532-131">Nell'esempio seguente viene aggiornato solo il modulo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="37532-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="37532-132">Se è necessario aggiornare la Guida nei server non connessi a Internet, è possibile utilizzare il cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) per ottenere la versione più recente della Guida e salvarla in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="37532-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="37532-133">È quindi possibile utilizzare il cmdlet **Update-Help** con il _parametro -SourcePath_ nei server non connessi a Internet per ottenere la Guida aggiornata dal percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="37532-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="37532-134">L'esempio seguente mostra come salvare i file della Guida in una condivisione file di rete e quindi aggiornare la Guida per il modulo Skype for Business dalla condivisione file.</span><span class="sxs-lookup"><span data-stu-id="37532-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="37532-135">Per informazioni più dettagliate, vedere [Informazioni sulla Guida aggiornabile.](https://technet.microsoft.com/library/hh847735.aspx)</span><span class="sxs-lookup"><span data-stu-id="37532-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37532-136">Se si usa PowerShell in remoto, potrebbe essere necessario consentire la comunicazione tramite un firewall.</span><span class="sxs-lookup"><span data-stu-id="37532-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="37532-137">Per ulteriori informazioni sulle porte usate dalla comunicazione remota di PowerShell, vedere Quale porta viene utilizzata [la comunicazione remota di PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="37532-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

