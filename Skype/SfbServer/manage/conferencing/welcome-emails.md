---
title: Inviare messaggi di posta elettronica di benvenuto agli utenti con accesso esterno in Skype for Business Server
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
description: 'Riepilogo: informazioni su come accogliere gli utenti nelle conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817496"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="5a350-103">Inviare messaggi di posta elettronica di benvenuto agli utenti con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5a350-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="5a350-104">**Riepilogo:** Informazioni su come accogliere gli utenti nelle conferenze telefoniche con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a350-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="5a350-105">Dopo aver configurato le conferenze telefoniche con accesso esterno e i test per verificare che funzioni correttamente, è necessario impostare i pin (Personal Identification Number) iniziali per gli utenti e informare gli utenti sulla disponibilità della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5a350-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="5a350-106">È possibile includere istruzioni introduttive, ad esempio il PIN iniziale e il collegamento alla pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="5a350-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="5a350-107">In genere, si utilizza il cmdlet **Set-CsClientPin** per reimpostare i pin, ma è possibile utilizzare la procedura descritta in questo argomento se si desidera inviare un messaggio di posta elettronica di benvenuto introduttivo con le informazioni sul pin.</span><span class="sxs-lookup"><span data-stu-id="5a350-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="5a350-108">Se non si desidera inviare tale messaggio, è possibile utilizzare **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="5a350-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="5a350-109">Lo script **Set-CsPinSendCAWelcomeMail** consente di impostare il PIN e inviare un messaggio di benvenuto a un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="5a350-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="5a350-110">Per impostazione predefinita, lo script non reimposta un PIN se è già impostato, ma è possibile utilizzare il parametro Force per forzarne la reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="5a350-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="5a350-111">Il messaggio di posta elettronica viene inviato utilizzando il protocollo SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="5a350-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="5a350-112">È possibile creare uno script che esegua lo script **Set-CsPinSendCAWelcomeMail** in modo iterativo in modo da impostare i PIN e inviare un messaggio di posta elettronica a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="5a350-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="5a350-113">È inoltre possibile modificare il modello di posta elettronica, ovvero il file CAWelcomeEmailTemplate.html, per aggiungere altri collegamenti alle pagine Intranet o per modificare il testo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a350-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="5a350-114">Impostare un PIN iniziale e inviare la posta elettronica di benvenuto</span><span class="sxs-lookup"><span data-stu-id="5a350-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="5a350-115">Accedere come membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5a350-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="5a350-116">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5a350-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5a350-117">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="5a350-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="5a350-118">**SmtpServer** Per impostazione predefinita, lo script utilizza il valore della variabile di ambiente riservata **$PSEmailServer** per questo parametro.</span><span class="sxs-lookup"><span data-stu-id="5a350-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="5a350-119">Se la variabile **$PSEmailServer** non è impostata, è necessario specificare questo parametro.</span><span class="sxs-lookup"><span data-stu-id="5a350-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="5a350-120">**Credenziale** Per impostazione predefinita, lo script utilizza le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="5a350-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="5a350-121">Se tale utente non dispone dell'autorizzazione per inviare un messaggio di posta elettronica con l'indirizzo Da specificato, è necessario immettere questo parametro.</span><span class="sxs-lookup"><span data-stu-id="5a350-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="5a350-122">Come regola generale, il parametro deve essere immesso se non si specifica l'indirizzo di posta elettronica come indirizzo Da.</span><span class="sxs-lookup"><span data-stu-id="5a350-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="5a350-123">Nell'esempio seguente viene creato un nuovo PIN e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="5a350-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="5a350-124">Viene utilizzato il testo del messaggio di posta elettronica del modello predefinito e utilizzato il formato HTML per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5a350-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="5a350-125">L'oggetto predefinito è "Welcome to dial in Conferencing":</span><span class="sxs-lookup"><span data-stu-id="5a350-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="5a350-126">Nell'esempio seguente viene forzato un nuovo PIN con un valore "383042650" per Bob, anche se Bob aveva un PIN esistente e quindi viene inviato un messaggio di posta elettronica di benvenuto da Marco a Bob.</span><span class="sxs-lookup"><span data-stu-id="5a350-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="5a350-127">Poiché il parametro Credential è specificato, all'utente che esegue il comando viene richiesto di immettere una password.</span><span class="sxs-lookup"><span data-stu-id="5a350-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="5a350-128">Il messaggio di posta elettronica viene inviato utilizzando il Secure Sockets Layer (SSL):</span><span class="sxs-lookup"><span data-stu-id="5a350-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
