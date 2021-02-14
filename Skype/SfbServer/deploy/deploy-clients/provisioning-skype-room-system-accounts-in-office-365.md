---
title: Provisioning degli account di Skype Room System in Microsoft 365 e Office 365
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
description: Leggere questo argomento per informazioni sul provisioning degli account skype room system in Microsoft 365 o Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820846"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Provisioning degli account di Skype Room System in Microsoft 365 e Office 365
 
Leggere questo argomento per informazioni sul provisioning degli account skype room system in Microsoft 365 o Office 365.
  
Nella sezione seguente viene illustrato il provisioning degli account di Skype Room System.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Prerequisiti di Microsoft 365 e Office 365

Il tenant online deve soddisfare i requisiti seguenti:
  
- Il piano di Microsoft 365 o Office 365 deve includere Skype for Business online Piano 2 o Office 365 E1, E3 o E5. <br/>Per informazioni dettagliate sui piani di Skype for Business online, vedere la descrizione [del servizio Skype for Business online.](https://technet.microsoft.com/library/jj822172.aspx)
    
- Il tenant deve avere la funzionalità di conferenza di Skype for Business abilitata.
    
- Nel tenant deve essere abilitato Exchange Online. 
    
- L'amministratore remoto tenant deve disporre dell'accesso a PowerShell seguente:
    
  - Accesso a PowerShell remoto di Exchange
    
  - Accesso remoto a PowerShell in Skype for Business online
    
  - Windows Azure modulo di Active Directory per Windows PowerShell accesso alla directory di Microsoft 365 o Office 365
    
Per l'account Skype Room, sono necessarie le licenze seguenti:
  
- È necessaria una licenza skype for Business online piano 2 o Office 365 E1 o E3 per abilitare le riunioni Skype.
    
- Per autorizzare la sala con la funzionalità VoIP aziendale in modo che la sala possa essere abilitata con un numero di telefono, è necessario un Skype for Business online Piano 2 con licenza sistema telefonico o Office 365 E5 (1).
    
- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per audioconferenza e Sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessario un Piano per chiamate nazionali o nazionali e internazionali. 
    
- Non è necessaria una licenza di Exchange Online per l'account Skype Room perché l'account deve essere configurato come account della cassetta postale delle risorse.
    
## <a name="provisioning-overview"></a>Panoramica del provisioning

Nel diagramma seguente viene fornita una panoramica del flusso di provisioning degli account di Skype Room System.
  
![Passaggi di provisioning di Skype Room System](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificare una nuova sala riunioni

You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment. In ogni caso, è necessario identificare un account della sala da usare nel tenant. Le sezioni Provisioning di Exchange Online e Provisioning di Skype for Business forniscono indicazioni per entrambi i tipi di account. Ad esempio, si supponga di avere le due sale seguenti e che si desideri distribuire Skype Room System per entrambe:
  
- Account cassetta postale risorsa esistente: confrm1@contoso.onmicrosoft.com
    
- Nuovo account cassetta postale per la risorsa: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisioning di Exchange Online

Prima di tutto, connettersi a PowerShell di Exchange Online seguendo le istruzioni nell'argomento, [Connettersi a PowerShell di Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
Per impostare un account della cassetta postale sala risorse esistente per Skype Room System, eseguire i seguenti comandi in PowerShell di Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Per creare un nuovo account della cassetta postale delle risorse di Exchange per Skype Room System, eseguire i seguenti comandi in PowerShell di Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

I comandi precedenti configurano o creano un nuovo account della cassetta postale per le risorse di Exchange per l'utilizzo di Skype Room System abilitando l'account.
  
Dopo aver creato la cassetta postale, è possibile utilizzare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 nelle distribuzioni locali a foresta singola

## <a name="assigning-a-skype-for-business-online-license"></a>Assegnazione di una licenza di Skype for Business online

Ora è possibile assegnare una licenza di Skype for Business online (Piano 2) o Skype for Business online (Piano 3) usando il portale di amministrazione di Microsoft 365 come descritto in Assegnare o rimuovere licenze per le licenze per i componenti aggiuntivi [di Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) per le aziende o skype [for Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
Dopo aver assegnato una licenza per Skype for Business online, potrai accedere e verificare che l'account sia attivo usando qualsiasi client Skype for Business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisioning di Skype for Business online

Dopo aver creato e abilitato un account della cassetta postale della sala risorse come mostrato in precedenza e dopo aver concesso in licenza l'account per Skype for Business online, l'account verrà sincronizzato dalla foresta di Exchange Online alla foresta di Skype for Business online utilizzando la foresta di Active Directory di Windows Azure. I passaggi seguenti sono necessari per eseguire il provisioning dell'account skype room system nel pool di Skype for Business online. Questi passaggi sono gli stessi per un account della cassetta postale per le risorse esistente o per un account appena creato (confrm1 o confrm2), perché una volta abilitati in Exchange Online, entrambi gli account verranno sincronizzati con Skype for Business online nello stesso modo:
  
1. Creare una sessione remota di PowerShell. Si noti che sarà necessario scaricare il modulo del connettore di Skype for Business online e l'assistente di Microsoft Online Services Sign-In e assicurarsi che il computer sia configurato. Per ulteriori informazioni, vedere [Configurare il computer per Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Per abilitare un account skype room system per Skype for Business, eseguire il comando seguente:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puoi ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for Business sono ospitati da uno degli account esistenti usando il comando seguente per ottenere questa proprietà:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Multi-Factor Authentication (MFA) non è supportato per gli account skype room system. 

## <a name="password-expiration"></a>Scadenza password

In Microsoft 365 o Office 365, il criterio di scadenza delle password predefinito per tutti gli account utente è di 90 giorni, a meno che non si configurano criteri di scadenza delle password diversi. Per gli account di Skype Room System, puoi selezionare l'impostazione Password senza scadenza con la procedura seguente.
  
1. Creare una Windows Azure di Active Directory utilizzando le credenziali di amministratore globale del tenant.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Impostare l'impostazione Password never expires per l'account della sala riunioni Skype Room System creato in precedenza utilizzando il comando seguente:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Per ulteriori informazioni, vedere [Configurare il computer per Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  
## <a name="validate"></a>Convalida

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere all'account creato.

