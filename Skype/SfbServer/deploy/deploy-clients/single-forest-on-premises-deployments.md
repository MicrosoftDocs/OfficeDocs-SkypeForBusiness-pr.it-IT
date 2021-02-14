---
title: Distribuzioni locali a foresta singola di Skype Room System
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
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820756"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Distribuzioni locali a foresta singola di Skype Room System
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.
  
In questa sezione viene fornita una panoramica dei passaggi per il provisioning dell'account skype room system in Exchange Server e Skype for Business Server ospitato in una distribuzione locale a foresta singola.
  
## <a name="single-forest-on-premises-deployments"></a>Distribuzioni locali della singola foresta

Se si dispone già di un account cassetta postale per le risorse per la sala conferenze, è possibile utilizzarlo. In caso contrario, sarà necessario crearne uno nuovo. È possibile utilizzare Exchange Management Shell (PowerShell) o Exchange Management Console creare un nuovo account cassetta postale per le risorse. È consigliabile usare una nuova cassetta postale per le risorse (eliminare la vecchia cassetta postale e creare di nuovo) per Skype Room System. Assicurarsi di eseguire il backup dei dati della cassetta postale prima di eliminarli e quindi esportarlo di nuovo nella cassetta postale ri-creata utilizzando il client Outlook (per ulteriori informazioni, vedere Esportare o eseguire il backup di messaggi, calendario, attività e contatti). Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [Connettere o ripristinare una cassetta postale eliminata.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Per utilizzare un account cassetta postale per le risorse esistente (ad esempio, LRS-01), attenersi alla procedura seguente:
  
1. Eseguire il seguente comando di Exchange Management PowerShell:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se si prevede di creare una nuova cassetta postale, quindi, per un'organizzazione exchange locale a foresta singola, eseguire il comando seguente:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale sala per una sala riunioni in un'organizzazione exchange locale. Il parametro RoomMailboxPassword consente di specificare la password per l'account utente.
    
3. Configurare l'account per risolvere automaticamente i conflitti accettando/rifiutando le riunioni. Gli account delle sale riunioni dotati di Skype Room System in Exchange possono essere gestiti da singoli utenti, ma tieni presente che finché l'utente non accetta una riunione non verrà visualizzato nel calendario della schermata iniziale di Skype Room System.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.
    
   Per ricordare agli organizzatori della riunione di impostare la riunione online su Skype for Business in Outlook, eseguire il comando seguente per configurare un avviso messaggio per il nuovo account: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Utilizzare i comandi seguenti per configurare le stringhe localizzate. Se richiesto dall'organizzazione, è anche possibile aggiungere traduzioni personalizzate: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facoltativo: configurare il testo di accettazione delle riunioni che fornisce agli utenti informazioni su Skype for Business Meeting Room e cosa aspettarsi quando pianificano e aderiscono alle riunioni. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Controllare l'account della cassetta postale per la risorsa in Active Directory

L'account della cassetta postale della sala riunioni creato da Exchange nel passaggio 1 precedente potrebbe essere un oggetto utente disabilitato in Active Directory. Skype Room System non può accedere o eseguire l'autenticazione utilizzando l'autenticazione Kerberos/NTLM se l'account è disabilitato in Active Directory. Il client Skype Room System deve essere in grado di eseguire l'autenticazione in Servizi Web Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna. 
  
Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti: 
  
1. In Active Directory, eseguire il comando seguente per abilitare l'accesso all'account: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   L'esecuzione di questo comando richiederà di immettere la password corrente e quindi di reimmissione della password due volte per la conferma.
    
2. Dopo aver impostato la password, eseguire il comando seguente per abilitare l'account: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Abilitazione degli account di Skype Room System per Skype for Business

Questa sezione fornisce una panoramica dei passaggi necessari per abilitare Skype for Business per l'account della sala riunioni, che verrà configurato in Skype Room System. 
  
Dopo aver creato un account della cassetta postale per le risorse per le sale riunioni, utilizzare Skype for Business Server Management Shell per abilitare gli account di Skype Room System per i servizi Skype for Business.
  
> [!NOTE]
> Nella procedura seguente si presuppone che l'account Skype Room System sia stato abilitato in Active Directory. 
  
1. Eseguire il comando seguente per abilitare l'account skype room system in un pool di Skype for Business Server:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facoltativo: consentire a questo account di effettuare e ricevere chiamate telefoniche PSTN abilitando l'account per VoIP aziendale. VoIP aziendale non è necessario per Skype Room System, ma se non lo abiliti per VoIP aziendale, il client Skype Room System non sarà in grado di fornire funzionalità di composizione PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se abiliti VoIP aziendale per l'account della sala riunioni di Skype Room System, assicurati di configurare un criterio vocale con restrizioni adatto alla tua organizzazione. Se la sala riunioni di Skype for Business è una risorsa disponibile pubblicamente, chiunque può usarla per partecipare a una riunione, pianificata o ad hoc. Dopo la partecipazione a una riunione, la persona può chiamare un numero qualsiasi. In Skype for Business Server, la funzionalità di chiamata in uscita dalle conferenze utilizza i criteri vocali dell'utente, in questo caso l'account di Sistema sala Skype usato per partecipare alla riunione. Nelle versioni precedenti di Lync Server viene utilizzato il criterio vocale dell'organizzatore. Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala riunioni di Skype Room System, chiunque può usare la sala riunioni Skype for Business per partecipare alla riunione e può comporre qualsiasi numero di telefono nazionale/regionale o internazionale, purché l'organizzatore sia autorizzato a comporre tali numeri. 
  

