---
title: 'Lync Server 2013: (facoltativo) accogliere gli utenti per le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: 4698484c240322623760f1fd308398192bfb928f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Dopo aver configurato la funzionalità di conferenza telefonica con accesso esterno e aver eseguito il test per verificarne il corretto funzionamento, è consigliabile impostare PIN iniziali per gli utenti e notificare agli utenti la disponibilità della funzionalità, incluse istruzioni di presentazione quali il PIN iniziale e il collegamento alla pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno. Questo passaggio è facoltativo. Per reimpostare i PIN, in genere viene utilizzato il cmdlet **Set-CsClientPin**, ma la prima volta è possibile utilizzare la procedura illustrata in questo argomento se si desidera inviare un messaggio di benvenuto con le informazioni. Se non si desidera inviare tale messaggio, è possibile utilizzare **Set-CsClientPin**.

Lo script **Set-CsPinSendCAWelcomeMail** consente di impostare il PIN e inviare un messaggio di benvenuto a un singolo utente. Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile utilizzare il parametro **Force** per forzarne la reimpostazione. Il messaggio di posta elettronica viene inviato utilizzando il protocollo SMTP (Simple Mail Transfer Protocol).

È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in modo iterativo in modo da impostare i PIN e inviare un messaggio di posta elettronica a un gruppo di utenti. È inoltre possibile modificare il modello di posta elettronica, ovvero il file **CAWelcomeEmailTemplate.html**, per aggiungere altri collegamenti alle pagine Intranet o per modificare il testo del messaggio.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Per impostare un PIN iniziale e inviare un messaggio di benvenuto

1.  Accedere come membro del gruppo RTCUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire il comando seguente al prompt:
    
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
    
    **SmtpServer**   per impostazione predefinita, lo script utilizza il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro. Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.
    
    **Credential**   per impostazione predefinita, lo script utilizza le credenziali dell'utente corrente. Se tale utente non dispone dell'autorizzazione per inviare un messaggio di posta elettronica con l'indirizzo Da specificato, è necessario immettere questo parametro. Come regola generale, il parametro deve essere immesso se non si specifica l'indirizzo di posta elettronica come indirizzo Da.
    
    Ad esempio:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    In questo esempio viene creato un nuovo PIN e quindi inviato un messaggio di benvenuto da parte di Marco a Bob. Viene utilizzato il testo del messaggio di posta elettronica del modello predefinito e utilizzato il formato HTML per il messaggio. L'oggetto predefinito è "Welcome to Dial In Conferencing".
    
    Un altro esempio:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    In questo esempio viene forzata l'impostazione di un nuovo PIN con il valore "383042650" per Bob, anche se Bob disponeva di un PIN esistente, e quindi inviato un messaggio di benvenuto da parte di Marco a Bob. Poiché il parametro Credential è specificato, all'utente che esegue il comando viene richiesto di immettere una password. Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

