---
title: Gestire gli annunci di partecipazione alla conferenza in Skype for Business Server
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Riepilogo: informazioni su come gestire gli annunci di partecipazione alle conferenze e per lasciare messaggi in Skype for Business Server.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828106"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gestire gli annunci di partecipazione alla conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire gli annunci per la partecipazione alle conferenze e per lasciare messaggi in Skype for Business Server.
  
Quando gli utenti con accesso esterno si uniscono o lasciano una conferenza, l'applicazione annuncio per le conferenze può annunciare la propria entrata o uscita suonando un tono o pronunciando i propri nomi. È possibile modificare il modo in cui gli annunci funzionano utilizzando Skype for Business Server Management Shell e il cmdlet **set-CsDialinConferencing** con i seguenti parametri:
  
- EnableNameRecording-Determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza. Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.
    
- EntryExitAnnouncementsEnabledByDefault-indica se gli annunci sono attivati o disattivati per impostazione predefinita. Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano. L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.
    
- EntryExitAnnouncementsType-indica l'azione intrapresa ogni volta che un partecipante si unisce o lascia una conferenza per la quale gli annunci sono abilitati. Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.
    
È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
3. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Questo cmdlet recupera le informazioni sul fatto che i partecipanti siano tenuti a registrare il proprio nome quando partecipano a una conferenza e in che modo Skype for Business Server risponde quando i partecipanti si uniscono o lasciano una conferenza telefonica con accesso esterno.
    
4. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Nell'esempio seguente, le impostazioni vengono configurate nell'ambito del sito per Redmond. Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. Viene riprodotto un tono quando i partecipanti entrano o lasciano una conferenza:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Per ulteriori informazioni, tra cui la sintassi e l'elenco completo dei parametri, vedere [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

