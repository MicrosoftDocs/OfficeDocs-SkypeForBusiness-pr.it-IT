---
title: Visualizzare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Riepilogo: informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992191"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Visualizzare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.
  
Puoi visualizzare i criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Visualizzare i criteri di conferenza tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
4. Nella pagina **criteri di conferenza** fare doppio clic sui criteri di conferenza che si desidera visualizzare.
    
5. In **Modifica filtro file**selezionare la casella di controllo **Mostra dettagli** .
    
    **Modificare i criteri di \<conferenza\> :** viene visualizzata la visualizzazione delle impostazioni per il criterio selezionato.
    
    Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare criteri di conferenza in Skype for Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Visualizzare i criteri di conferenza tramite Skype for Business Server Management Shell

Per visualizzare i criteri di conferenza, usare il cmdlet **Get-CsConferencingPolicy** :
  
```PowerShell
Get-CsConferencingPolicy
```

Il cmdlet restituisce informazioni come le seguenti:
  
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

Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

