---
title: Visualizzare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Riepilogo: informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817506"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Visualizzare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.
  
È possibile visualizzare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Visualizzare i criteri di conferenza tramite il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**
    
4. Nella pagina **Criteri conferenza** fare doppio clic sul criterio di conferenza che si desidera visualizzare.
    
5. In **Modifica filtro file** selezionare la casella di **controllo** Mostra dettagli.
    
    **Modifica criteri \<policy\> conferenza -** visualizza le impostazioni per il criterio selezionato.
    
    Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [Creare criteri di conferenza in Skype for Business Server.](create-policies.md)
    
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

Per ulteriori informazioni, inclusa una descrizione della sintassi completa e un elenco di parametri, vedere [Get-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)
  

