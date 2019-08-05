---
title: Inviare la posta elettronica di benvenuto agli utenti con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Riepilogo: informazioni su come accogliere gli utenti in servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: db2e8bd84fa6a03bad845a87f7fb3c1532ae7ec2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188912"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Inviare la posta elettronica di benvenuto agli utenti con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come accogliere gli utenti in servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Dopo aver configurato i servizi di conferenza telefonica con accesso esterno e i test per verificare che funzioni correttamente, è necessario impostare i pin (Personal Identification Number) iniziali per gli utenti e comunicare agli utenti la disponibilità della funzionalità. È possibile includere istruzioni introduttive, ad esempio il PIN iniziale e il collegamento alla pagina Web delle impostazioni di conferenza telefonica con accesso esterno. 
  
In genere, si usa il cmdlet **Set-CsClientPin** per reimpostare i pin, ma è possibile usare la procedura descritta in questo argomento se si vuole inviare un messaggio di benvenuto introduttivo con le informazioni sul pin. Se non si vuole inviare il messaggio di posta elettronica, è possibile usare invece **Set-CsClientPin** .
  
Puoi usare lo script **Set-CsPinSendCAWelcomeMail** per impostare il PIN e inviare un messaggio di benvenuto a un singolo utente. Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile usare il parametro Force per forzare la reimpostazione di un PIN. Il messaggio di posta elettronica viene inviato tramite SMTP (Simple Mail Transfer Protocol).
  
È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in maniera iterativa per impostare i pin e inviare messaggi di posta elettronica a un gruppo di utenti. È possibile modificare il modello di posta elettronica, ovvero il file CAWelcomeEmailTemplate. html, per aggiungere altri collegamenti alle pagine Intranet o modificare il testo della posta elettronica.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Impostare un PIN iniziale e inviare un messaggio di benvenuto

1. Accedere come membro del gruppo RTCUniversalServerAdmins.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```
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

**SmtpServer** Per impostazione predefinita, lo script usa il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro. Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.
    
**Credenziali** Per impostazione predefinita, lo script usa le credenziali dell'utente corrente. Se l'utente corrente non ha l'autorizzazione per inviare messaggi di posta elettronica per conto dell'indirizzo specificato da, devi specificare questo parametro. Come regola generale, specificare questo parametro se non si specifica l'indirizzo di posta elettronica come indirizzo mittente.
    
Nell'esempio seguente viene creato un nuovo PIN e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Roberto. Usa il testo della posta elettronica dal modello predefinito e crea il messaggio di posta elettronica in formato HTML. L'oggetto predefinito è "Welcome to dial in conferenza":
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

Nell'esempio successivo viene forzato un nuovo PIN con un valore "383042650" per Roberto, anche se Roberto ha un PIN esistente e quindi Invia un messaggio di benvenuto da Marco a Roberto. Dato che viene specificato il parametro Credential, viene chiesto di immettere una password per la persona con cui viene eseguito il comando. Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer):
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
