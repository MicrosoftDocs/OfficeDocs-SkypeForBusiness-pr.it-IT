---
title: Distribuzioni locali di Skype room System Single Forest
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un unico ambiente della foresta locale.
ms.openlocfilehash: 2d73ee2313088c653f4362139cb431e55d92015b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775264"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Distribuzioni locali di Skype room System Single Forest
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un unico ambiente della foresta locale.
  
Questa sezione offre una panoramica dei passaggi per il provisioning dell'account di sistema room Skype su Exchange Server e Skype for Business Server ospitato in una singola distribuzione locale della foresta.
  
## <a name="single-forest-on-premises-deployments"></a>Distribuzioni locali singole della foresta

Se si dispone già di un account di cassetta postale delle risorse per la sala conferenze, è possibile usarlo. In caso contrario, sarà necessario crearne uno nuovo. È possibile usare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account di cassetta postale per la risorsa. È consigliabile usare una nuova cassetta postale delle risorse (Elimina vecchia cassetta postale e ricrea) per Skype room System. Assicurarsi di eseguire il backup dei dati delle cassette postali prima di eliminarli e quindi di esportarli nella cassetta postale ricreata usando il client Outlook (vedere esportare o eseguire il backup di messaggi, calendario, attività e contatti per altre informazioni). Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Per usare un account della cassetta postale delle risorse esistente, ad esempio LRS-01, eseguire la procedura seguente:
  
1. Eseguire il comando di PowerShell di Exchange Management seguente:
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Se si prevede di creare una nuova cassetta postale, eseguire il comando seguente per una singola organizzazione di Exchange locale della foresta:
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale della sala per una sala riunioni in un'organizzazione di Exchange locale. Il parametro RoomMailboxPassword specifica la password per l'account utente.
    
3. Configurare l'account per risolvere automaticamente i conflitti accettando o rifiutando le riunioni. Skype room System-attrezzato account sala conferenze in Exchange può essere gestito da singoli utenti, ma tenere presente che finché l'utente non accetta una riunione non verrà visualizzata nel calendario della schermata iniziale di Skype room System.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.
    
   Per ricordare agli organizzatori della riunione di partecipare a una riunione Skype for business online in Outlook, eseguire il comando seguente per configurare un MailTip per il nuovo account: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Usare i comandi seguenti per configurare le stringhe localizzate. Se richiesto dall'organizzazione, è anche possibile aggiungere traduzioni personalizzate: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Facoltativo: configurare il testo di accettazione della riunione che fornisce agli utenti informazioni sulla sala riunioni di Skype for business e cosa aspettarsi quando pianificano e partecipano alle riunioni. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Controllare l'account delle cassette postali in Active Directory

L'account delle cassette postali della sala riunioni creato da Exchange nel passaggio 1 potrebbe essere un oggetto utente disabilitato in Active Directory. Skype room System non è in grado di accedere o eseguire l'autenticazione tramite Kerberos/NTLM se l'account è disabilitato in Active Directory. Il client di sistema room Skype deve essere in grado di eseguire l'autenticazione con i servizi Web di Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna. 
  
Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti: 
  
1. In Active Directory eseguire il comando seguente per abilitare l'accesso all'account: 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   In questo comando verrà chiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.
    
2. Dopo aver impostato la password, eseguire il comando seguente per abilitare l'account: 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Abilitazione degli account di Skype room System per Skype for business

Questa sezione fornisce una panoramica dei passaggi necessari per abilitare Skype for business per l'account della sala riunioni, che sarà configurato in Skype room System. 
  
Dopo aver creato un account per le cassette postali per le sale conferenza, usare Skype for Business Server Management Shell per abilitare gli account di Skype for business room System.
  
> [!NOTE]
> La procedura seguente presuppone che l'account di sistema della sala Skype sia stato abilitato in Active Directory. 
  
1. Eseguire il comando seguente per abilitare l'account di sistema room Skype in un pool di Skype for Business Server:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Facoltativo: consentire a questo account di effettuare e ricevere chiamate telefoniche PSTN abilitando l'account per VoIP aziendale. Enterprise Voice non è necessaria per Skype room System, ma se non è abilitato per VoIP aziendale, il client di sistema room Skype non sarà in grado di specificare la funzionalità di chiamata PSTN:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si Abilita Enterprise Voice per l'account della sala riunioni di Skype room System, assicurarsi di configurare un criterio vocale con restrizioni appropriato per l'organizzazione. Se la sala riunioni di Skype for business è una risorsa disponibile pubblicamente, chiunque può usarla per partecipare a una riunione, programmata o ad hoc. Dopo aver partecipato a una riunione, la persona può effettuare la chiamata a qualsiasi numero. In Skype for Business Server, la funzionalità di chiamata in uscita dalle conferenze usa il criterio vocale dell'utente, in questo caso l'account di sistema room Skype usato per partecipare alla riunione. Nelle versioni precedenti di Lync Server viene usato il criterio vocale dell'organizzatore. Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala di Skype room System, chiunque può usare la sala riunioni di Skype for business per partecipare alla riunione e può chiamare qualsiasi telefono nazionale/regionale o internazionale numero, purché l'organizzatore sia autorizzato a chiamare questi numeri. 
  

