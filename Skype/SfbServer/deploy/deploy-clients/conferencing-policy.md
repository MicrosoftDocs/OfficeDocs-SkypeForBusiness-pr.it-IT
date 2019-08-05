---
title: Criteri di conferenza per gli account di sistema per Skype room
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di sistema di chat room Skype.
ms.openlocfilehash: 5662778c14d8f987e26b36eaca252fbd8a6ea98c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190478"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Criteri di conferenza per gli account di sistema per Skype room
 
Leggere questo argomento per informazioni su come assegnare criteri di conferenza per gli account di sistema di chat room Skype.
  
## <a name="conferencing-policy-features"></a>Caratteristiche dei criteri di conferenza

I criteri di conferenza assegnati all'account di sistema room Skype devono avere determinate caratteristiche. La maggior parte del tempo, il client di sistema room Skype si unisce a una riunione pianificata e quindi i criteri di conferenza dell'organizzatore della riunione influiranno sulla conferenza. Tuttavia, in Skype for Business Server, alcune funzionalità dipendono dalla configurazione del partecipante. Ad esempio, se i criteri del partecipante permettono una risoluzione video massima di 1080p, i partecipanti sperimenteranno questa funzionalità video con risoluzione superiore nella conferenza, anche se il criterio dell'organizzatore non lo consente. La tabella seguente descrive alcune di queste impostazioni che è necessario tenere presenti quando si configurano i criteri di conferenza per gli account di sistema room Skype nell'organizzazione. 
  
|Funzionalità  <br/> |Valore  <br/> |Commento  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Deve essere vero per l'audio del sistema room Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Deve essere vero per l'audio di Skype room System per il lavoro in sessioni di lavagna (ad hoc) in Skype room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Consente al sistema room Skype di eseguire il rendering di più flussi video in visualizzazione multipla  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Dipende dal fatto che l'account sia Enterprise Voice (EV) Enabled (Vedi la sezione Abilitazione degli account di Skype room System per Skype for business)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Dipende dal fatto che l'account è abilitato per VoIP aziendale (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/d in riunioni ora (ad hoc), ma il sistema in camera Skype può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/d in riunioni ora (ad hoc), ma il sistema in camera Skype può rispondere ai sondaggi sullo schermo nella parte anteriore della sala  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/d per Skype room System. Se TRUE, una parte remota può registrare  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/d per Skype room System. Se TRUE, una parte remota può registrare  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |N/D  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Consente al client di Skype room System di partecipare alle sessioni video peer-to-peer  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |N/D  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Ignorato da Skype for Business Server, Skype room System usa HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Influenza le sessioni di riunione di lavagna (ad hoc) in Skype room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Questa è la velocità in bit del video in uscita massima consentita. Skype room System può inviare 1 1080 Stream insieme a Pano (se si usa la tavola rotonda) a questo bit rate. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Vedere la nota alla fine della tabella\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/D  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Ti consigliamo di impostare il più in alto possibile. La larghezza di banda effettiva dipende dalle condizioni di rete in occasione delle conferenze.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Deve essere vero per Skype room System per garantire flussi video con visualizzazione multipla  <br/> |
   
* Per informazioni sulla pianificazione della larghezza di banda, vedere [requisiti di larghezza di banda della rete per il traffico multimediale](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Se il client della sala di Skype room cerca di partecipare a una riunione pianificata organizzata da un utente che si trova in un pool di Lync Server 2010, i criteri di conferenza dell'organizzatore della riunione potrebbero impedire al client del sistema Skype room di eseguire la collaborazione. 
  
## <a name="meeting-authentication"></a>Autenticazione della riunione

Skype room System chiede agli utenti di eseguire l'autenticazione quando usano il collegamento alla riunione per partecipare a una riunione con restrizioni; ad esempio, una riunione per cui sono state configurate le opzioni della sala riunioni in Outlook. Questa impostazione è sempre attiva per le riunioni personalizzate e gli utenti vengono sempre richiesti. Tuttavia, per le riunioni senza restrizioni, gli utenti possono partecipare alla riunione con l'autenticazione. 
  
Il comando seguente consente agli amministratori di richiedere l'autenticazione per tutte le riunioni, incluse le riunioni senza restrizioni: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Per impostazione predefinita, RequireRoomSystemsAuthorization è FALSE. 
  

