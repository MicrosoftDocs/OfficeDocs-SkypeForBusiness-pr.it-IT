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
description: Per informazioni sui parametri relativi alla lunghezza e ai requisiti di un PIN, vedere come impostare la lunghezza delle riunioni in Microsoft teams.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691102"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Impostare la lunghezza del PIN per le riunioni di audioconferenza in Microsoft Teams

Quando si configura una conferenza audio per Microsoft teams, si otterrà un Bridge per audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Il numero di telefono impostato verrà incluso nell'invito alla riunione per l'app Microsoft teams.
  
Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono. Risponde al chiamante con le richieste vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni. Gli organizzatori della riunione usano i pin per avviare le riunioni se non possono partecipare alla riunione usando l'app Microsoft teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Impostazione della lunghezza del PIN

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni. 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** , in **lunghezza PIN**, selezionare il numero di cifre desiderato per il PIN.

4. Fare clic su **Salva**.

> [!NOTE]
> Un PIN è diverso da un ID conferenza. Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione. Vengono utilizzati per identificare la riunione. Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione. 

## <a name="want-to-know-more-about-pin-settings"></a>Vuoi saperne di più sulle impostazioni del PIN?

- I pin possono essere da 4 a 12 cifre; il valore predefinito è 5. Solo i numeri vengono utilizati quando si creano dei PIN. Lettere e caratteri speciali non vengono utilizzati.
    
- Un PIN è necessario solo per l'organizzatore della riunione quando un utente di Microsoft teams non ha già avviato la riunione. L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.
    
- Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft. Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
    
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare servizi di audioconferenza in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
