---
title: Assegnare o modificare una posizione di emergenza per un utente
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: In questo articolo viene spiegato come assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004635be112bb8d38b88277e89c24d263b21ec37
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180899"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Assegnare o modificare una posizione di emergenza per un utente

Indipendentemente dall'opzione di connettività [PSTN](pstn-connectivity.md) scelta, è necessario scegliere Piani per chiamate Microsoft, Connessione con operatore o Instradamento diretto a ogni numero di telefono o &mdash; &mdash; utente.

A seconda dell'opzione di connettività PSTN, tuttavia, la modalità di gestione e assegnazione delle posizioni di emergenza per un utente può variare. Per altre informazioni, vedere [Gestire le chiamate di emergenza.](what-are-emergency-locations-addresses-and-call-routing.md)

Questo articolo descrive come assegnare o modificare una posizione per gli interventi di emergenza per un utente. 

Questo articolo si applica ai Piani per chiamate e Connessione con operatore.
  
È possibile assegnare o modificare una posizione per gli interventi di emergenza per un utente nell'interfaccia di amministrazione Microsoft Teams o usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione fare clic su **Numeri**  >  **Telefono vocali**.

2. Nella pagina **Telefono numeri** fare clic sulla **scheda Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**

3. Nel riquadro **Modifica,** in **Posizione emergenza,** eseguire una delle operazioni seguenti:

   - Per assegnare una posizione per gli interventi di emergenza, cercare e selezionare una posizione per gli interventi di emergenza.

   - Per modificare la posizione di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente e quindi cercare e selezionare la posizione da assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.** Per impostazione predefinita, questa opzione è impostata su .

5. Fare clic **su Applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare un luogo per una posizione di emergenza per un utente](assign-change-emergency-place-user.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)
