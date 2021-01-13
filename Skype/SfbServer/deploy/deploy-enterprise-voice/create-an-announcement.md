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
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Creare o eliminare un annuncio in Skype for Business Server

Creare o eliminare annunci per l'applicazione annuncio in Skype for Business Server VoIP aziendale. Ciò influisce sul modo in cui vengono gestite le chiamate ai numeri non assegnati.

Quando si configurano gli annunci, si specifica in realtà come devono essere gestite le chiamate a numeri non assegnati. È possibile riprodurre un messaggio, che può essere un file audio o un file di sintesi vocale oppure è possibile trasferire semplicemente la chiamata a una destinazione specificata senza riprodurre alcun messaggio.

È necessario creare gli annunci prima di definire la tabella dei numeri non assegnati. È necessario eseguire questa operazione per tutti gli annunci con un messaggio audio o un messaggio di sintesi vocale, oppure senza alcun messaggio.

In questo argomento viene descritto come importare e creare annunci. Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Creare un nuovo annuncio per i numeri non assegnati

Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:

1. Per i messaggi audio, registrare il file audio mediante l'applicazione di registrazione audio preferita.

2. Per i messaggi audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio nell'archivio file.

3. Eseguire il cmdlet **New-CsAnnouncement** per creare l'annuncio e assegnargli un nome. Eseguire questo passaggio per creare annunci con un messaggio audio o un messaggio di sintesi vocale (TTS) oppure senza alcun messaggio.

    > [!TIP]
    > È possibile creare un annuncio senza messaggio, ad esempio se si desidera trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.

4. Assegnare il nuovo annuncio a un intervallo di numeri della tabella di numeri non assegnati.

### <a name="to-create-a-new-announcement"></a>Per creare un nuovo annuncio

1. Per i messaggi audio, creare il file audio.

2. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.

3. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

4. Per i messaggi audio eseguire:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Eseguire: 

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Per trasferire le chiamate alla segreteria telefonica, digitare SIPAddress nel formato sip:nomeutente@nomedominio;opaque=app:voicemail (ad esempio, sip:francesco@contoso.com;opaque=app:voicemail). Per trasferire le chiamate a un numero di telefono, digitare SIPAddress nel formato sip:numero@nomedominio;user=phone (ad esempio, sip:+ 14255550121@contoso.com;user=phone).

    Ad esempio, per specificare un messaggio audio:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Ad esempio, per specificare un messaggio di sintesi vocale:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Per ulteriori informazioni su questi cmdlet e per visualizzare un elenco dei codici di lingua da utilizzare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Eliminare un annuncio per i numeri non assegnati

### <a name="to-delete-an-announcement"></a>Per eliminare un annuncio

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **delegate Setup Permissions**.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

3. Elencare tutti gli annunci disponibili nell'organizzazione. Nella riga di comando digitare il comando seguente:

   ```powershell
   Get-CsAnnouncement
   ```

4. Nell'elenco risultante individuare l'annuncio da eliminare e copiare il GUID, quindi nella riga di comando digitare il comando seguente:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Ad esempio:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Per informazioni dettagliate su altre opzioni, vedere [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) e [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>Vedere anche

[Creare o eliminare un annuncio in Skype for Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

