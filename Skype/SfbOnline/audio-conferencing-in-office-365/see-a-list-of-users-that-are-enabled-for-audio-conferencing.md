---
title: Visualizzare un elenco di utenti abilitati per le audioconferenze in Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni su come visualizzare un elenco di utenti nell'organizzazione abilitati per la conferenza telefonica dall'interfaccia di amministrazione di Skype for Business. "
ms.openlocfilehash: 91ac12b07465491b2b8e721f7e876bb9e35cd9af
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618292"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Visualizzare un elenco di utenti abilitati per le audioconferenze in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Per informazioni sugli utenti abilitati su Microsoft Teams, consulta [Visualizzare un elenco di utenti che sono abilitati per le Audioconferenza su Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Dopo aver abilitato gli utenti di Skype for Business all'interno della tua organizzazione per Audioconferenza, puoi visualizzare l'elenco degli utenti che sono stati abilitati. Quando esamini l'elenco, verrà visualizzato anche il tipo di provider di servizi di conferenza audio che utilizza ogni utente, il numero di telefono di accesso esterno predefinito per l'utente e, se la tua organizzazione non è abilitata per gli ID conferenza dinamici, gli ID conferenza statici per le riunioni in audioconferenza che essi organizzano.

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

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business Online usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando è necessario eseguire più attività. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo del interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
