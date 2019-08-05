---
title: Creare o eliminare un annuncio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Creare o eliminare annunci per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.
ms.openlocfilehash: 6160631473a2ead839346e53f9f63294a7959289
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191351"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Creare o eliminare un annuncio in Skype for Business Server

Creare o eliminare annunci per l'applicazione di annunci in Skype for Business Server VoIP aziendale. Ciò influenza il modo in cui vengono gestite le chiamate a numeri non assegnati.

Quando si configurano gli annunci, si sta realmente configurando come gestire le chiamate a numeri non assegnati. È possibile riprodurre un prompt, che può essere un file audio o un file di sintesi vocale, oppure semplicemente trasferire la chiamata a una destinazione specificata senza riuscire a eseguire una richiesta.

È necessario creare annunci prima di definire la tabella dei numeri non assegnati. È necessario eseguire questo passaggio per tutti gli annunci che usano un prompt audio, un prompt TTS o nessun messaggio.

Questo argomento descrive come importare e creare annunci. Per informazioni dettagliate sull'assegnazione di annunci nella tabella dei numeri non assegnati, vedere [configurare la tabella dei numeri non assegnati](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Creare un nuovo annuncio per i numeri non assegnati

Per creare un nuovo annuncio, è necessario eseguire la procedura seguente:

1. Per le istruzioni audio, registrare il file audio usando l'applicazione di registrazione audio preferita.

2. Per le istruzioni audio, eseguire il cmdlet **Import-CsAnnouncementFile** per importare il contenuto del file audio in archivio file.

3. Eseguire il cmdlet **New-CsAnnouncement** per creare e assegnare un nome all'annuncio. Eseguire questo passaggio per creare annunci con un prompt audio, una richiesta di sintesi vocale o nessun messaggio.

    > [!TIP]
    > Potrebbe essere necessario creare un annuncio senza prompt, ad esempio se si vuole trasferire le chiamate a una destinazione specifica senza riprodurre un messaggio.

4. Assegnare il nuovo annuncio a un intervallo di numeri nella tabella dei numeri non assegnati.

### <a name="to-create-a-new-announcement"></a>Per creare un nuovo annuncio

1. Per le istruzioni audio, creare il file audio.

2. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.

3. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

4. Per le istruzioni audio, eseguire:

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Eseguire

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Per il trasferimento delle chiamate alla segreteria telefonica, digitare SIPAddress nel formato SIP: nomeutente @ nomedominio; opaque = app: voicemail (ad esempio, SIP: bob@contoso.com; opaque = app: voicemail). Per il trasferimento di chiamate a un numero di telefono, digitare SIPAddress nel formato SIP: Number @ NomeDominio; utente = telefono, ad esempio SIP: + 14255550121@contoso.com; utente = telefono.

    Ad esempio, per specificare un prompt audio:

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Ad esempio, per specificare un prompt TTS:

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Per altri dettagli su questi cmdlet e per visualizzare un elenco dei codici di lingua da usare nel parametro **TextToSpeechPrompt** , vedere [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Eliminare un annuncio per i numeri non assegnati

### <a name="to-delete-an-announcement"></a>Per eliminare un annuncio

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.

2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

3. Elencare tutti gli annunci dell'organizzazione. Nella riga di comando eseguire:

   ```
   Get-CsAnnouncement
   ```

4. Nell'elenco risultante individuare l'annuncio che si vuole eliminare e copiare il GUID. Quindi, alla riga di comando, Esegui:

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Ad esempio:

   ```
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

