---
title: 'Lync Server 2013: (Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="88f74-102">(Facoltativo) Presentazione della funzionalità di conferenza telefonica con accesso esterno agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88f74-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88f74-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="88f74-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="88f74-104">Dopo aver configurato i servizi di conferenza telefonica con accesso esterno e i test per verificare che funzioni correttamente, è necessario impostare i pin (Personal Identification Number) iniziali per gli utenti e comunicare agli utenti la disponibilità della funzionalità, incluse le istruzioni introduttive come PIN iniziale e il collegamento alla pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="88f74-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="88f74-105">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="88f74-105">This step is optional.</span></span> <span data-ttu-id="88f74-106">In genere, si usa il cmdlet **Set-CsClientPin** per reimpostare i pin, ma è possibile usare la procedura descritta in questo argomento per la prima volta se si vuole inviare un messaggio di posta elettronica di benvenuto con le informazioni.</span><span class="sxs-lookup"><span data-stu-id="88f74-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="88f74-107">Se non si vuole inviare il messaggio di posta elettronica, è possibile usare invece **Set-CsClientPin** .</span><span class="sxs-lookup"><span data-stu-id="88f74-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="88f74-108">Puoi usare lo script **Set-CsPinSendCAWelcomeMail** per impostare il PIN e inviare un messaggio di benvenuto a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="88f74-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="88f74-109">Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile usare il parametro **Force** per forzare la reimpostazione di un PIN.</span><span class="sxs-lookup"><span data-stu-id="88f74-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="88f74-110">Il messaggio di posta elettronica viene inviato tramite SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="88f74-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="88f74-111">È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in maniera iterativa per impostare i pin e inviare messaggi di posta elettronica a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="88f74-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="88f74-112">È possibile modificare il modello di posta elettronica, ovvero il file **CAWelcomeEmailTemplate. html** , per aggiungere altri collegamenti alle pagine Intranet o modificare il testo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="88f74-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="88f74-113">Per impostare un PIN iniziale e inviare un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="88f74-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="88f74-114">Accedere come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="88f74-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="88f74-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="88f74-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88f74-116">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="88f74-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="88f74-117">**SmtpServer**   per impostazione predefinita, lo script usa il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="88f74-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="88f74-118">Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="88f74-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="88f74-119">**Credenziali**   per impostazione predefinita, lo script usa le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="88f74-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="88f74-120">Se l'utente corrente non ha l'autorizzazione per inviare messaggi di posta elettronica per conto dell'indirizzo specificato da, devi specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="88f74-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="88f74-121">Come regola generale, specificare questo parametro se non si specifica l'indirizzo di posta elettronica come indirizzo mittente.</span><span class="sxs-lookup"><span data-stu-id="88f74-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="88f74-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88f74-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="88f74-123">In questo esempio viene creato un nuovo PIN e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Roberto.</span><span class="sxs-lookup"><span data-stu-id="88f74-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="88f74-124">Usa il testo della posta elettronica dal modello predefinito e crea il messaggio di posta elettronica in formato HTML.</span><span class="sxs-lookup"><span data-stu-id="88f74-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="88f74-125">L'oggetto predefinito è "Welcome to dial in Conferencing".</span><span class="sxs-lookup"><span data-stu-id="88f74-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="88f74-126">Un altro esempio:</span><span class="sxs-lookup"><span data-stu-id="88f74-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="88f74-127">In questo esempio viene forzato un nuovo PIN con un valore "383042650" per Roberto, anche se Roberto ha un PIN esistente e quindi Invia un messaggio di benvenuto da Marco a Roberto.</span><span class="sxs-lookup"><span data-stu-id="88f74-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="88f74-128">Dato che viene specificato il parametro Credential, viene chiesto di immettere una password per la persona con cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="88f74-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="88f74-129">Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="88f74-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

