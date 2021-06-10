---
title: Assegnare, modificare le posizioni per gli interventi di emergenza per gli utenti
author: cichur
ms.author: v-cichur
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
description: In questo articolo viene spiegato come assegnare o modificare la posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120828"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Assegnare o modificare la posizione di un luogo per gli interventi di emergenza per un utente

Ogni numero di telefono attivo deve avere una posizione di emergenza associata quando lo assegni a un utente. L'indirizzo viene associato quando si ottiene un numero di telefono in Office 365 o quando si trasferisce un numero di telefono. Quando si associa il numero a una posizione di emergenza, è anche possibile aggiungere un luogo per fornire una posizione più esatta all'interno di una posizione fisica. Un luogo può essere il piano, l'ala dell'edificio o il numero dell'ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posti per una determinata posizione di emergenza e cambiare il luogo se l'utente si sposta in un altro ufficio o edificio. Ad esempio, se l'utente passa dal piano 34 al piano 35.
  
Per informazioni su come ottenere piani per chiamate e sul costo, vedere Teams [licenze per i componenti aggiuntivi.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
È possibile assegnare o modificare la posizione di un luogo per gli interventi di emergenza per un utente nell'interfaccia di amministrazione di Microsoft Teams o usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Numeri**  >  **Telefono vocali**.

2. Nella pagina **Telefono numeri** fare clic sulla scheda **Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**

3. Nel riquadro **Modifica,** in **Posizione emergenza,** eseguire una delle operazioni seguenti:

    - Per assegnare una posizione, cercare la posizione o la posizione e quindi selezionare la posizione nei risultati della ricerca.

    - Per modificare la posizione già assegnata all'utente, fare clic su **X** per rimuovere la posizione e la posizione esistenti, cercare e quindi selezionare il luogo da assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.** Per impostazione predefinita, questa opzione è impostata su .

5. Fare clic **su Applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare una posizione di emergenza per un utente](assign-change-emergency-location-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)