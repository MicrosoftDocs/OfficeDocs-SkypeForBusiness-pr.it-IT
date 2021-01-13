---
title: Creare o eliminare un annuncio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Creare o eliminare annunci per l'applicazione annuncio in Skype for Business Server VoIP aziendale. Ciò influisce sul modo in cui vengono gestite le chiamate ai numeri non assegnati.
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824906"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="ce8b6-104">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce8b6-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="ce8b6-105">Creare o eliminare annunci per l'applicazione annuncio in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="ce8b6-106">Ciò influisce sul modo in cui vengono gestite le chiamate ai numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="ce8b6-p103">Quando si configurano gli annunci, si specifica in realtà come devono essere gestite le chiamate a numeri non assegnati. È possibile riprodurre un messaggio, che può essere un file audio o un file di sintesi vocale oppure è possibile trasferire semplicemente la chiamata a una destinazione specificata senza riprodurre alcun messaggio.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="ce8b6-p104">È necessario creare gli annunci prima di definire la tabella dei numeri non assegnati. È necessario eseguire questa operazione per tutti gli annunci con un messaggio audio o un messaggio di sintesi vocale, oppure senza alcun messaggio.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="ce8b6-111">In questo argomento viene descritto come importare e creare annunci.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="ce8b6-112">Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce8b6-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="ce8b6-113">Creare un nuovo annuncio per i numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="ce8b6-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="ce8b6-114">Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="ce8b6-115">Per i messaggi audio, registrare il file audio mediante l'applicazione di registrazione audio preferita.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="ce8b6-116">Per i messaggi audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="ce8b6-117">Eseguire il cmdlet **New-CsAnnouncement** per creare l'annuncio e assegnargli un nome.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="ce8b6-118">Eseguire questo passaggio per creare annunci con un messaggio audio o un messaggio di sintesi vocale (TTS) oppure senza alcun messaggio.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="ce8b6-119">È possibile creare un annuncio senza messaggio, ad esempio se si desidera trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="ce8b6-120">Assegnare il nuovo annuncio a un intervallo di numeri della tabella di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="ce8b6-121">Per creare un nuovo annuncio</span><span class="sxs-lookup"><span data-stu-id="ce8b6-121">To create a new announcement</span></span>

1. <span data-ttu-id="ce8b6-122">Per i messaggi audio, creare il file audio.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="ce8b6-123">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="ce8b6-124">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="ce8b6-125">Per i messaggi audio eseguire:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="ce8b6-126">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="ce8b6-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="ce8b6-p107">Per trasferire le chiamate alla segreteria telefonica, digitare SIPAddress nel formato sip:nomeutente@nomedominio;opaque=app:voicemail (ad esempio, sip:francesco@contoso.com;opaque=app:voicemail). Per trasferire le chiamate a un numero di telefono, digitare SIPAddress nel formato sip:numero@nomedominio;user=phone (ad esempio, sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="ce8b6-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="ce8b6-129">Ad esempio, per specificare un messaggio audio:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="ce8b6-130">Ad esempio, per specificare un messaggio di sintesi vocale:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="ce8b6-131">Per ulteriori informazioni su questi cmdlet e per visualizzare un elenco dei codici di lingua da utilizzare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ce8b6-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="ce8b6-132">Eliminare un annuncio per i numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="ce8b6-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="ce8b6-133">Per eliminare un annuncio</span><span class="sxs-lookup"><span data-stu-id="ce8b6-133">To delete an announcement</span></span>

1. <span data-ttu-id="ce8b6-134">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="ce8b6-135">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ce8b6-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="ce8b6-p108">Elencare tutti gli annunci disponibili nell'organizzazione. Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="ce8b6-p109">Nell'elenco risultante individuare l'annuncio da eliminare e copiare il GUID, quindi nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="ce8b6-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ce8b6-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="ce8b6-141">Per informazioni dettagliate su altre opzioni, vedere [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) e [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ce8b6-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce8b6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce8b6-142">See also</span></span>

[<span data-ttu-id="ce8b6-143">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce8b6-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="ce8b6-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="ce8b6-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="ce8b6-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="ce8b6-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="ce8b6-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="ce8b6-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="ce8b6-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="ce8b6-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

