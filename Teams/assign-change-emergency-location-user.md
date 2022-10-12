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
description: In questo articolo vengono fornite informazioni su come assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a43ca031b8787d62639e141c3f733acdb402f85a
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551650"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Assegnare o modificare una posizione di emergenza per un utente

Indipendentemente [dall'opzione di connettività PSTN](pstn-connectivity.md) scelta per&mdash;i piani per chiamate Microsoft, Operator Connect, Teams Phone Mobile o Direct Routing&mdash;, è necessario assegnare una posizione per gli interventi di emergenza a ogni numero di telefono o utente.

A seconda dell'opzione di connettività PSTN, tuttavia, la modalità di gestione e assegnazione delle posizioni per gli interventi di emergenza per un utente può variare. Per ulteriori informazioni, vedi [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).

Questo articolo descrive come assegnare o modificare una posizione per gli interventi di emergenza per un utente. 

Questo articolo si applica a Piani per chiamate, Operator Connect e Teams Phone Mobile.
  
È possibile assegnare o modificare una posizione per gli interventi di emergenza per un utente nell'interfaccia di amministrazione di Microsoft Teams o usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Numeri di telefono** **vocale** > .

2. Nella pagina **Numeri di telefono** fare clic sulla scheda **Numeri** , selezionare un numero utente nell'elenco e quindi fare clic su **Modifica**.

3. Nel riquadro **Modifica** , in **Posizione per gli interventi di emergenza**, eseguire una delle operazioni seguenti:

   - Per assegnare una posizione per gli interventi di emergenza, cerca e seleziona una posizione per gli interventi di emergenza.

   - Per modificare la posizione per gli interventi di emergenza già assegnata all'utente, fai clic su **X** per rimuovere la posizione esistente, quindi cerca e seleziona la posizione che vuoi assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare **Email utente con informazioni sul numero di telefono**. Per impostazione predefinita, questa opzione è attivata.

5. Fare clic su **Applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment). 

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare un luogo per una posizione di emergenza per un utente](assign-change-emergency-place-user.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)
