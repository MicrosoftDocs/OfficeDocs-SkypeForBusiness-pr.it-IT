---
title: Criteri di conferenza per Skype di sistema room
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leggere questo argomento per informazioni su come assegnare criteri di conferenza per Skype di sistema room.
ms.openlocfilehash: 202440953aedaa54ac69a7bd4549bf7dcbd8d865
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618202"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Criteri di conferenza per Skype di sistema room
 
Leggere questo argomento per informazioni su come assegnare criteri di conferenza per Skype di sistema room.
  
## <a name="conferencing-policy-features"></a>Funzionalità dei criteri di conferenza

Il criterio di conferenza assegnato all'account Skype Room System deve avere determinate caratteristiche. Nella maggior parte dei casi, il client Skype Room System partecipa a una riunione pianificata e pertanto i criteri di conferenza dell'organizzatore della riunione influiranno sulla conferenza. Tuttavia, in Skype for Business Server alcune funzionalità dipendono dalla configurazione del partecipante. Ad esempio, se i criteri del partecipante consentono una risoluzione video massima di 1080p, i partecipanti sperimenteranno questa funzionalità video con risoluzione superiore nella conferenza anche se i criteri dell'organizzatore non lo consentono. Nella tabella seguente vengono descritte diverse impostazioni di questo tipo che è necessario tenere presenti quando si impostano i criteri di conferenza per gli account di Skype Room System nell'organizzazione. 
  
|Funzionalità  <br/> |Valore  <br/> |Aggiungere commenti  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve essere true per l'audio Skype Room System  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve essere true perché Skype audio del sistema room funzioni nelle sessioni della lavagna Riunione ora (ad hoc) in Skype Room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Consente Skype Room System di eseguire il rendering di flussi video multipli e multi-visualizzazione  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Dipende dal fatto che l'account sia abilitato VoIP aziendale (EV) (vedere la sezione Abilitazione degli account di sistema Skype room per Skype for Business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Dipende se l'account è VoIP aziendale (EV) abilitato  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/D nelle riunioni riunione ora (ad hoc), ma Skype Room System può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/D nelle riunioni riunione ora (ad hoc), ma Skype Room System può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/D per Skype Room System. Se TRUE, una parte remota potrebbe registrare  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/D per Skype Room System. Se TRUE, una parte remota potrebbe registrare  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Consente al client Skype Room System di partecipare a sessioni video peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorato da Skype for Business Server, Skype Room System usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Influisce sulle sessioni della lavagna meet now (ad hoc) in Skype Room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Vedere nota alla fine della tabella\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Questa è la velocità in bit video in uscita massima consentita. Skype Room System può inviare un flusso 1080 insieme a pano (se viene utilizzato RoundTable) a questa velocità in bit. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Vedere nota alla fine della tabella\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |È consigliabile impostare questo valore il più alto possibile. La larghezza di banda effettiva dipende dalle condizioni di rete al momento delle conferenze.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve essere TRUE per Skype Room System per garantire flussi video multi-visualizzazione  <br/> |
   
* Per informazioni sulla pianificazione della larghezza di banda, vedere [Requisiti di larghezza di banda di rete per il traffico multimediale.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Se il client Skype Room System tenta di partecipare a una riunione pianificata organizzata da un utente che si trova in un pool di Lync Server 2010, i criteri di conferenza dell'organizzatore della riunione potrebbero impedire al client di sistema sala di Skype di eseguire la collaborazione. 
  
## <a name="meeting-authentication"></a>Autenticazione riunione

Skype Il sistema sala richiede agli utenti l'autenticazione quando utilizzano il collegamento per partecipare a una riunione con restrizioni; ad esempio, una riunione per la quale sono state configurate le opzioni di sala di attesa della riunione in Outlook. Questa impostazione è sempre attiva per le riunioni personalizzate e agli utenti viene sempre richiesto. Tuttavia, per le riunioni senza restrizioni, gli utenti possono partecipare alla riunione senza autenticazione. 
  
Il comando seguente consente agli amministratori di richiedere l'autenticazione per tutte le riunioni, incluse le riunioni senza restrizioni: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Per impostazione predefinita, RequireRoomSystemsAuthorization è FALSE. 
  

