---
title: Provisioning degli account di sistema di Skype room in Microsoft 365 e Office 365
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
description: Leggere questo argomento per informazioni sul provisioning degli account di sistema di Skype room in Microsoft 365 o Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820846"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Provisioning degli account di sistema di Skype room in Microsoft 365 e Office 365
 
Leggere questo argomento per informazioni sul provisioning degli account di sistema di Skype room in Microsoft 365 o Office 365.
  
Nella sezione seguente viene illustrato il provisioning dell'account del sistema di chat room Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Prerequisiti di Microsoft 365 e Office 365

Il tenant online deve soddisfare i requisiti seguenti:
  
- Il piano Microsoft 365 o Office 365 deve includere Skype for business online (piano 2) o Office 365 E1, E3 o E5. <br/>Per informazioni dettagliate sui piani di Skype for business online, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Il tenant deve disporre della funzionalità di conferenza abilitata per Skype for business.
    
- Il tenant deve disporre di Exchange Online abilitato. 
    
- L'amministratore remoto del tenant deve disporre dell'accesso PowerShell seguente:
    
  - Accesso a Remote PowerShell di Exchange
    
  - Accesso remoto a PowerShell di Skype for business online
    
  - Modulo di Windows Azure Active Directory per Windows PowerShell per accedere a Microsoft 365 o all'accesso alla directory di Office 365
    
Per l'account della sala Skype, è necessaria la licenza seguente:
  
- È richiesta una licenza di Skype for business online piano 2 o Office 365 E1 o E3 per abilitare le riunioni Skype.
    
- Per autorizzare la chat room con la funzionalità VoIP aziendale in modo che la sala possa essere abilitata con un numero di telefono, è necessario un piano 2 di Skype for business online con la licenza del sistema telefonico o Office 365 E5 (1).
    
- Se si necessita di funzionalità di accesso esterno da una riunione, sarà necessario disporre di una licenza di audioconferenza e sistema telefonico.  Se si necessita di funzionalità di chiamata in uscita da una riunione, sarà necessario un piano per chiamate nazionali o nazionali e internazionali. 
    
- Non è necessaria una licenza di Exchange Online per l'account della sala Skype perché l'account deve essere configurato come account della cassetta postale per le risorse.
    
## <a name="provisioning-overview"></a>Panoramica del provisioning

Nel diagramma seguente viene fornita una panoramica del flusso di provisioning dell'account del sistema di Skype room.
  
![Procedure per il provisioning di Skype room System](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificare una nuova sala riunioni

Potrebbe essere già presente una cassetta postale della sala risorse in Exchange che fornisce la funzionalità di pianificazione oppure è possibile creare una cassetta postale per la prima volta per facilitare la distribuzione di Skype room System. In ogni caso, è necessario identificare un account room da utilizzare nel tenant. Le sezioni del provisioning di Exchange Online e di Skype for business forniscono indicazioni per entrambi i tipi di account. Ad esempio, si supponga di avere le seguenti due sale e si desidera distribuire Skype room System per entrambi:
  
- Account della cassetta postale delle risorse esistente: confrm1@contoso.onmicrosoft.com
    
- Nuovo account della cassetta postale per le risorse: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisioning di Exchange Online

Per prima cosa, connettersi a PowerShell di Exchange Online seguendo le istruzioni riportate nell'argomento, [connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Per impostare un account di cassetta postale per la sala risorse esistente per il sistema in chat di Skype, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Per creare un nuovo account di cassetta postale per la risorsa di Exchange per il sistema delle sale Skype, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

I comandi precedenti consentono di impostare o creare un nuovo account di cassetta postale per la risorsa di Exchange per l'utilizzo del sistema in chat tramite l'abilitazione dell'account.
  
Dopo aver creato la cassetta postale, è possibile utilizzare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale. Per ulteriori informazioni, fare riferimento ai passaggi da 3 a 6 in distribuzioni locali in una foresta singola.

## <a name="assigning-a-skype-for-business-online-license"></a>Assegnazione di una licenza di Skype for business online

A questo punto è possibile assegnare una licenza di Skype for business online (piano 2) o Skype for business online (piano 3) utilizzando il portale amministrativo Microsoft 365 come descritto in [assegnare o rimuovere licenze per microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o in licenze per i componenti aggiuntivi di [Skype for business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Dopo aver assegnato una licenza per Skype for business online, è possibile effettuare l'accesso e verificare che l'account sia attivo utilizzando un client Skype for business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisioning di Skype for business online

Dopo aver creato e abilitato l'account di una cassetta postale della sala risorse, come illustrato in precedenza e aver concesso in licenza l'account per Skype for business online, l'account verrà sincronizzato dalla foresta di Exchange Online alla foresta di Skype for business online utilizzando la foresta di Windows Azure Active Directory. I passaggi seguenti sono necessari per eseguire il provisioning dell'account del sistema di chat room Skype nel pool Skype for business online. Questi passaggi sono gli stessi sia per un account della cassetta postale di una risorsa esistente che per un account appena creato (confrm1 o confrm2), perché dopo che sono stati abilitati in Exchange Online, entrambi gli account verranno sincronizzati con Skype for business online nello stesso modo:
  
1. Creare una sessione di PowerShell remota. Tenere presente che è necessario scaricare il modulo di Skype for Business Online Connector e l'assistente Sign-In dei Microsoft Online Services e verificare che il computer sia configurato. Per ulteriori informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Per abilitare un account di sistema di Skype room per Skype for business, eseguire il comando riportato di seguito:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    È possibile ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for business sono ospitati da uno degli account esistenti utilizzando il comando seguente per restituire la proprietà:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>L'autenticazione a più fattori (AMF) non è supportata per gli account di sistema di Skype room. 

## <a name="password-expiration"></a>Scadenza password

In Microsoft 365 o Office 365, i criteri di scadenza della password predefinita per tutti gli account utente sono di 90 giorni, a meno che non si configuri un criterio di scadenza di una password diversa. Per gli account di sistema delle chat room Skype, è possibile selezionare la password never expires setting con i passaggi seguenti.
  
1. Creare una sessione di Windows Azure Active Directory utilizzando le credenziali di amministratore globale del tenant.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Impostare la password never expires setting for the Skype room System room account creato in precedenza utilizzando il seguente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Per ulteriori informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Convalida

Per la convalida, è necessario essere in grado di utilizzare qualsiasi client Skype for business per accedere all'account creato.

