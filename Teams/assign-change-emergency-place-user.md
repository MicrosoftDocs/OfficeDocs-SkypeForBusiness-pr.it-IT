---
title: Assegnare, modificare i luoghi per le posizioni per gli interventi di emergenza per gli utenti
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
description: In questo articolo imparerai ad assegnare o modificare la posizione per una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809526"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Assegnare o modificare la posizione per una posizione per gli interventi di emergenza di un utente

Ogni numero di telefono attivo deve essere associato a una posizione per gli interventi di emergenza quando lo assegni a un utente. L'indirizzo viene associato quando si ottiene un numero di telefono in Office 365 o quando si trasferisce un numero di telefono. Quando si associa il numero a una posizione per gli interventi di emergenza, è anche possibile aggiungere una posizione per fornire una posizione più precisa all'interno di una posizione fisica. Una posizione può essere il piano, l'ala dell'edificio o il numero dell'ufficio in cui si trova l'utente. Puoi avere un numero illimitato di posti per una determinata posizione per gli interventi di emergenza e modificare la posizione se l'utente si sposta in un ufficio o un altro edificio. Ad esempio, se l'utente passa da piano 34 a piano 35.
  
Per informazioni su come ottenere i Piani per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
Puoi assegnare o modificare la posizione per gli interventi di emergenza di un utente nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su**  >  **Numeri di telefono vocali.**

2. Nella pagina **Numeri di telefono** fare clic sulla scheda **Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**

3. Nel riquadro **Modifica,** in **Posizione per gli interventi di** emergenza, eseguire una delle operazioni seguenti:

    - Per assegnare una posizione, cercala e quindi selezionala nei risultati della ricerca.

    - Per cambiare la posizione già assegnata all'utente, fare clic su **X** per rimuovere la posizione e la posizione esistenti, cercare e quindi selezionare la posizione da assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica con le informazioni sul numero di telefono all'utente, disattivare o attivare l'e-mail con informazioni **sul numero di telefono.** Per impostazione predefinita, questa opzione è on.

5. Fare clic **su Applica.**

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare una posizione di emergenza per un utente](assign-change-emergency-location-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
