---
title: 'Lync Server 2013: (Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Dopo aver configurato i servizi di conferenza telefonica con accesso esterno e i test per verificare che funzioni correttamente, è necessario impostare i pin (Personal Identification Number) iniziali per gli utenti e comunicare agli utenti la disponibilità della funzionalità, incluse le istruzioni introduttive come PIN iniziale e il collegamento alla pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno. Questo passaggio è facoltativo. In genere, si usa il cmdlet **Set-CsClientPin** per reimpostare i pin, ma è possibile usare la procedura descritta in questo argomento per la prima volta se si vuole inviare un messaggio di posta elettronica di benvenuto con le informazioni. Se non si vuole inviare il messaggio di posta elettronica, è possibile usare invece **Set-CsClientPin** .

Puoi usare lo script **Set-CsPinSendCAWelcomeMail** per impostare il PIN e inviare un messaggio di benvenuto a un singolo utente. Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile usare il parametro **Force** per forzare la reimpostazione di un PIN. Il messaggio di posta elettronica viene inviato tramite SMTP (Simple Mail Transfer Protocol).

È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in maniera iterativa per impostare i pin e inviare messaggi di posta elettronica a un gruppo di utenti. È possibile modificare il modello di posta elettronica, ovvero il file **CAWelcomeEmailTemplate. html** , per aggiungere altri collegamenti alle pagine Intranet o modificare il testo della posta elettronica.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Per impostare un PIN iniziale e inviare un messaggio di benvenuto

1.  Accedere come membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
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
    
    **SmtpServer**   per impostazione predefinita, lo script usa il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro. Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.
    
    **Credenziali**   per impostazione predefinita, lo script usa le credenziali dell'utente corrente. Se l'utente corrente non ha l'autorizzazione per inviare messaggi di posta elettronica per conto dell'indirizzo specificato da, devi specificare questo parametro. Come regola generale, specificare questo parametro se non si specifica l'indirizzo di posta elettronica come indirizzo mittente.
    
    Ad esempio:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    In questo esempio viene creato un nuovo PIN e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Roberto. Usa il testo della posta elettronica dal modello predefinito e crea il messaggio di posta elettronica in formato HTML. L'oggetto predefinito è "Welcome to dial in Conferencing".
    
    Un altro esempio:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    In questo esempio viene forzato un nuovo PIN con un valore "383042650" per Roberto, anche se Roberto ha un PIN esistente e quindi Invia un messaggio di benvenuto da Marco a Roberto. Dato che viene specificato il parametro Credential, viene chiesto di immettere una password per la persona con cui viene eseguito il comando. Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

