---
title: Gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Riepilogo: informazioni su come gestire gli annunci di partecipazione e di lasciare conferenze Skype for Business Server.'
ms.openlocfilehash: f2219fc8d55485a4c34a8730fbec6b556d57b728
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625208"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire gli annunci di partecipazione e di lasciare conferenze in Skype for Business Server.
  
Quando gli utenti con accesso remoto aderiscono o escono da una conferenza, il applicazione Annuncio conferenza può annunciare l'ingresso o l'uscita riproducendo un tono o pronunciando i propri nomi. È possibile modificare il funzionamento degli annunci utilizzando Skype for Business Server Management Shell e il cmdlet **Set-CsDialinConferencing** con i parametri seguenti:
  
- EnableNameRecording - Determina se ai partecipanti anonimi viene richiesto di registrare il proprio nome prima di accedere alla conferenza. Il valore predefinito è "$true" e indica che ai partecipanti anonimi viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. I partecipanti autenticati non registrano il proprio nome perché viene utilizzato il nome visualizzato.
    
- EntryExitAnnouncementsEnabledByDefault - Indica se gli annunci sono attivati o disattivati per impostazione predefinita. Il valore predefinito è "$false" e indica che per impostazione predefinita non vengono visualizzati annunci quando gli utenti partecipano a una conferenza o la abbandonano. L'organizzatore della riunione può sostituire questa impostazione durante la pianificazione della riunione.
    
- EntryExitAnnouncementsType - Indica l'azione eseguita ogni volta che un partecipante partecipa o esce da una conferenza per la quale sono abilitati gli annunci. Il valore predefinito è "UseNames" e indica la visualizzazione di un annuncio simile al seguente: "Davide Garghentini si è unito alla conferenza" quando gli annunci sono attivati.
    
È possibile configurare queste impostazioni a livello globale o di sito. Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Per modificare il comportamento di partecipazione a una conferenza o di abbandono della stessa

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
3. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Questo cmdlet consente di recuperare informazioni sulla necessità o meno ai partecipanti di registrare il proprio nome durante la partecipazione a una conferenza e su come Skype for Business Server risponde quando i partecipanti aderiscono o abbandonano una conferenza telefonica con accesso esterno.
    
4. Eseguire il comando seguente al prompt:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Nell'esempio seguente le impostazioni vengono configurate nell'ambito del sito per Redmond. Gli annunci sono attivati ma ai partecipanti non viene richiesto di specificare il proprio nome durante l'accesso a una conferenza. Quando i partecipanti a una conferenza entrano o abbandonano una conferenza, viene riprodotto un tono:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Per ulteriori informazioni, inclusa la sintassi e un elenco completo dei parametri, [vedere Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
