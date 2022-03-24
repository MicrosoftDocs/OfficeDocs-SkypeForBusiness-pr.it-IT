---
title: Teams PowerShell - Versioni supportate
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sulle versioni supportate dal modulo Teams PowerShell, usato per l'amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea8a755c75c5f91c5dbf3a4cd4dd749ac576557c
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "63762010"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell - Versioni supportate

Microsoft Teams modulo di PowerShell (TPM) versione 4.0.0 o successive saranno le uniche versioni supportate in futuro. Tutte le versioni precedenti sono nel percorso di ritiro.



## <a name="new-organizations"></a>Nuove organizzazioni

Le organizzazioni che hanno appena avviato l'onboarding su Teams potranno usare solo il modulo di PowerShell 4.0.0 o versioni successive di Teams a partire dal 1° aprile 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizzazioni correnti (non TPM attive)

Le organizzazioni che non hanno usato il TPM negli ultimi tre mesi (dal 22 gennaio al 22 marzo), potranno usare TPM 4.0.0 o versioni successive solo a partire dal 1° aprile 2022.



## <a name="current-organizations-tpm-active"></a>Organizzazioni correnti (TPM attivo)

Le organizzazioni che hanno utilizzato il TPM negli ultimi tre mesi (dal 22 gennaio al 22 marzo) potranno usare TPM 4.0.0 o versioni successive solo a partire dal 15 giugno 2022. È consigliabile aggiornare il modulo Teams PowerShell alla versione più recente.


## <a name="important-notes"></a>Note importanti

- Le note sulla versione per tutte Teams versioni del modulo di PowerShell sono disponibili in Teams [sulla versione di PowerShell](teams-powershell-release-notes.md).

- Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se è stato usato in origine Install-Module, è consigliabile usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se si aggiorna da Teams modulo di PowerShell versione 1.1.6, aggiornare gli script da usare `Connect-MicrosoftTeams` al posto di `New-CsOnlineSession`.

-   Durante l'aggiornamento, è consigliabile non usare TPM 4.x.x/3.x.x insieme alle versioni precedenti alla 3.0.0. Ad esempio, non è consigliabile usare le versioni 4.0.0 & 2.6.0 insieme per le diverse operazioni di amministrazione nella stessa organizzazione. 

- Modifiche correlate
  * Aggiornamenti a Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.0.0 e successive- altre informazioni in [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (post del Centro messaggi – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Modifiche in arrivo Telefono assegnazione di numeri- altre informazioni in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (post del Centro messaggi - MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Argomenti correlati

[Teams sulla versione di PowerShell](teams-powershell-release-notes.md)

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams di cmdlet](/powershell/module/teams) 

[Skype for Business cmdlet](/powershell/module/skype) 
