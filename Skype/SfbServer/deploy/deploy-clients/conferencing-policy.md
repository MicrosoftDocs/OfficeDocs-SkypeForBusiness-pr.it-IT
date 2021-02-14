---
title: Criteri di conferenza per gli account di Skype Room System
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
description: Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di Skype Room System.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812726"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Criteri di conferenza per gli account di Skype Room System
 
Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di Skype Room System.
  
## <a name="conferencing-policy-features"></a>Funzionalità dei criteri di conferenza

Il criterio di conferenza assegnato all'account Skype Room System deve avere determinate caratteristiche. Nella maggior parte dei casi, il client Skype Room System partecipa a una riunione pianificata e pertanto i criteri di conferenza dell'organizzatore della riunione influiranno sulla conferenza. Tuttavia, in Skype for Business Server alcune funzionalità dipendono dalla configurazione del partecipante. Ad esempio, se i criteri del partecipante consentono una risoluzione video massima di 1080p, i partecipanti potranno sperimentare questa funzionalità video con risoluzione superiore nella conferenza anche se i criteri dell'organizzatore non lo consentono. Nella tabella seguente vengono descritte diverse impostazioni di questo tipo di cui è necessario tenere conto durante la configurazione dei criteri di conferenza per gli account skype room system nell'organizzazione. 
  
|Funzionalità  <br/> |Valore  <br/> |Commento  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve essere true per l'audio di Skype Room System  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve essere true per il funzionamento dell'audio di Skype Room System nelle sessioni della lavagna Meet Now (ad hoc) in Skype Room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Consente a Skype Room System di eseguire il rendering di flussi video multipli e multi-visualizzazione  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Dipende se l'account è VoIP aziendale (EV) abilitato (vedere la sezione Abilitazione degli account di Sistema sala Skype per Skype for Business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Dipende se l'account è VoIP aziendale (EV) abilitato  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/D nelle riunioni riunione (ad hoc), ma Skype Room System può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/D nelle riunioni riunione (ad hoc), ma Skype Room System può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/D per Skype Room System. Se TRUE, una parte remota potrebbe registrare  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/D per Skype Room System. Se TRUE, una parte remota potrebbe registrare  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Consente al client Skype Room System di partecipare a sessioni video peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorato da Skype for Business Server, Skype Room System usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Influisce sulle sessioni della lavagna Meet Now (ad hoc) nel sistema skype room  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Questa è la velocità in bit video in uscita massima consentita. Skype Room System può inviare un flusso 1080 insieme al pano (se si usa RoundTable) a questa velocità in bit. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |È consigliabile impostare questo valore il più alto possibile. La larghezza di banda effettiva dipende dalle condizioni di rete al momento delle conferenze.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve essere TRUE per Skype Room System per garantire flussi video multi-visualizzazione  <br/> |
   
* Per informazioni sulla pianificazione della larghezza di banda, vedere [Requisiti di larghezza di banda di rete per il traffico multimediale.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Se il client Skype Room System tenta di partecipare a una riunione pianificata organizzata da un utente che si trova in un pool di Lync Server 2010, i criteri di conferenza dell'organizzatore della riunione potrebbero impedire al client Skype Room System di collaborare. 
  
## <a name="meeting-authentication"></a>Autenticazione riunione

Skype Room System richiede agli utenti l'autenticazione quando usano il collegamento di partecipazione alla riunione per partecipare a una riunione con restrizioni; Ad esempio, una riunione per cui sono state configurate le opzioni della sala di attesa della riunione in Outlook. Questa impostazione è sempre attiva per le riunioni personalizzate e agli utenti viene sempre richiesto. Per le riunioni senza restrizioni, tuttavia, gli utenti possono partecipare alla riunione senza autenticazione. 
  
Il comando seguente consente agli amministratori di richiedere l'autenticazione per tutte le riunioni, incluse le riunioni senza restrizioni: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Per impostazione predefinita, RequireRoomSystemsAuthorization è FALSE. 
  

