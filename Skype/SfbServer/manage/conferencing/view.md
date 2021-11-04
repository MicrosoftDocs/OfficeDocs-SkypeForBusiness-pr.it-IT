---
title: Visualizzare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Riepilogo: informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: cb401abbf6fec1a280099ca30c570338d419c55e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762474"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Visualizzare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.
  
È possibile visualizzare i criteri di conferenza Skype for Business Server pannello di controllo o tramite Skype for Business Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Visualizzare i criteri di conferenza tramite Skype for Business Server Pannello di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Criteri conferenza.**
    
4. Nella pagina **Criteri conferenza** fare doppio clic sul criterio di conferenza che si desidera visualizzare.
    
5. In **Modifica filtro file** selezionare la casella di **controllo** Mostra dettagli.
    
    **Modifica criteri \<policy\> conferenza -** visualizza le impostazioni per il criterio selezionato.
    
    Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [Create conferencing policies in Skype for Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Visualizzare i criteri di conferenza tramite Skype for Business Server Management Shell

Per visualizzare i criteri conferenza, utilizzare il cmdlet **Get-CsConferencingPolicy:**
  
```PowerShell
Get-CsConferencingPolicy
```

Il cmdlet restituisce informazioni quali le seguenti:
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
