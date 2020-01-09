---
title: Gestire gli annunci di conferenza e lasciarli in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Riepilogo: informazioni su come gestire gli annunci di conferenza e uscire da Skype for Business Server.'
ms.openlocfilehash: 5c2bc7175f99ee50e94bee26ef0e6d54a6a8db5a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991831"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gestire gli annunci di conferenza e lasciarli in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire gli annunci in Skype for Business Server e partecipare a una conferenza.
  
Quando gli utenti con accesso esterno entrano o lasciano una conferenza, l'applicazione di annunci per conferenze può annunciare l'entrata o l'uscita suonando un tono o pronunciando i loro nomi. È possibile modificare la modalità di funzionamento degli annunci usando Skype for Business Server Management Shell e il cmdlet **set-CsDialinConferencing** con i parametri seguenti:
  
- EnableNameRecording-Determina se i partecipanti anonimi vengono invitati a registrare il nome prima di partecipare alla conferenza. Il valore predefinito è "$true", che indica che ai partecipanti anonimi viene richiesto di indicare il loro nome quando partecipano a una conferenza. I partecipanti autenticati non registrano il proprio nome perché viene usato il nome visualizzato.
    
- EntryExitAnnouncementsEnabledByDefault: indica se gli annunci sono attivati o disattivati per impostazione predefinita. Il valore predefinito è "$false", che indica che per impostazione predefinita non ci sono annunci quando i partecipanti partecipano o lasciano una conferenza. L'organizzatore della riunione può eseguire l'override di questa impostazione durante la pianificazione di una riunione.
    
- EntryExitAnnouncementsType-indica l'azione eseguita ogni volta che un partecipante partecipa o esce da una conferenza per cui sono abilitati gli annunci. Il valore predefinito è "UseNames", che indica che è presente un annuncio simile al seguente: "Ken si è unito alla conferenza" quando gli annunci sono attivati.
    
Queste impostazioni possono essere configurate nell'ambito globale o nell'ambito del sito. Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Per modificare il comportamento dell'annuncio per la conferenza e il permesso

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire la procedura seguente al prompt dei comandi:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Questo cmdlet recupera informazioni sul fatto che i partecipanti siano tenuti a registrare il loro nome quando partecipano a una conferenza e in che modo Skype for Business Server risponde quando i partecipanti partecipano o lasciano una conferenza telefonica con accesso esterno.
    
4. Eseguire la procedura seguente al prompt dei comandi:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Nell'esempio seguente le impostazioni sono configurate nell'ambito del sito per Redmond. Gli annunci sono attivati, ma ai partecipanti non viene chiesto di pronunciare il loro nome quando partecipano a una conferenza. Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Per altre informazioni, tra cui la sintassi e un elenco completo dei parametri, vedere [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

