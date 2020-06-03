---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni in teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: L'amministratore può scoprire come attivare o disattivare gli annunci di entrata e uscita in una riunione di Microsoft teams.
ms.openlocfilehash: 5b3cdabac41c5c79827df714ccf3192f06b55440
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539473"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Microsoft Teams

Quando imposti Audioconferenza in Office 365, ottieni un ponte per audioconferenze. Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono che gli utenti useranno per chiamare una riunione di Microsoft teams. 
  
Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono. Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza. Un PIN viene assegnato a un organizzatore della riunione di Microsoft teams e consente loro di avviare una riunione se non è possibile avviare la riunione con l'app Microsoft teams. È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione delle opzioni di partecipazione alla riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

Per apportare queste modifiche, è necessario essere un amministratore.

1. Accedere all'interfaccia di amministrazione di  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni. 

3. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

4. Nel riquadro **Impostazioni Bridge** abilitare o disabilitare le **notifiche di entrata e uscita delle riunioni**. Questa opzione è selezionata per impostazione predefinita. Se lo si deseleziona, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.
    
5. Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.
  > [!NOTE]
  > Per impostazione predefinita, i partecipanti esterni non possono visualizzare i numeri di telefono dei partecipanti con accesso esterno. Se si vuole mantenere la privacy di questi numeri di telefono, selezionare **toni** per il **tipo di annuncio di entrata/uscita** (questo impedisce che i numeri vengano letti dalle squadre).
    
6. Se si sceglie **nomi o numeri di telefono**, abilitare o disabilitare i **chiamanti per registrare il nome prima di partecipare alla riunione**.
    
7. Fare clic su **Salva**.

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
  
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
