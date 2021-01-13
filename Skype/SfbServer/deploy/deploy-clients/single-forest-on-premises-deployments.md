---
title: Distribuzioni locali di Skype room System Single Forest
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente locale in una foresta singola.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820756"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Distribuzioni locali di Skype room System Single Forest
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente locale in una foresta singola.
  
In questa sezione viene fornita una panoramica dei passaggi per il provisioning dell'account del sistema di chat room Skype su Exchange Server e Skype for Business Server ospitato in una distribuzione locale di una singola foresta.
  
## <a name="single-forest-on-premises-deployments"></a>Distribuzioni locali della singola foresta

Se si dispone già di un account della cassetta postale delle risorse per la sala conferenze, è possibile utilizzarlo. In caso contrario, è necessario crearne uno nuovo. È possibile utilizzare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account di cassetta postale per la risorsa. Si consiglia di usare una nuova cassetta postale per la risorsa di Skype (Delete Old mailbox and ricreate) per il sistema in chat. Assicurarsi di eseguire il backup dei dati delle cassette postali prima di eliminarlo e quindi di riesportarlo nella cassetta postale ricreata utilizzando il client Outlook (vedere esportare o eseguire il backup di messaggi, calendario, attività e contatti per altre informazioni). Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Per utilizzare un account di cassetta postale per la risorsa esistente (ad esempio, LRS-01), attenersi alla procedura seguente:
  
1. Eseguire il seguente comando di Exchange Management PowerShell:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se si prevede di creare una nuova cassetta postale, eseguire il comando riportato di seguito per una singola organizzazione di Exchange in una foresta locale.
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale sala per una sala riunioni in un'organizzazione di Exchange locale. Il parametro RoomMailboxPassword consente di specificare la password per l'account utente.
    
3. Configurare l'account per risolvere automaticamente i conflitti accettando o rifiutando le riunioni. Gli account delle sale riunioni attrezzate con Skype room System in Exchange possono essere gestiti da singoli utenti, ma si noti che fino a quando l'utente non accetta una riunione non verrà visualizzato nel calendario della schermata iniziale del sistema Skype room.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.
    
   Per ricordare agli organizzatori della riunione di rendere la riunione una riunione Skype for business online in Outlook, utilizzare il seguente comando per configurare un avviso messaggio per il nuovo account: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilizzare i seguenti comandi per configurare le stringhe localizzate. Se richiesto dall'organizzazione, è anche possibile aggiungere le traduzioni personalizzate: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facoltativo: configurare il testo di accettazione della riunione che fornisce agli utenti informazioni sulla sala riunioni di Skype for business e cosa aspettarsi durante la pianificazione e la partecipazione alle riunioni. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Controllare l'account della cassetta postale delle risorse in Active Directory

L'account della cassetta postale della sala riunioni creato da Exchange nel passaggio 1 potrebbe essere un oggetto utente disabilitato in Active Directory. Skype room System non è in grado di eseguire l'accesso o l'autenticazione tramite Kerberos/NTLM se l'account è disabilitato in Active Directory. Il client del sistema Skype Room deve essere in grado di eseguire l'autenticazione con i servizi Web di Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna. 
  
Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti: 
  
1. In Active Directory, eseguire il comando riportato di seguito per abilitare l'accesso all'account: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Se si esegue questo comando, verrà richiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.
    
2. Dopo aver impostato la password, eseguire il comando riportato di seguito per abilitare l'account: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Abilitazione degli account di sistema di Skype room per Skype for business

In questa sezione viene fornita una panoramica dei passaggi necessari per abilitare Skype for business per l'account della sala riunioni, che sarà configurato su Skype room System. 
  
Dopo aver creato un account per le cassette postali delle risorse per le sale conferenze, utilizzare Skype for Business Server Management Shell per abilitare gli account Skype for business room System.
  
> [!NOTE]
> La procedura seguente presuppone che sia stato abilitato l'account Skype room System in Active Directory. 
  
1. Eseguire il seguente comando per abilitare l'account del sistema di chat room Skype su un pool di Skype for Business Server:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facoltativo: consentire a questo account di effettuare e ricevere telefonate PSTN abilitando l'account per VoIP aziendale. VoIP aziendale non è necessario per Skype room System, ma se non lo si Abilita per VoIP aziendale, il client del sistema Skype room non sarà in grado di fornire la funzionalità di composizione PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si Abilita VoIP aziendale per l'account della sala riunioni di Skype room System, assicurarsi di configurare un criterio vocale limitato appropriato per la propria organizzazione. Se la sala riunioni di Skype for business è una risorsa disponibile pubblicamente, chiunque può utilizzarla per partecipare a una riunione, pianificata o ad hoc. Dopo aver partecipato a una riunione, la persona potrebbe comporre qualsiasi numero. In Skype for Business Server, la funzionalità di accesso esterno per le conferenze utilizza il criterio vocale dell'utente, in questo caso l'account di sistema della sala Skype utilizzato per partecipare alla riunione. Nelle versioni precedenti di Lync Server, viene utilizzato il criterio vocale dell'organizzatore. Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala di Skype room System, chiunque può utilizzare la sala riunioni di Skype for business per partecipare alla riunione e potrebbe comporre un numero di telefono nazionale/regionale o internazionale, purché l'organizzatore sia autorizzato a comporre tali numeri. 
  

