---
title: Creare criteri di accesso esterno personalizzato
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
- Setup
description: Skype for Business Online consente di creare altri criteri di accesso esterno. A differenza dei criteri client o di conferenza, in cui è possibile avere più combinazioni, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240145"
---
# <a name="create-custom-external-access-policies"></a>Creare criteri di accesso esterno personalizzato

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business Online consente di creare altri criteri di accesso esterno. A differenza dei criteri client o di conferenza, in cui è possibile avere più combinazioni, sono disponibili tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari. Di seguito sono seguenti:
  
- Nessun accesso federato o Skype consumer (_Tag:NoFederationAndPIC_ )
    
- Solo accesso federato (_Tag:FederationOnly_ )
    
- Accesso federato e consumer (_FederationAndPICDefault_)
    
I criteri esterni personalizzati consentono di creare altri criteri non coperti dalle impostazioni precedenti. Quando il criterio è stato creato, è necessario impostare tutti i parametri obbligatori e non è possibile modificarli in un secondo momento. La creazione di nuovi criteri personalizzati consente di controllare funzionalità come l'accesso degli utenti Skype utenti o un criterio per disabilitare l'audio/video nel cloud pubblico, che non è stato coperto da impostazioni predefinite. I criteri di accesso esterno personalizzati seguono la stessa sintassi dei criteri client, dispositivi mobili e conferenza. Per altre informazioni su queste impostazioni, [fare clic qui.](/previous-versions//mt228132(v=technet.10))
  
Per eseguire questa operazione, l'utente deve usare una versione supportata dell'app A Skype for Business 2016 che la supporta. È necessaria la versione minima di Skype for Business 2016 A scelta del client:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (Build 7571.2006)  <br/> |
|Canale corrente  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (Build 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che usano versioni precedenti di app Skype for Business Windows o client Mac saranno comunque in grado di trasferire i file. 
  
## <a name="start-windows-powershell"></a>Avviare Windows PowerShell

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente. Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector.
1. Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connessione a tutti i servizi Microsoft 365 o Office 365 in un'unica finestra [di Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurare il [computer](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)per Windows PowerShell .
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Creare criteri di accesso esterno personalizzati per un utente

Per farlo, eseguire quanto segue:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati
[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
