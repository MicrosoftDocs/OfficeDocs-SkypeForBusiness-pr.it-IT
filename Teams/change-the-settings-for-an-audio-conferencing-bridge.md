---
title: Modificare le impostazioni per un bridge per audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modificare le impostazioni del bridge per i servizi di audioconferenza, incluse le notifiche di accesso e uscita, riprodurre nomi o numeri di telefono, toni e chiedere ai chiamanti di registrare il proprio nome.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918708"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un bridge per audioconferenza

Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno i numeri di telefono per gli utenti da un bridge per audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Questi numeri di telefono vengono utilizzati per l'accesso esterno a una riunione. Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione di Skype for Business o Microsoft Teams.
  
Il bridge risponde a una chiamata e richiede al chiamante comandi vocali utilizzando un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. I PIN vengono regalati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app di Skype for Business o Microsoft Teams.

  > [!IMPORTANT]
  > Il PIN è necessario solo per l'organizzatore della riunione quando un utente dell'app Skype for Business o Microsoft Teams non ha già avviato la riunione. Se tutti i partecipanti stanno componendo il numero per la riunione, il PIN è necessario per l'avvio della riunione da parte dell'organizzatore. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra, passa **a Bridge**  >  **conferenza riunioni.** 

2. Nella parte superiore della pagina **Bridge conferenza** fare clic su **Impostazioni bridge.** 

3. Nel riquadro **Impostazioni bridge** seleziona: 
   - **Notifiche di accesso e uscita da una riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno avvisati quando qualcuno entra o esce dalla riunione.
    
     Quando si attivano le **notifiche di accesso e uscita da** una riunione, è possibile selezionare queste opzioni:
    
   - **Nomi o numeri di telefono** Quando un utente partecipa a una riunione tramite telefono, il suo numero di telefono viene riprodotto al momento dell'accesso.
    
   - **Toni** Quando un utente partecipa a una riunione tramite telefono, viene riprodotto un tono audio quando un utente si unisce alla riunione.
      
   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il proprio nome prima di partecipare a una riunione.

4. Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN **nell'elenco di lunghezza del PIN.**

5. Per specificare se inviare e-mail agli utenti, abilita o disabilita Invia automaticamente e-mail agli utenti in caso di modifiche alla configurazione delle **audioconferenze.**
    Per [ulteriori informazioni,](emails-sent-to-users-when-their-settings-change-in-teams.md) vedi E-mail inviate automaticamente agli utenti quando le impostazioni di audioconferenza vengono modificate in Microsoft Teams o E-mail inviate agli utenti quando le impostazioni vengono modificate [in Skype for Business online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)
 
6. Fare clic su **Salva**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questo processo, è possibile usare il cmdlet [Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurare le audioconferenze per Skype for Business online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
