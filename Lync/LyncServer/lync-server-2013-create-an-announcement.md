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

# <a name="create-an-announcement-in-lync-server-2013"></a>Creare un annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:

1.  Per le istruzioni audio, registrare il file audio usando l'applicazione di registrazione audio preferita.

2.  Per le istruzioni audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio in archivio file.

3.  Eseguire il cmdlet **New-CsAnnouncement** per creare e assegnare un nome all'annuncio. Eseguire questo passaggio per creare annunci con un prompt audio, una richiesta di sintesi vocale o nessun messaggio.
    
    <div>
    

    > [!TIP]  
    > Potrebbe essere necessario creare un annuncio senza prompt, ad esempio se si vuole trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.

    
    </div>

4.  Assegnare il nuovo annuncio a un intervallo di numeri nella tabella dei numeri non assegnati.

Questo argomento descrive come importare e creare annunci. Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [configurare la tabella dei numeri non assegnati in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>Per creare un nuovo annuncio

1.  Per le istruzioni audio, creare il file audio.

2.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

4.  Per le istruzioni audio, eseguire:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Eseguire
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Per il trasferimento delle chiamate alla segreteria telefonica, digitare SIPAddress nel formato SIP: username@domainname; opaque = app: voicemail, ad esempio SIP: bob@contoso. com; opaque = app: voicemail). Per trasferire le chiamate a un numero di telefono, digitare SIPAddress nel formato SIP: number@domainname; utente = telefono, ad esempio SIP: + 14255550121@contoso. com; utente = telefono).
    
    Ad esempio, per specificare un prompt audio:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Ad esempio, per specificare un prompt TTS:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Per altri dettagli su questi cmdlet e per visualizzare un elenco dei codici di lingua da usare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Configurare la tabella dei numeri non assegnati in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

