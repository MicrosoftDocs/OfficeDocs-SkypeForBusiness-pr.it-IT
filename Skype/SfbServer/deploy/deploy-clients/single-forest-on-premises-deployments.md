---
title: Skype Distribuzioni locali a foresta singola del sistema sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.
ms.openlocfilehash: 0f8ab644efc3d832fd5e201bd49517971ba5ba08
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828419"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Distribuzioni locali a foresta singola del sistema sala
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.
  
In questa sezione viene fornita una panoramica dei passaggi per il provisioning dell'account di Skype Room System in Exchange Server e Skype for Business Server ospitati in una distribuzione locale a foresta singola.
  
## <a name="single-forest-on-premises-deployments"></a>Distribuzioni locali della singola foresta

Se si dispone già di un account cassetta postale della risorsa per la sala conferenze, è possibile utilizzarlo. In caso contrario, sarà necessario crearne uno nuovo. È possibile utilizzare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account cassetta postale per le risorse. È consigliabile utilizzare una nuova cassetta postale (eliminare la cassetta postale precedente e creare di nuovo) per Skype Room System. Assicurarsi di eseguire il backup dei dati della cassetta postale prima di eliminarli e quindi esportarlo di nuovo nella cassetta postale ri-creata utilizzando il client Outlook (per ulteriori informazioni, vedere Esportare o eseguire il backup di messaggi, calendario, attività e contatti). Per ripristinare le riunioni perse eliminando la cassetta postale, [vedere Connessione o ripristinare una cassetta postale eliminata.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Per utilizzare un account cassetta postale delle risorse esistente (ad esempio, LRS-01) eseguire la procedura seguente:
  
1. Eseguire il comando Exchange Management PowerShell seguente:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se si prevede di creare una nuova cassetta postale, quindi, per una singola foresta locale Exchange organizzazione, eseguire il comando seguente:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale sala per una sala riunioni in un'organizzazione Exchange locale. Il parametro RoomMailboxPassword consente di specificare la password per l'account utente.
    
3. Configurare l'account per risolvere automaticamente i conflitti accettando/rifiutando le riunioni. Skype Gli account delle sale riunioni dotate di sistema sala Exchange possono essere gestiti da singoli utenti, ma si noti che fino a quando l'utente non accetta una riunione non verrà visualizzata nel calendario della schermata iniziale di Skype Room System.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.
    
   Per ricordare agli organizzatori della riunione di rendere la riunione una riunione Skype for Business online in Outlook, eseguire il comando seguente per configurare un suggerimento messaggio per il nuovo account: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilizzare i comandi seguenti per configurare le stringhe localizzate. Se richiesto dall'organizzazione, è anche possibile aggiungere traduzioni personalizzate: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facoltativo: configurare il testo di accettazione delle riunioni che fornisce agli utenti informazioni sulle Skype for Business Sala riunioni e su cosa aspettarsi quando pianificano e aderiscono alle riunioni. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Controllare l'account della cassetta postale della risorsa in Active Directory

L'account della cassetta postale della sala riunioni creato Exchange nel passaggio 1 precedente potrebbe essere un oggetto utente disabilitato in Active Directory. Skype Room System non può accedere o eseguire l'autenticazione utilizzando l'autenticazione Kerberos/NTLM se l'account è disabilitato in Active Directory. Il client Skype Room System deve essere in grado di eseguire l'autenticazione nei servizi Web di Exchange per recuperare le impostazioni del calendario e deve inoltre essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna. 
  
Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti: 
  
1. In Active Directory, eseguire il comando seguente per abilitare l'accesso all'account: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Eseguendo questo comando verrà richiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.
    
2. Dopo aver impostato la password, eseguire il comando seguente per abilitare l'account: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Abilitazione Skype account di sistema room per Skype for Business

In questa sezione viene fornita una panoramica dei passaggi necessari per abilitare Skype for Business per l'account della sala riunioni, che verrà configurato in Skype Room System. 
  
Dopo aver creato un account della cassetta postale delle risorse per le sale conferenze, utilizzare Skype for Business Server Management Shell per abilitare gli account Skype Room System per Skype for Business servizi.
  
> [!NOTE]
> La procedura seguente presuppone che sia stato abilitato l'account Skype Room System in Active Directory. 
  
1. Eseguire il comando seguente per abilitare l'account Skype Room System in un pool Skype for Business Server locale:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facoltativo: consentire a questo account di effettuare e ricevere chiamate telefoniche PSTN abilitando l'account per VoIP aziendale. VoIP aziendale non è necessario per Skype Room System, ma se non lo si abilita per VoIP aziendale, il client Skype Room System non sarà in grado di fornire funzionalità di composizione PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si abilita VoIP aziendale per l'account della sala Skype sala riunioni, assicurarsi di configurare un criterio vocale con restrizioni adatto all'organizzazione. Se la Skype for Business Sala riunioni è una risorsa disponibile pubblicamente, chiunque potrebbe usarla per partecipare a una riunione, pianificata o ad hoc. Dopo la partecipazione a una riunione, la persona potrebbe chiamare qualsiasi numero. In Skype for Business Server, la funzionalità di chiamata in uscita dalle conferenze utilizza il criterio vocale dell'utente, in questo caso l'account di sistema sala Skype utilizzato per partecipare alla riunione. Nelle versioni precedenti di Lync Server viene utilizzato il criterio vocale dell'organizzatore. Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account sala di sistema sala Skype, chiunque può utilizzare il Skype for Business Sala riunioni per partecipare alla riunione e può comporre qualsiasi numero di telefono nazionale/regionale o internazionale, purché l'organizzatore sia autorizzato a comporre tali numeri. 
