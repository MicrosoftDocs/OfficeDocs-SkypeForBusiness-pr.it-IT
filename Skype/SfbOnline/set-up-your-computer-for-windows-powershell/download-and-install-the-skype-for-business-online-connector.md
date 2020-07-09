---
title: Download e installazione del modulo Skype for Business Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085702"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="6dc76-103">Download e installazione del modulo Skype for Business Online Connector</span><span class="sxs-lookup"><span data-stu-id="6dc76-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="6dc76-104">La [versione di anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) più recente è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell per Teams.</span><span class="sxs-lookup"><span data-stu-id="6dc76-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="6dc76-105">[] Modulo del connettore di Skype for Business Online include il cmdlet **New-CsOnlineSession**, che consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="6dc76-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6dc76-106">Questo modulo, supportato solo in computer a 64 bit (vedere [configurare il computer per la gestione di Skype for business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) per altre informazioni), può essere scaricato dall'area download Microsoft [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="6dc76-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="6dc76-107">Scarica il file SkypeOnlinePowershell.exe, poi procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="6dc76-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="6dc76-108">Fai doppio clic sul file **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="6dc76-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="6dc76-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span><span class="sxs-lookup"><span data-stu-id="6dc76-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="6dc76-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span><span class="sxs-lookup"><span data-stu-id="6dc76-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="6dc76-111">Nella pagina **Skype for Business Online, modulo Windows PowerShell completato**, fai clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="6dc76-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="6dc76-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span><span class="sxs-lookup"><span data-stu-id="6dc76-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="6dc76-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span><span class="sxs-lookup"><span data-stu-id="6dc76-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="6dc76-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span><span class="sxs-lookup"><span data-stu-id="6dc76-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="6dc76-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="6dc76-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="6dc76-116">Quando viene visualizzato Blocco note, aggiungi la riga seguente dopo i comandi già presenti nel profilo (se ce ne sono):</span><span class="sxs-lookup"><span data-stu-id="6dc76-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="6dc76-117">Save the file.</span><span class="sxs-lookup"><span data-stu-id="6dc76-117">Save the file.</span></span> <span data-ttu-id="6dc76-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span><span class="sxs-lookup"><span data-stu-id="6dc76-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="6dc76-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span><span class="sxs-lookup"><span data-stu-id="6dc76-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="6dc76-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="6dc76-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="6dc76-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6dc76-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="6dc76-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span><span class="sxs-lookup"><span data-stu-id="6dc76-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="6dc76-123">Per verificare il numero di versione del modulo Connector attualmente installato sul computer, apri Pannello di controllo, apri **Programmi e funzionalità** e verifica il numero di versione di **Skype for Business Online, modulo Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6dc76-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6dc76-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6dc76-124">Related topics</span></span>
[<span data-ttu-id="6dc76-125">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6dc76-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
