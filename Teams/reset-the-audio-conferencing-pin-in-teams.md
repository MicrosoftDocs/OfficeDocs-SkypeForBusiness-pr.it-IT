---
title: Reimpostare il PIN di audioconferenza in Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- seo-marvel-apr2020
description: Scopri come reimpostare il PIN di un utente per i servizi di audioconferenza in Microsoft Teams e scopri i fatti importanti sui PIN.
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329030"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Reimpostare il PIN di audioconferenza in Microsoft Teams

Un PIN è un codice costituito da numeri creati per ogni utente di Microsoft Teams abilitato per le audioconferenze. I PIN per i servizi di audioconferenza vengono utilizzati dagli organizzatori della riunione per identificare l'organizzatore della riunione e consentire loro di avviare una riunione tramite telefono. Se usano l'app Microsoft Teams per avviare la riunione, non è necessario un PIN. Se gli utenti dimenticano il PIN e non riescono a trovarlo nel messaggio e-mail che gli è stato inviato quando sono stati abilitati per i servizi di audioconferenza, un amministratore può reimpostare il PIN o reimpostare il proprio PIN.
  
Le riunioni possono essere avviate quando un utente autenticato partecipa tramite l'app Microsoft Teams o quando l'organizzatore partecipa con il PROPRIO PIN tramite telefono. Quando una riunione richiede l'avvio di un PIN, gli utenti che partecipano tramite telefono verranno messi nella sala d'attesa e ascolteranno musica in attesa finché l'organizzatore non li ammette. Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.

## <a name="reset-a-users-pin"></a>Reimpostare il PIN dell'utente

Usando l'interfaccia di amministrazione di Microsoft Teams:

1. Nel riquadro di spostamento sinistro fare clic su **Utenti** e quindi selezionare l'utente dall'elenco di utenti disponibili.

2. Fare clic su **Modifica**.

3. In **Audioconferenza** fai clic su **Reimposta PIN**.

4. Fare clic su **Reimposta**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>Chiedi a un utente di reimpostare il proprio PIN

1. Chiedi all'utente di accedere a [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp).
2. Fare clic su **Reimposta PIN**.

> [!NOTE]
> Per GCCH, vai a: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp).
> Per DoD, vai a: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp).

> [!NOTE]
> Se si usa questo metodo, all'utente non verrà inviato un messaggio di posta elettronica per la reimpostazione del PIN.

## <a name="what-else-should-you-know-about-pins"></a>Quali sono le altre informazioni utili sul PIN?

- Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, quando il PIN viene reimpostato. Dopo la reimpostazione del PIN da parte di un amministratore, il PIN verrà elencato come **********.

- L'invio automatico di messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per i servizi di audioconferenza o quando il PIN viene reimpostato. Tuttavia, se hai disabilitato l'invio automatico dei messaggi di posta elettronica, un messaggio e-mail di reimpostazione del PIN non verrà inviato a un utente e dovrai inviare manualmente le informazioni sul PIN all'utente.

- All'avvio di una riunione, l'organizzatore deve ammettere tutti gli utenti PSTN nella sala di attesa per partecipare alla riunione. Ad esempio, se due partecipanti PSTN tentano di partecipare a una riunione prima dell'inizio, verranno messi in sala d'attesa e ascolteranno musica in attesa e quando l'organizzatore della riunione si unirà usando il PIN tramite telefono, la riunione verrà avviata e l'organizzatore potrà usare il comando in riunione (premere *21) per ammettere tutti gli utenti PSTN nella sala di attesa.

- L'impostazione predefinita è impedire l'avvio di una riunione da parte di chiamanti anonimi.

- Quando si abilita un utente per i servizi di audioconferenza, per impostazione predefinita vengono inviati messaggi di posta elettronica che includono informazioni sulle conferenze e il PIN. L'utente deve avere una cassetta postale di Microsoft 365 o Office 365 perché, quando il PIN viene reimpostato, un nuovo PIN viene inviato all'utente tramite posta elettronica al suo indirizzo SMTP principale (alias) impostato per l'utente.

- Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione. I PIN possono essere compresi tra 4 e 12 cifre, il valore predefinito è 5. Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze. Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).

- Per impostazione predefinita, la posta elettronica verrà impostata su Microsoft 365 o Office 365 indirizzo SMTP principale dell'utente. È possibile inviare un messaggio di posta elettronica a un indirizzo non Microsoft 365 o non Office 365, ad esempio un indirizzo di posta elettronica Hotmail o MSN. È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell. Questa opzione è utile se gli utenti non hanno una cassetta postale di Exchange in Microsoft 365 o Office 365.

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che semplifica il lavoro quotidiano quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Argomenti correlati

[Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user-in-teams.md)
