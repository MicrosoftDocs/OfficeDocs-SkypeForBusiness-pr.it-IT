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
ms.openlocfilehash: d9f0740128a8790052534e63c95a8305f65bb96d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992833"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="aecd9-103">Inviare la posta elettronica di benvenuto agli utenti con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="aecd9-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="aecd9-104">**Riepilogo:** Informazioni su come accogliere gli utenti in servizi di conferenza telefonica con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aecd9-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="aecd9-105">Dopo aver configurato i servizi di conferenza telefonica con accesso esterno e i test per verificare che funzioni correttamente, è necessario impostare i pin (Personal Identification Number) iniziali per gli utenti e comunicare agli utenti la disponibilità della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aecd9-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="aecd9-106">È possibile includere istruzioni introduttive, ad esempio il PIN iniziale e il collegamento alla pagina Web delle impostazioni di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="aecd9-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="aecd9-107">In genere, si usa il cmdlet **Set-CsClientPin** per reimpostare i pin, ma è possibile usare la procedura descritta in questo argomento se si vuole inviare un messaggio di benvenuto introduttivo con le informazioni sul pin.</span><span class="sxs-lookup"><span data-stu-id="aecd9-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="aecd9-108">Se non si vuole inviare il messaggio di posta elettronica, è possibile usare invece **Set-CsClientPin** .</span><span class="sxs-lookup"><span data-stu-id="aecd9-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="aecd9-109">Puoi usare lo script **Set-CsPinSendCAWelcomeMail** per impostare il PIN e inviare un messaggio di benvenuto a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="aecd9-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="aecd9-110">Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile usare il parametro Force per forzare la reimpostazione di un PIN.</span><span class="sxs-lookup"><span data-stu-id="aecd9-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="aecd9-111">Il messaggio di posta elettronica viene inviato tramite SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="aecd9-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="aecd9-112">È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in maniera iterativa per impostare i pin e inviare messaggi di posta elettronica a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="aecd9-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="aecd9-113">È possibile modificare il modello di posta elettronica, ovvero il file CAWelcomeEmailTemplate. html, per aggiungere altri collegamenti alle pagine Intranet o modificare il testo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aecd9-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="aecd9-114">Impostare un PIN iniziale e inviare un messaggio di benvenuto</span><span class="sxs-lookup"><span data-stu-id="aecd9-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="aecd9-115">Accedere come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aecd9-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="aecd9-116">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="aecd9-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="aecd9-117">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="aecd9-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="aecd9-118">**SmtpServer** Per impostazione predefinita, lo script usa il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="aecd9-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="aecd9-119">Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="aecd9-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="aecd9-120">**Credenziali** Per impostazione predefinita, lo script usa le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="aecd9-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="aecd9-121">Se l'utente corrente non ha l'autorizzazione per inviare messaggi di posta elettronica per conto dell'indirizzo specificato da, devi specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="aecd9-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="aecd9-122">Come regola generale, specificare questo parametro se non si specifica l'indirizzo di posta elettronica come indirizzo mittente.</span><span class="sxs-lookup"><span data-stu-id="aecd9-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="aecd9-123">Nell'esempio seguente viene creato un nuovo PIN e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Roberto.</span><span class="sxs-lookup"><span data-stu-id="aecd9-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="aecd9-124">Usa il testo della posta elettronica dal modello predefinito e crea il messaggio di posta elettronica in formato HTML.</span><span class="sxs-lookup"><span data-stu-id="aecd9-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="aecd9-125">L'oggetto predefinito è "Welcome to dial in conferenza":</span><span class="sxs-lookup"><span data-stu-id="aecd9-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="aecd9-126">Nell'esempio successivo viene forzato un nuovo PIN con un valore "383042650" per Roberto, anche se Roberto ha un PIN esistente e quindi Invia un messaggio di benvenuto da Marco a Roberto.</span><span class="sxs-lookup"><span data-stu-id="aecd9-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="aecd9-127">Dato che viene specificato il parametro Credential, viene chiesto di immettere una password per la persona con cui viene eseguito il comando.</span><span class="sxs-lookup"><span data-stu-id="aecd9-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="aecd9-128">Il messaggio di posta elettronica viene inviato tramite SSL (Secure Sockets Layer):</span><span class="sxs-lookup"><span data-stu-id="aecd9-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
