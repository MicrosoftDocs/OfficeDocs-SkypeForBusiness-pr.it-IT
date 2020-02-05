---
title: Provisioning degli account di Skype room System in Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leggere questo argomento per informazioni sul provisioning degli account di Skype room System in Office 365.
ms.openlocfilehash: 33c3acf2f0fffc69da55468e8c16902ec7fa4f88
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768749"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Provisioning degli account di Skype room System in Office 365
 
Leggere questo argomento per informazioni sul provisioning degli account di Skype room System in Office 365.
  
La sezione seguente illustra il provisioning degli account di Skype room System per un tenant di Office 365.
  
## <a name="office-365-prerequisites"></a>Prerequisiti di Office 365

Il tenant online deve soddisfare i requisiti seguenti:
  
- Il piano di Office 365 deve includere Skype for business online Plan 2 o Office 365 E1, E3 o E5. <br/>Per informazioni dettagliate sui piani di Skype for business online, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Il tenant deve avere la funzionalità di conferenza di Skype for business abilitata.
    
- Il tenant deve avere abilitato Exchange Online. 
    
- L'amministratore remoto del tenant deve avere l'accesso di PowerShell seguente:
    
  - Accesso remoto a PowerShell di Exchange
    
  - Accesso remoto a PowerShell per Skype for business online
    
  - Modulo di Windows Azure Active Directory per Windows PowerShell per accedere alla directory di Office 365 Access
    
Per l'account della sala Skype è necessaria la licenza seguente:
  
- Per abilitare le riunioni Skype è necessaria una licenza di Skype for business online Plan 2 o Office 365 E1 o E3.
    
- Per autorizzare la chat room con la funzionalità VoIP aziendale in modo che la chat room possa essere abilitata con un numero di telefono, è necessario un piano 2 Skype for business online con la licenza per il sistema telefonico o Office 365 E5 (1).
    
- Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per l'audioconferenza e il sistema telefonico.  Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessario un piano per chiamate nazionali o nazionali e internazionali. 
    
- Una licenza di Exchange Online non è necessaria per l'account della sala Skype perché l'account deve essere configurato come account di cassetta postale per le risorse.
    
## <a name="provisioning-overview"></a>Panoramica del provisioning

Il diagramma seguente offre una panoramica del flusso di provisioning degli account di Skype room System in Office 365.
  
![Procedura per il provisioning di Skype room System per Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificare una nuova sala riunioni

Potrebbe essere già presente una cassetta postale della sala risorse in Exchange che fornisce la funzionalità di pianificazione oppure creare una cassetta postale per la prima volta per facilitare la distribuzione di Skype room System. In ogni caso, devi identificare un account room da usare nel tenant. Le sezioni Exchange Online Provision e Skype for business promettono indicazioni per entrambi i tipi di account. Supponiamo, ad esempio, di avere le due sale seguenti e si vuole distribuire Skype room System per entrambi:
  
- Account delle cassette postali delle risorse esistenti: confrm1@contoso.onmicrosoft.com
    
- Nuovo account di cassetta postale per le risorse: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Provisioning di Exchange Online

Prima di tutto, connettersi a PowerShell di Exchange Online seguendo le istruzioni dell'argomento [connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Per impostare un account della cassetta postale della sala risorse esistente per Skype room System, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Per creare un nuovo account delle cassette postali di Exchange per Skype room System, eseguire i comandi seguenti in PowerShell di Exchange Online:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

I comandi precedenti configurano o creano un nuovo account di cassetta postale di Exchange per l'utilizzo di Skype room System abilitando l'account.
  
Dopo aver creato la cassetta postale, è possibile usare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale. Vedere i passaggi da 3 a 6 in distribuzioni locali di una singola foresta per altre informazioni

## <a name="assigning-a-skype-for-business-online-license"></a>Assegnazione di una licenza Skype for business online

Ora è possibile assegnare una licenza di Skype for business online (piano 2) o Skype for business online (piano 3) usando il portale amministrativo di Office 365, come descritto in [assegnare o rimuovere licenze per office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o in licenze per i [componenti aggiuntivi Skype for business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Dopo aver assegnato una licenza per Skype for business online, è possibile effettuare l'accesso e verificare che l'account sia attivo usando qualsiasi client Skype for business.
  
## <a name="skype-for-business-online-provisioning"></a>Provisioning di Skype for business online

Dopo aver creato e abilitato un account della cassetta postale della sala risorse, come illustrato in precedenza, e aver concesso in licenza l'account per Skype for business online, l'account verrà sincronizzato dalla foresta di Exchange Online alla foresta di Skype for business online usando il Foresta di Windows Azure Active Directory. I passaggi seguenti sono necessari per eseguire il provisioning dell'account di sistema room Skype nel pool Skype for business online. Questi passaggi sono identici sia per un account di cassetta postale delle risorse esistente che per un account appena creato (confrm1 o confrm2), perché una volta abilitati in Exchange Online, entrambi gli account verranno sincronizzati con Skype for business online nello stesso modo:
  
1. Creare una sessione remota di PowerShell. Tieni presente che dovrai scaricare il modulo Connector di Skype for business online e l'assistente per l'accesso ai Microsoft Online Services e verificare che il computer sia configurato. Per altre informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Per abilitare un account di sistema room Skype per Skype for business, eseguire il comando seguente:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puoi ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for business si trovano in uno degli account esistenti usando il comando seguente per restituire questa proprietà:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>L'autenticazione a più fattori (AMF) non è supportata per gli account di sistema room Skype. 

## <a name="password-expiration"></a>Scadenza password

In Office 365 i criteri di scadenza della password predefiniti per tutti gli account utente sono di 90 giorni, a meno che non vengano configurati criteri di scadenza della password diversi. Per gli account di sistema Skype room, è possibile selezionare la password non scade mai con i passaggi seguenti.
  
1. Creare una sessione di Windows Azure Active Directory usando le credenziali di amministratore globale del tenant.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Impostare la password non scade mai l'impostazione per l'account della sala di Skype room System creato in precedenza usando il comando seguente:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Per altre informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Convalidare

Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere all'account creato.

