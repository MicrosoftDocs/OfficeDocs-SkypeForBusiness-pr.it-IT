---
title: Creare o eliminare un annuncio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Creare o eliminare annunci per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.
ms.openlocfilehash: 7cde8c268c66d19e6806a4b6c3e585a7271ef2ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767959"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="f99cd-104">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f99cd-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="f99cd-105">Creare o eliminare annunci per l'applicazione di annunci in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f99cd-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="f99cd-106">Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="f99cd-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="f99cd-107">Quando si configurano gli annunci, si sta realmente configurando come gestire le chiamate a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="f99cd-107">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled.</span></span> <span data-ttu-id="f99cd-108">È possibile riprodurre un prompt, che può essere un file audio o un file di sintesi vocale, oppure semplicemente trasferire la chiamata a una destinazione specificata senza riuscire a eseguire una richiesta.</span><span class="sxs-lookup"><span data-stu-id="f99cd-108">You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="f99cd-109">È necessario creare annunci prima di definire la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="f99cd-109">You need to create announcements before you define the unassigned number table.</span></span> <span data-ttu-id="f99cd-110">È necessario eseguire questo passaggio per tutti gli annunci che usano un prompt audio, un prompt TTS o nessun messaggio.</span><span class="sxs-lookup"><span data-stu-id="f99cd-110">You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="f99cd-111">Questo argomento descrive come importare e creare annunci.</span><span class="sxs-lookup"><span data-stu-id="f99cd-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="f99cd-112">Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [configurare la tabella dei numeri non assegnati](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="f99cd-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="f99cd-113">Creare un nuovo annuncio per i numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="f99cd-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="f99cd-114">Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f99cd-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="f99cd-115">Per le istruzioni audio, registrare il file audio usando l'applicazione di registrazione audio preferita.</span><span class="sxs-lookup"><span data-stu-id="f99cd-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="f99cd-116">Per le istruzioni audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio in archivio file.</span><span class="sxs-lookup"><span data-stu-id="f99cd-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="f99cd-117">Eseguire il cmdlet **New-CsAnnouncement** per creare e assegnare un nome all'annuncio.</span><span class="sxs-lookup"><span data-stu-id="f99cd-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="f99cd-118">Eseguire questo passaggio per creare annunci con un prompt audio, una richiesta di sintesi vocale o nessun messaggio.</span><span class="sxs-lookup"><span data-stu-id="f99cd-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="f99cd-119">Potrebbe essere necessario creare un annuncio senza prompt, ad esempio se si vuole trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f99cd-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="f99cd-120">Assegnare il nuovo annuncio a un intervallo di numeri nella tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="f99cd-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="f99cd-121">Per creare un nuovo annuncio</span><span class="sxs-lookup"><span data-stu-id="f99cd-121">To create a new announcement</span></span>

1. <span data-ttu-id="f99cd-122">Per le istruzioni audio, creare il file audio.</span><span class="sxs-lookup"><span data-stu-id="f99cd-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="f99cd-123">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione delegate**.</span><span class="sxs-lookup"><span data-stu-id="f99cd-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="f99cd-124">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f99cd-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="f99cd-125">Per le istruzioni audio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="f99cd-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="f99cd-126">Eseguire</span><span class="sxs-lookup"><span data-stu-id="f99cd-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="f99cd-127">Per il trasferimento delle chiamate alla segreteria telefonica, digitare SIPAddress nel formato SIP: username@domainname; opaque = app: voicemail, ad esempio SIP: bob@contoso. com; opaque = app: voicemail).</span><span class="sxs-lookup"><span data-stu-id="f99cd-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="f99cd-128">Per trasferire le chiamate a un numero di telefono, digitare SIPAddress nel formato SIP: number@domainname; utente = telefono, ad esempio SIP: + 14255550121@contoso. com; utente = telefono).</span><span class="sxs-lookup"><span data-stu-id="f99cd-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="f99cd-129">Ad esempio, per specificare un prompt audio:</span><span class="sxs-lookup"><span data-stu-id="f99cd-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="f99cd-130">Ad esempio, per specificare un prompt TTS:</span><span class="sxs-lookup"><span data-stu-id="f99cd-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="f99cd-131">Per altri dettagli su questi cmdlet e per visualizzare un elenco dei codici di lingua da usare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f99cd-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="f99cd-132">Eliminare un annuncio per i numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="f99cd-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="f99cd-133">Per eliminare un annuncio</span><span class="sxs-lookup"><span data-stu-id="f99cd-133">To delete an announcement</span></span>

1. <span data-ttu-id="f99cd-134">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione delegate**.</span><span class="sxs-lookup"><span data-stu-id="f99cd-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="f99cd-135">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f99cd-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="f99cd-136">Elencare tutti gli annunci dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f99cd-136">List all the announcements in your organization.</span></span> <span data-ttu-id="f99cd-137">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="f99cd-137">At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="f99cd-138">Nell'elenco risultante individuare l'annuncio che si vuole eliminare e copiare il GUID.</span><span class="sxs-lookup"><span data-stu-id="f99cd-138">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="f99cd-139">Quindi, alla riga di comando, Esegui:</span><span class="sxs-lookup"><span data-stu-id="f99cd-139">Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="f99cd-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f99cd-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="f99cd-141">Per informazioni dettagliate su altre opzioni, vedere [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) e [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f99cd-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="f99cd-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f99cd-142">See also</span></span>

[<span data-ttu-id="f99cd-143">Creare o eliminare un annuncio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f99cd-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="f99cd-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="f99cd-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="f99cd-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="f99cd-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="f99cd-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="f99cd-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="f99cd-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="f99cd-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

