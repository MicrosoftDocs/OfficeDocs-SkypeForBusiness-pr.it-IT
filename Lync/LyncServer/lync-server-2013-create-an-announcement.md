---
title: 'Lync Server 2013: creare un annuncio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="2cda6-102">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cda6-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cda6-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2cda6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2cda6-104">Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2cda6-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="2cda6-105">Per le istruzioni audio, registrare il file audio usando l'applicazione di registrazione audio preferita.</span><span class="sxs-lookup"><span data-stu-id="2cda6-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="2cda6-106">Per le istruzioni audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio in archivio file.</span><span class="sxs-lookup"><span data-stu-id="2cda6-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="2cda6-107">Eseguire il cmdlet **New-CsAnnouncement** per creare e assegnare un nome all'annuncio.</span><span class="sxs-lookup"><span data-stu-id="2cda6-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="2cda6-108">Eseguire questo passaggio per creare annunci con un prompt audio, una richiesta di sintesi vocale o nessun messaggio.</span><span class="sxs-lookup"><span data-stu-id="2cda6-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2cda6-109">Potrebbe essere necessario creare un annuncio senza prompt, ad esempio se si vuole trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2cda6-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="2cda6-110">Assegnare il nuovo annuncio a un intervallo di numeri nella tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="2cda6-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="2cda6-111">Questo argomento descrive come importare e creare annunci.</span><span class="sxs-lookup"><span data-stu-id="2cda6-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="2cda6-112">Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [configurare la tabella dei numeri non assegnati in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="2cda6-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="2cda6-113">Per creare un nuovo annuncio</span><span class="sxs-lookup"><span data-stu-id="2cda6-113">To create a new announcement</span></span>

1.  <span data-ttu-id="2cda6-114">Per le istruzioni audio, creare il file audio.</span><span class="sxs-lookup"><span data-stu-id="2cda6-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="2cda6-115">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2cda6-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="2cda6-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2cda6-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="2cda6-117">Per le istruzioni audio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2cda6-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="2cda6-118">Eseguire</span><span class="sxs-lookup"><span data-stu-id="2cda6-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="2cda6-119">Per il trasferimento delle chiamate alla segreteria telefonica, digitare SIPAddress nel formato SIP: username@domainname; opaque = app: voicemail, ad esempio SIP: bob@contoso. com; opaque = app: voicemail).</span><span class="sxs-lookup"><span data-stu-id="2cda6-119">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="2cda6-120">Per trasferire le chiamate a un numero di telefono, digitare SIPAddress nel formato SIP: number@domainname; utente = telefono, ad esempio SIP: + 14255550121@contoso. com; utente = telefono).</span><span class="sxs-lookup"><span data-stu-id="2cda6-120">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="2cda6-121">Ad esempio, per specificare un prompt audio:</span><span class="sxs-lookup"><span data-stu-id="2cda6-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="2cda6-122">Ad esempio, per specificare un prompt TTS:</span><span class="sxs-lookup"><span data-stu-id="2cda6-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="2cda6-123">Per altri dettagli su questi cmdlet e per visualizzare un elenco dei codici di lingua da usare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="2cda6-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cda6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cda6-124">See Also</span></span>


[<span data-ttu-id="2cda6-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="2cda6-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="2cda6-126">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="2cda6-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="2cda6-127">Configurare la tabella dei numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cda6-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

