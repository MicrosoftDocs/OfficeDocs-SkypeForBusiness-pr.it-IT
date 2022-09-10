---
title: Impostare la lunghezza dei PIN per le riunioni in audioconferenza
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN e su come impostare la lunghezza per le riunioni in Microsoft Teams.
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641957"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Impostare la lunghezza del PIN per le riunioni di Audioconferenza in Microsoft Teams

Quando si configurano le audioconferenze per Microsoft Teams, si ottiene un bridge di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Il numero di telefono impostato verrà incluso negli inviti alle riunioni per l'app Microsoft Teams.
  
Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono. Risponde al chiamante con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche e chiedere ai chiamanti di registrare il proprio nome. **Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni. Gli organizzatori delle riunioni usano pin per avviare le riunioni se non possono partecipare alla riunione con l'app Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Impostazione della lunghezza del PIN

Usando l'interfaccia di amministrazione di Microsoft Teams:

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** , in **Lunghezza PIN**, seleziona il numero di cifre desiderato per il PIN.

4. Fare clic su **Salva**.

> [!NOTE]
> Un PIN è diverso da un ID conferenza. Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione. Vengono utilizzati per identificare la riunione. Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione.

## <a name="want-to-know-more-about-pin-settings"></a>Vuoi saperne di più sulle impostazioni del PIN?

- I PIN possono essere da 4 a 12 cifre; il valore predefinito è 5. Solo i numeri vengono utilizati quando si creano dei PIN. Lettere e caratteri speciali non vengono utilizzati.

- Il PIN è necessario per l'organizzatore della riunione solo quando un utente di Microsoft Teams non ha già avviato la riunione. L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.

- Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft. Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che semplifica il lavoro quotidiano quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare i servizi di audioconferenza in Microsoft 365 per Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
