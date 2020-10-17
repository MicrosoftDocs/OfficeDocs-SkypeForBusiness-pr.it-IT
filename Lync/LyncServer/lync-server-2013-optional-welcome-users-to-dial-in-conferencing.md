---
title: 'Lync Server 2013: (facoltativo) accogliere gli utenti per le conferenze telefoniche con accesso esterno'
description: 'Lync Server 2013: (facoltativo) accogliere gli utenti per le conferenze telefoniche con accesso esterno.'
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
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546902"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="39397-103">Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39397-103">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39397-104">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="39397-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="39397-105">Dopo aver configurato la funzionalità di conferenza telefonica con accesso esterno e aver eseguito il test per verificarne il corretto funzionamento, è consigliabile impostare PIN iniziali per gli utenti e notificare agli utenti la disponibilità della funzionalità, incluse istruzioni di presentazione quali il PIN iniziale e il collegamento alla pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="39397-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="39397-106">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="39397-106">This step is optional.</span></span> <span data-ttu-id="39397-107">Per reimpostare i PIN, in genere viene utilizzato il cmdlet **Set-CsClientPin**, ma la prima volta è possibile utilizzare la procedura illustrata in questo argomento se si desidera inviare un messaggio di benvenuto con le informazioni.</span><span class="sxs-lookup"><span data-stu-id="39397-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="39397-108">Se non si desidera inviare tale messaggio, è possibile utilizzare **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="39397-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="39397-109">Lo script **Set-CsPinSendCAWelcomeMail** consente di impostare il PIN e inviare un messaggio di benvenuto a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="39397-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="39397-110">Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile utilizzare il parametro **Force** per forzarne la reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="39397-110">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="39397-111">Il messaggio di posta elettronica viene inviato utilizzando il protocollo SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="39397-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="39397-112">È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in modo iterativo in modo da impostare i PIN e inviare un messaggio di posta elettronica a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="39397-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="39397-113">È inoltre possibile modificare il modello di posta elettronica, ovvero il file **CAWelcomeEmailTemplate.html**, per aggiungere altri collegamenti alle pagine Intranet o per modificare il testo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="39397-113">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="39397-114">Per impostare un PIN iniziale e inviare un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="39397-114">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="39397-115">Accedere come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="39397-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39397-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="39397-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="39397-117">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="39397-117">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="39397-118">**SmtpServer**     Per impostazione predefinita, lo script utilizza il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="39397-118">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="39397-119">Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="39397-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="39397-120">**Credenziale**     Per impostazione predefinita, lo script utilizza le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="39397-120">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="39397-121">Se tale utente non dispone dell'autorizzazione per inviare un messaggio di posta elettronica con l'indirizzo Da specificato, è necessario immettere questo parametro.</span><span class="sxs-lookup"><span data-stu-id="39397-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="39397-122">Come regola generale, il parametro deve essere immesso se non si specifica l'indirizzo di posta elettronica come indirizzo Da.</span><span class="sxs-lookup"><span data-stu-id="39397-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="39397-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="39397-123">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="39397-p106">In questo esempio viene creato un nuovo PIN e quindi inviato un messaggio di benvenuto da parte di Marco a Bob. Viene utilizzato il testo del messaggio di posta elettronica del modello predefinito e utilizzato il formato HTML per il messaggio. L'oggetto predefinito è "Welcome to Dial In Conferencing".</span><span class="sxs-lookup"><span data-stu-id="39397-p106">This example creates a new PIN and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="39397-127">Un altro esempio:</span><span class="sxs-lookup"><span data-stu-id="39397-127">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="39397-p107">In questo esempio viene forzata l'impostazione di un nuovo PIN con il valore "383042650" per Bob, anche se Bob disponeva di un PIN esistente, e quindi inviato un messaggio di benvenuto da parte di Marco a Bob. Poiché il parametro Credential è specificato, all'utente che esegue il comando viene richiesto di immettere una password. Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="39397-p107">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

