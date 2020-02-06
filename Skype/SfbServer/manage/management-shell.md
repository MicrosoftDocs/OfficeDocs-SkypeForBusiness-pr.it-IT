---
title: Skype for Business Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server Management Shell offre l'interfaccia della riga di comando per l'amministrazione e la gestione dei server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per i prodotti Skype e legacy Lync Server.
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817555"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="74aee-104">Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="74aee-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="74aee-105">Skype for Business Server Management Shell offre l'interfaccia della riga di comando per l'amministrazione e la gestione dei server.</span><span class="sxs-lookup"><span data-stu-id="74aee-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="74aee-106">È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per i prodotti Skype e legacy Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74aee-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="74aee-107">Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="74aee-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="74aee-108">Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo.</span><span class="sxs-lookup"><span data-stu-id="74aee-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="74aee-109">Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows in ritardo in 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="74aee-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="74aee-110">È stata incorporata nella maggior parte dei prodotti Microsoft Server, inclusi i server Lync e Skype che iniziano con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="74aee-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="74aee-111">In Skype for Business Server Management Shell sono disponibili più di 700 cmdlet specifici di Lync e Skype.</span><span class="sxs-lookup"><span data-stu-id="74aee-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aee-112">Il riferimento ai cmdlet di Skype for business è stato spostato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74aee-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="74aee-113">Facendo clic sui collegamenti seguenti si accede alla nuova pagina di docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="74aee-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="74aee-114">Il contenuto è ora aperto e disponibile per i contributi della community tramite GitHub.</span><span class="sxs-lookup"><span data-stu-id="74aee-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="74aee-115">Vuoi contribuire?</span><span class="sxs-lookup"><span data-stu-id="74aee-115">Interested in contributing?</span></span> <span data-ttu-id="74aee-116">Vedere il file README nel repository qui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="74aee-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="74aee-117">Skype for Business Server viene fornito con più di 700 cmdlet che consentono agli amministratori di gestire Skype for Business Server con Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="74aee-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="74aee-118">È possibile recuperare la guida per un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="74aee-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="74aee-119">Il comando precedente recupera la guida completa disponibile per il cmdlet **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="74aee-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="74aee-120">Per visualizzare la guida per un cmdlet diverso, sostituire **New-CsVoicePolicy** con il nome del cmdlet per cui si vuole recuperare la guida.</span><span class="sxs-lookup"><span data-stu-id="74aee-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="74aee-121">Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Skype for Business Server, digitare quanto segue al prompt dei comandi della shell:</span><span class="sxs-lookup"><span data-stu-id="74aee-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="74aee-122">Informazioni da sapere su Windows PowerShell in Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="74aee-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="74aee-123">Per eseguire i cmdlet di Skype for Business Server, aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="74aee-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="74aee-124">Se si apre una finestra di Windows PowerShell invece di Skype for Business Server Management Shell, per impostazione predefinita potrebbe non essere possibile eseguire i cmdlet Skype.</span><span class="sxs-lookup"><span data-stu-id="74aee-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="74aee-125">Per eseguire i cmdlet di Skype for Business Server da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="74aee-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="74aee-126">Skype for Business Server Management Shell viene installato automaticamente in ogni server Skype for Business Server Enterprise Edition front-end o Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="74aee-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="74aee-127">Puoi aggiornare il contenuto della Guida di Skype for Business Server Management Shell eseguendo il cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="74aee-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="74aee-128">Il cmdlet Update-Help Scarica e installa i file della guida più recenti disponibili per tutti i moduli installati nel computer, inclusi gli aggiornamenti ai cmdlet di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="74aee-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="74aee-129">Per impostazione predefinita, il cmdlet **Update-Help** aggiornerà tutti i moduli installati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74aee-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="74aee-130">Per aggiornare soltanto alcuni moduli, è possibile usare il parametro _Module_ per limitare l'ambito del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="74aee-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="74aee-131">L'esempio seguente aggiorna solo il modulo Skype for business.</span><span class="sxs-lookup"><span data-stu-id="74aee-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="74aee-132">Se è necessario aggiornare la guida per i server che non sono connessi a Internet, è possibile usare il cmdlet [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) per ottenere la versione più recente della guida e salvarla in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="74aee-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="74aee-133">È quindi possibile usare il cmdlet **Update-Help** con il parametro _-SourcePath_ nei server non connessi a Internet per ottenere la guida aggiornata dalla posizione selezionata.</span><span class="sxs-lookup"><span data-stu-id="74aee-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="74aee-134">L'esempio seguente mostra come salvare i file della Guida in una condivisione file di rete e quindi aggiornare la guida per il modulo Skype for business dalla condivisione file.</span><span class="sxs-lookup"><span data-stu-id="74aee-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="74aee-135">Per informazioni più dettagliate, vedere informazioni [sulla guida aggiornabile](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="74aee-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74aee-136">Se si usa PowerShell in remoto, potrebbe essere necessario consentire la comunicazione tramite un firewall.</span><span class="sxs-lookup"><span data-stu-id="74aee-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="74aee-137">Per altre informazioni sui servizi remoti di PowerShell per le porte, vedere [quale porta viene usata da PowerShell remoting?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="74aee-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

