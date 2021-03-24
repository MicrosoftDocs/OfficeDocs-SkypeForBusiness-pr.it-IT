---
title: Provisioning degli account di Sistema sala Skype in Microsoft 365 e Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leggere questo argomento per informazioni sul provisioning degli account di Sistema sala Skype in Microsoft 365 o Office 365.
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093520"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Provisioning degli account di Sistema sala Skype in Microsoft 365 e Office 365
 
Leggere questo argomento per informazioni sul provisioning degli account di Sistema sala Skype in Microsoft 365 o Office 365.
  
La sezione seguente illustra il provisioning dell'account skype room system.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Prerequisiti di Microsoft 365 e Office 365

Il tenant online deve soddisfare i requisiti seguenti:
  
- Il piano di Microsoft 365 o Office 365 deve includere Skype for Business Online Piano 2 o Office 365 E1, E3 o E5. <br/>Per informazioni dettagliate sui piani di Skype for Business Online, vedere Descrizione [del servizio Skype for Business online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- Il tenant deve avere la funzionalità di conferenza di Skype for Business abilitata.
    
- Nel tenant deve essere abilitato Exchange Online. 
    
- L'amministratore remoto tenant deve disporre dell'accesso PowerShell seguente:
    
  - Accesso remoto a PowerShell di Exchange
    
  - Accesso remoto a PowerShell di Skype for Business online
    
  - Windows Azure Active Directory Module per Windows PowerShell accesso alla directory di Microsoft 365 o Office 365
    
Per l'account sala Skype, sono necessarie le licenze seguenti:
  
- Per abilitare le riunioni Skype for Business online, è necessaria una licenza Skype for Business Online Piano 2 o Office 365 E1 o E3.
    
- Per autorizzare la sala con la funzionalità VoIP aziendale in modo che la sala possa essere abilitata con un numero di telefono, è necessario un Skype for Business Online Piano 2 con licenza sistema telefonico o Office 365 E5 (1).
    
- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per audioconferenza e sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessario un piano per chiamate nazionali o nazionali e internazionali. 
    
- Non è necessaria una licenza di Exchange Online per l'account sala Skype perché l'account deve essere configurato come account della cassetta postale delle risorse.
    
## <a name="provisioning-overview"></a>Panoramica del provisioning

Nel diagramma seguente viene fornita una panoramica del flusso di provisioning dell'account di sistema sala Skype.
  
![Passaggi per il provisioning del sistema skype room](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificare una nuova sala riunioni

È possibile che in Exchange sia già disponibile una cassetta postale sala risorse che fornisce la funzionalità di pianificazione oppure che si crei per la prima volta una cassetta postale per le risorse per facilitare la distribuzione di Skype Room System. In ogni caso, è necessario identificare un account sala da utilizzare nel tenant. Le sezioni Provisioning di Exchange Online e Provisioning di Skype for Business forniscono indicazioni per entrambi i tipi di account. Ad esempio, supponiamo che tu abbia le due sale seguenti e che desideri distribuire Skype Room System per entrambe:
  
- Account cassetta postale risorsa esistente: confrm1@contoso.onmicrosoft.com
    
- Nuovo account cassetta postale risorsa: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisioning di Exchange Online

Prima di tutto, connettersi a PowerShell di Exchange Online seguendo le istruzioni nell'argomento Connect [to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Per impostare un account cassetta postale sala risorse esistente per Skype Room System, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Per creare un nuovo account cassetta postale delle risorse di Exchange per Skype Room System, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

I comandi precedenti configurano o creano un nuovo account della cassetta postale per le risorse di Exchange per l'utilizzo di Skype Room System abilitando l'account.
  
Dopo aver creato la cassetta postale, è possibile utilizzare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 in Distribuzioni locali a foresta singola

## <a name="assigning-a-skype-for-business-online-license"></a>Assegnazione di una licenza di Skype for Business online

Ora è possibile assegnare una licenza skype for business online (piano 2) o Skype for Business online (Piano 3) utilizzando il portale amministrativo di Microsoft 365 come descritto in Assegnare o rimuovere licenze per [Microsoft 365 per](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) le aziende o in Licenze per componenti aggiuntivi [Skype for Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
Dopo aver assegnato una licenza per Skype for Business online, potrai accedere e verificare che l'account sia attivo usando qualsiasi client Skype for Business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisioning di Skype for Business online

Dopo aver creato e abilitato un account della cassetta postale sala risorse come mostrato in precedenza e avere concesso in licenza l'account per Skype For Business Online, l'account verrà sincronizzato dalla foresta di Exchange Online a Skype for Business Online utilizzando la foresta di Active Directory di Windows Azure. I passaggi seguenti sono necessari per eseguire il provisioning dell'account di sistema sala Skype nel pool skype for business online. Questi passaggi sono gli stessi per un account della cassetta postale delle risorse esistente o per un account appena creato (confrm1 o confrm2), perché una volta abilitati in Exchange Online, entrambi questi account verranno sincronizzati con Skype for Business Online nello stesso modo:
  
1. Creare una sessione remota di PowerShell. Tenere presente che sarà necessario scaricare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Per abilitare un account di sistema sala Skype per Skype for Business, eseguire il comando seguente:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    È possibile ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for Business sono ospitati da uno degli account esistenti utilizzando il comando seguente per ottenere questa proprietà:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Multi-Factor Authentication (MFA) non è supportato per gli account di sistema sala Skype. 

## <a name="password-expiration"></a>Scadenza password

In Microsoft 365 o Office 365, il criterio di scadenza delle password predefinito per tutti gli account utente è di 90 giorni, a meno che non si configurano criteri di scadenza delle password diversi. Per gli account di sistema sala Skype, è possibile selezionare l'impostazione Nessuna scadenza password con la procedura seguente.
  
1. Creare una Windows Azure di Active Directory utilizzando le credenziali di amministratore globale del tenant.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Impostare l'impostazione Nessuna scadenza password per l'account sala di sistema skype room creato in precedenza utilizzando il comando seguente:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Per ulteriori informazioni, vedere [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="validate"></a>Convalida

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere all'account creato.