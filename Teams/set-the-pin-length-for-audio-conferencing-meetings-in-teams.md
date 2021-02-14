---
title: Impostare la lunghezza dei PIN per le riunioni in audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN e su come impostare la durata delle riunioni in Microsoft Teams.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691102"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Impostare la lunghezza del PIN per le riunioni con audioconferenza in Microsoft Teams

Quando si configurano le audioconferenze per Microsoft Teams, si ottiene un bridge per i servizi di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Il numero di telefono impostato verrà incluso nelle convocazioni di riunione per l'app Microsoft Teams.
  
Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono. Risponde al chiamante con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni. Gli organizzatori delle riunioni usano i PIN per avviare le riunioni se non possono partecipare usando l'app Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Impostazione della lunghezza del PIN

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.** 

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.** 

3. Nel riquadro **Impostazioni bridge,** in **Lunghezza PIN,** selezionare il numero di cifre desiderato per il PIN.

4. Fare clic su **Salva**.

> [!NOTE]
> Un PIN è diverso da un ID conferenza. Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione. Vengono utilizzati per identificare la riunione. Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione. 

## <a name="want-to-know-more-about-pin-settings"></a>Vuoi saperne di più sulle impostazioni del PIN?

- I PIN possono contenere da 4 a 12 cifre; l'impostazione predefinita è 5. Solo i numeri vengono utilizati quando si creano dei PIN. Lettere e caratteri speciali non vengono utilizzati.
    
- Il PIN è necessario solo per l'organizzatore della riunione quando un utente di Microsoft Teams non ha già avviato la riunione. L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.
    
- Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft. Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
    
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
