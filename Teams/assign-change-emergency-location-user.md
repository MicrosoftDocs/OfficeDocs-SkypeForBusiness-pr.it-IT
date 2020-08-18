---
title: Assegnare o modificare una posizione di emergenza per un utente
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni su come assegnare o modificare una posizione di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788660"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Assegnare o modificare una posizione di emergenza per un utente

Quando si configurano piani di chiamata, è necessario assegnare una posizione di emergenza a ogni numero di telefono o utente. Nei paesi europei la posizione di emergenza è associata al numero di telefono quando viene scaricata da Microsoft 365 o Office 365 o quando si trasferisce un numero di telefono a Microsoft 365 o Office 365. Negli Stati Uniti, la posizione di emergenza è associata al numero di telefono quando viene assegnata all'utente. L'indirizzo di emergenza può essere modificato se l'utente a cui viene assegnato si sposta in una nuova posizione. Per altre informazioni su indirizzi e posizioni di emergenza, vedere [quali sono le posizioni di emergenza, i luoghi e il routing delle chiamate?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).
  
Per informazioni su come ottenere piani per le chiamate e su quanto costano, vedere [licenze per i componenti aggiuntivi](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)per i team.
  
È possibile assegnare o modificare una posizione di emergenza per un utente nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **Voice**  >  **numeri di telefono**vocale.

2. Nella pagina **numeri di telefono** fare clic sulla scheda **numeri** , selezionare un numero utente nell'elenco e quindi fare clic su **modifica**.

3. Nel riquadro **modifica** , in **posizione di emergenza**, eseguire una delle operazioni seguenti:

   - Per assegnare una posizione di emergenza, cercare e selezionare una posizione di emergenza.

   - Per modificare la posizione di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente e quindi cercare e selezionare la posizione che si vuole assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni relative al numero di telefono, disattivare o attivare l' **utente di posta elettronica con le informazioni sui numeri di telefono**. Per impostazione predefinita, questa opzione è attivata.

5. Fare clic su **applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare un luogo per una posizione di emergenza per un utente](assign-change-emergency-place-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
