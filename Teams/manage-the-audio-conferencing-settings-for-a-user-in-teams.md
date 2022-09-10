---
title: Gestire le impostazioni dei servizi di audioconferenza per gli utenti
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
description: Un amministratore di Microsoft 365 o Office 365 può modificare le impostazioni delle audioconferenze di Teams, inclusi il provider, il numero a pagamento o verde predefinito, l'ID conferenza o il PIN per un utente.
ms.openlocfilehash: 9b68ea4452928ce739ec8429ed9b71bfaca91cf4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641907"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Gestire le impostazioni delle audioconferenze per un utente in Microsoft Teams

Gli amministratori di Microsoft 365 o Office 365 possono modificare le impostazioni per i servizi di audioconferenza, ad esempio il provider, il numero a pagamento o verde predefinito, l'ID conferenza o il PIN, per un singolo utente dell'organizzazione. Se vuoi modificare le impostazioni per la tua organizzazione, vedi [Gestire le impostazioni dei servizi di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. Fare clic su **Modifica**.

3. In **Audioconferenza**, modifica una delle opzioni seguenti:

|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Audioconferenza**|Per attivare o disattivare i servizi di audioconferenza per l'utente, fai clic su **Modifica** accanto a **Audioconferenza** e quindi, nel riquadro **Audioconferenza** , attiva o disattiva **Audioconferenza** .|
|**Inviare informazioni sulla conferenza tramite posta elettronica**  |Fai clic su questo collegamento solo se desideri inviare immediatamente un messaggio di posta elettronica all'utente con il suo ID conferenza e numero di telefono. (Questo messaggio di posta elettronica non include il PIN). Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**ID conferenza**  |Se devi reimpostare l'ID conferenza per l'utente, fai clic su **Reimposta ID conferenza** . Per ulteriori informazioni, consulta [Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user-in-teams.md).  |
|**PIN** |Se è necessario reimpostare il PIN per l'utente, fare clic su **Reimposta PIN** . Per ulteriori informazioni, consulta [Reimpostare il PIN per Audioconferenza](reset-the-audio-conferencing-pin-in-teams.md). |
|**Numero di telefono a pagamento predefinito per le conferenze** (obbligatorio) |I numeri impostati sul bridge di audioconferenza. Formattare i numeri in modo che vengano visualizzati nelle convocazioni riunione di Teams. Per modificare il numero a pagamento predefinito, fai clic su **Modifica** accanto a **Audioconferenza** e seleziona un numero in Numero a **pagamento** nel riquadro **Audioconferenza**. È anche possibile impostare i numeri di telefono aggiungendoli al TeamsAudioConferencingPolicy e assegnando i criteri agli utenti. I numeri di telefono aggiunti al criterio hanno la precedenza sui numeri di telefono impostati con il **numero di telefono a pagamento per le conferenze predefinite**. Se non vengono aggiunti numeri di telefono a TeamsAudioConferencingPolicy, il numero di telefono impostato utilizzando il **numero di telefono** predefinito per le conferenze a pagamento verrà visualizzato nelle convocazioni di riunione di Microsoft Teams. |
|**Gli inviti di questo utente possono includere il numero verde**|Questa impostazione può essere modificata solo usando TeamsAudioconferecningPolicy. |
|**Gli utenti non autenticati possono essere la prima persona nella riunione**|Per modificare questa impostazione, attivare o disattivare **gli utenti non autenticati** .
|**Autorizzazioni di accesso in uscita**|Per modificare questa impostazione, fai clic su **Modifica** accanto a **Audioconferenza** e nel riquadro **Audioconferenza** scegli un'opzione in **Chiamata in uscita dalle riunioni**.|

![Mostra le impostazioni delle audioconferenze per un utente.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
