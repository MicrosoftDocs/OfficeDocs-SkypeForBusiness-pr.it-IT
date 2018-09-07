---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come attivare gli annunci di entrata e uscita per le riunioni in Skype for Business Online tramite l'interfaccia di amministrazione di Skype for Business. "
ms.openlocfilehash: 8d91db2014439eb2c9e38f65215cf85d6f047157
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863264"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Skype for Business online

> [!Note]
> Per informazioni sugli annunci di entrata e uscita in Microsof Teamst, consulta [Attivazione o disattivazione degli annunci di entrata e uscita per le riunioni in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Quando imposti Audioconferenza in Office 365, ottieni un ponte per audioconferenze. Un ponte per audioconferenze può contenere uno o più numeri di telefono che le persone possono utilizzare per partecipare a una riunione su Skype for Business. 
  
Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono. Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza. Viene assegnato un PIN a un organizzatore della riunione su Skype for Business, il quale permette di avviare la riunione se i partecipanti non sono in grado di farlo tramite l'app di Skype for Business. È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione delle opzioni di partecipazione alla riunione
    
1. Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Audioconferenza** > **Impostazioni del ponte Microsoft**.
    
2. Su **Esperienza di partecipazione alle riunioni**, seleziona o deseleziona **Abilita l'attivazione di annunci di entrata e uscita per la riunione**. Questa opzione è selezionata per impostazione predefinita. Se si deseleziona la casella, gli utenti che già partecipano alla riunione non verranno informati quando un utente accede alla riunione o quando l'abbandona.
    
3. Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.
    
4. Seleziona o deseleziona **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per automatizzarle o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
-  Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre numerosi vantaggi per quanto riguarda velocità, semplicità e produttività rispetto all'uso della sola Interfaccia di amministrazione di Office 365, ad esempio quando si modificano le impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
