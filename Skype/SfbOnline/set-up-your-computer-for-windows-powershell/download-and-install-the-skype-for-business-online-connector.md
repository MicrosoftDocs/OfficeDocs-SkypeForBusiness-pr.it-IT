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
ms.openlocfilehash: fd0a114bcd434e624937b323fbfa787d252db96ffafb701c3f13ff3a677b7118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339284"
---
# <a name="download-and-install-the-teams-powershell-module"></a>Scaricare e installare il modulo Teams PowerShell

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> L'ultima Teams pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un unico modulo per la gestione Teams e Skype for Business di PowerShell online.


1. Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
