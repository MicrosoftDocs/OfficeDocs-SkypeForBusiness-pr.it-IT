---
title: Criteri di conferenza per gli account di sistema per Skype room
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di sistema di Skype room.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812726"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Criteri di conferenza per gli account di sistema per Skype room
 
Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di sistema di Skype room.
  
## <a name="conferencing-policy-features"></a>Funzionalità per i criteri di conferenza

I criteri di conferenza assegnati all'account di sistema della sala Skype devono avere determinate caratteristiche. La maggior parte delle volte, il client del sistema Skype room si unisce a una riunione pianificata e pertanto i criteri di conferenza dell'organizzatore della riunione influiranno sulla conferenza. Tuttavia, in Skype for Business Server, alcune funzionalità dipendono dalla configurazione del partecipante. Ad esempio, se i criteri del partecipante consentono una risoluzione video massima di 1080p, i partecipanti sperimenteranno questa funzionalità video a risoluzione più elevata nella conferenza anche se i criteri dell'organizzatore non lo consentono. Nella tabella seguente vengono descritte diverse impostazioni che è necessario tenere presenti quando si configurano i criteri di conferenza per gli account di sistema di Skype room nell'organizzazione. 
  
|Funzionalità  <br/> |Valore  <br/> |Aggiungere commenti  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve essere true per l'audio del sistema chat room Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve essere impostato su true per l'audio del sistema Skype room per l'utilizzo delle sessioni di lavagna (ad hoc) del sistema di chat in Skype room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Consente a Skype room System di eseguire il rendering di più flussi video in più visualizzazioni  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Varia a seconda che l'account sia abilitato per VoIP aziendale (vedere la sezione Abilitazione degli account di sistema di Skype room System per Skype for business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Varia a seconda che l'account sia abilitato per VoIP aziendale  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/d nelle riunioni di Meet Now (ad hoc), ma il sistema in sala Skype può rispondere ai sondaggi sullo schermo nella parte anteriore della chat room  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/d nelle riunioni di Meet Now (ad hoc), ma il sistema in sala Skype può rispondere ai sondaggi sullo schermo nella parte anteriore della chat room  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A per Skype room System. Se è impostato su TRUE, una parte remota potrebbe registrare  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A per Skype room System. Se è impostato su TRUE, una parte remota potrebbe registrare  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Consente al client del sistema Skype room di partecipare a sessioni video peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorato da Skype for Business Server, Skype room System utilizza HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Influisce sulle sessioni della lavagna (ad hoc) in Skype room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Questa è la frequenza di bit video in uscita massima consentita. Skype room System può inviare 1 1080 Stream insieme a Pano (se viene utilizzata la tavola rotonda) a questo bit rate. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |È consigliabile impostare il livello massimo possibile. La larghezza di banda effettiva dipende dalle condizioni di rete al momento delle conferenze.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve essere vero per Skype room System per garantire flussi video multi-view  <br/> |
   
* Per informazioni sulla pianificazione della larghezza di banda, vedere [requisiti della larghezza di banda di rete per il traffico multimediale](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Se il client del sistema Skype room tenta di partecipare a una riunione pianificata organizzata da un utente ospitato in un pool di Lync Server 2010, i criteri di conferenza dell'organizzatore della riunione potrebbero impedire al client del sistema di chat room Skype di eseguire la collaborazione. 
  
## <a name="meeting-authentication"></a>Autenticazione riunione

Skype room System richiede agli utenti di eseguire l'autenticazione quando utilizzano il collegamento di partecipazione alle riunioni per partecipare a una riunione limitata; ad esempio, una riunione per la quale sono state configurate le opzioni della lobby delle riunioni in Outlook. Questa impostazione è sempre attiva per le riunioni personalizzate e gli utenti vengono sempre richiesti. Tuttavia, per le riunioni non limitate, gli utenti possono partecipare alla riunione senza l'autenticazione. 
  
Il comando seguente consente agli amministratori di richiedere l'autenticazione per tutte le riunioni, incluse le riunioni senza restrizioni: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Per impostazione predefinita, RequireRoomSystemsAuthorization è impostato su FALSE. 
  

