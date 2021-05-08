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
description: Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238867"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="3c8f4-103">Scaricare e installare il modulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c8f4-103">Download and install the Teams PowerShell module</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> <span data-ttu-id="3c8f4-104">L'ultima Teams pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un unico modulo per la gestione Teams e Skype for Business di PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="3c8f4-105">Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3c8f4-106">Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="3c8f4-107">Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3c8f4-108">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3c8f4-108">Related topics</span></span>
[<span data-ttu-id="3c8f4-109">Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c8f4-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
