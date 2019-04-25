---
title: Visualizzare un elenco di utenti abilitati per le conferenze Audio in Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come visualizzare un elenco di utenti nell'organizzazione abilitati per la conferenza telefonica dall'interfaccia di amministrazione di Skype for Business. "
ms.openlocfilehash: 722f9e411e1781529ea68f6995a2109f58d39cb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229262"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Visualizzare un elenco di utenti abilitati per le conferenze Audio in Skype Business online

> [!NOTE]
> Per informazioni sugli utenti abilitati su Microsoft Teams, consulta [Visualizzare un elenco di utenti che sono abilitati per le Audioconferenza su Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

After you have enabled Skype for Business users in your organization for Audio Conferencing, you can view the list of those users who have been enabled. When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Visualizzazione di un elenco di utenti

   
- Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**.

## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Quando visualizzi l'elenco di utenti abilitati, puoi selezionare un utente dall'elenco e utilizzare il riquadro Azioni per modificare le sue impostazioni di audioconferenza.
    
- Quando selezioni un singolo utente configurato per utilizzare Microsoft come provider di servizi di audioconferenza, puoi visualizzare il numero di telefono predefinito e se la tua organizzazione è abilitata per gli ID conferenza dinamici, e puoi reimpostare l'ID conferenza per le riunioni che organizza l'utente.
    
- Quando selezioni un singolo utente configurato per utilizzare un provider di servizi di audioconferenza di terze parti, puoi visualizzare il nome del provider di servizi di audioconferenza, il numero di telefono a pagamento e quello gratuito (se configurati).
    
- Puoi utilizzare le opzioni di filtro per visualizzare gli utenti che sono:
    
  - **In Audioconferenza**
    
  - **Non in Audioconferenza**
    
  - **Provider di servizi di conferenza - Microsoft**
    
  - **Provider di servizi di conferenza: altri**
    
- Puoi utilizzare il pulsante Cerca per cercare un singolo utente nell'elenco.
    
- Puoi selezionare più di un utente ed eseguire le operazioni seguenti:
    
  - Selezionare un numero predefinito diverso per tali utenti.
    
  - Disattivare le audioconferenze con accesso esterno per l'utente cambiando il provider su **Nessuno**.
    
  - Passare a Microsoft come provider di servizi di audioconferenza se all'utente è stata assegnata una licenza di **Audioconferenza**.
    
  - Consentire/vietare agli utenti anonimi di attivare le riunioni telefoniche degli utenti selezionati.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
