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
description: Skype for Business online consente di creare criteri di accesso esterno aggiuntivi. A differenza dei criteri client o conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814195"
---
# <a name="create-custom-external-access-policies"></a>Creare criteri di accesso esterno personalizzato

Skype for Business online consente di creare criteri di accesso esterno aggiuntivi. A differenza dei criteri client o conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti che possono coprire la maggior parte degli scenari. Ecco come:
  
- Nessun accesso federato o consumer Skype (_Tag:NoFederationAndPIC_ )
    
- Solo accesso federato (_Tag:FederationOnly_ )
    
- Accesso federato e consumer (_FederationAndPICDefault_)
    
I criteri esterni personalizzati consentono di creare altri criteri non coperti dalle impostazioni precedenti. Quando sono stati creati i criteri, era necessario impostare tutti i parametri obbligatori e non era possibile modificarli in un secondo momento. La creazione di nuovi criteri personalizzati ti consente di controllare funzionalità come l'accesso consumer di Skype o un criterio per disabilitare l'audio/video nel cloud pubblico, che non era coperto da impostazioni predefinite. I criteri di accesso esterno personalizzati seguono la stessa sintassi dei criteri client, mobilità e conferenza. Altre informazioni su queste impostazioni sono [disponibili qui.](https://technet.microsoft.com/library/mt228132.aspx)
  
A tale scopo, l'utente deve utilizzare una versione supportata dell'app Skype for Business 2016 A scelta che la supporta. È richiesta la seguente versione minima del client A scelta di Skype for Business 2016:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (build 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (build 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che utilizzano versioni precedenti delle app Windows o dei client Mac di Skype for Business potranno comunque trasferire i file. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://www.microsoft.com/download/details.aspx?id=40855) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
    
4. Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.
    
    Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'unica Windows PowerShell singola.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **Avviare una sessione di Windows PowerShell**
    
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:
    
  > [!NOTE]
  > Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
  >
  > Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure Configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Creare criteri di accesso esterno personalizzati per un utente

Per farlo, eseguire quanto segue:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
