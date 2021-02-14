---
title: Inviare messaggi di benvenuto agli utenti con accesso remoto in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Riepilogo: informazioni su come consentire agli utenti di accedere alle conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817496"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Inviare messaggi di benvenuto agli utenti con accesso remoto in Skype for Business Server
 
**Riepilogo:** Informazioni su come dare il benvenuto agli utenti alle conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Dopo aver configurato le conferenze telefoniche con accesso esterno e aver verificato che funzioni correttamente, è necessario impostare i PIN iniziali per gli utenti e informare gli utenti della disponibilità della funzionalità. È possibile includere istruzioni introduttive, ad esempio il PIN iniziale e il collegamento alla pagina Web Impostazioni conferenza telefonica con accesso esterno. 
  
In genere, si utilizza il cmdlet **Set-CsClientPin** per reimpostare i PIN, ma è possibile utilizzare la procedura descritta in questo argomento se si desidera inviare un messaggio di benvenuto introduttivo con le informazioni sul PIN. Se non si desidera inviare tale messaggio, è possibile utilizzare **Set-CsClientPin**.
  
Lo script **Set-CsPinSendCAWelcomeMail** consente di impostare il PIN e inviare un messaggio di benvenuto a un singolo utente. Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile utilizzare il parametro Force per forzarne la reimpostazione. Il messaggio di posta elettronica viene inviato utilizzando il protocollo SMTP (Simple Mail Transfer Protocol).
  
È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in modo iterativo in modo da impostare i PIN e inviare un messaggio di posta elettronica a un gruppo di utenti. È inoltre possibile modificare il modello di posta elettronica, ovvero il file CAWelcomeEmailTemplate.html, per aggiungere altri collegamenti alle pagine Intranet o per modificare il testo del messaggio.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Impostare un PIN iniziale e inviare un messaggio di benvenuto

1. Accedere come membro del gruppo RTCUniversalServerAdmins.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** Per impostazione predefinita, lo script utilizza il valore della variabile di ambiente **riservata $PSEmailServer** per questo parametro. Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.
    
**Credential** Per impostazione predefinita, lo script utilizza le credenziali dell'utente corrente. Se tale utente non dispone dell'autorizzazione per inviare un messaggio di posta elettronica con l'indirizzo Da specificato, è necessario immettere questo parametro. Come regola generale, il parametro deve essere immesso se non si specifica l'indirizzo di posta elettronica come indirizzo Da.
    
Nell'esempio seguente viene creato un nuovo PIN e quindi viene inviato un messaggio di benvenuto da Marco a Bob. Viene utilizzato il testo del messaggio di posta elettronica del modello predefinito e utilizzato il formato HTML per il messaggio. L'oggetto predefinito è "Welcome to Dial In Conferencing":
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

Nell'esempio seguente viene forzato un nuovo PIN con il valore "383042650" per Bob, anche se Bob aveva un PIN esistente, e quindi viene inviato un messaggio di benvenuto da Marco a Bob. Poiché il parametro Credential è specificato, all'utente che esegue il comando viene richiesto di immettere una password. Il messaggio di posta elettronica viene inviato utilizzando SSL (Secure Sockets Layer):
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
