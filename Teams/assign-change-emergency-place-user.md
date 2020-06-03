---
title: Assegnare, modificare le posizioni per i percorsi di emergenza per gli utenti
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
description: In questo articolo verrà illustrato come assegnare o modificare la posizione di un luogo di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539513"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Assegnare o modificare la posizione di un luogo di emergenza per un utente

Ogni numero di telefono attivo deve avere una posizione di emergenza associata quando si assegna il numero di telefono a un utente. (Si associa l'indirizzo quando si riceve un numero di telefono in Office 365 o quando si trasferisce un numero di telefono). Quando si associa il numero a una posizione di emergenza, è anche possibile aggiungere una posizione per specificare un percorso più preciso all'interno di una posizione fisica. Una posizione può essere il piano, l'ala dell'edificio o il numero di ufficio in cui si trova l'utente. È possibile avere un numero illimitato di posizioni per una determinata posizione di emergenza e modificare la posizione se l'utente si sposta in un altro ufficio o edificio. Ad esempio, se l'utente si sposta da piano 34 a piano 35.
  
Per informazioni su come ottenere piani per le chiamate e su quanto costano, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.
  
È possibile assegnare o modificare la posizione di un luogo di emergenza per un utente nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **Voice**  >  **numeri di telefono**vocale.

2. Nella pagina **numeri di telefono** fare clic sulla scheda **numeri** , selezionare un numero utente nell'elenco e quindi fare clic su **modifica**.

3. Nel riquadro **modifica** , in **posizione di emergenza**, eseguire una delle operazioni seguenti:

    - Per assegnare una posizione, cercare la posizione o il luogo e quindi selezionare il luogo nei risultati della ricerca.

    - Per modificare la posizione già assegnata all'utente, fare clic su **X** per rimuovere il percorso e il luogo esistenti, cercare e quindi selezionare la posizione che si vuole assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni relative al numero di telefono, disattivare o attivare l' **utente di posta elettronica con le informazioni sui numeri di telefono**. Per impostazione predefinita, questa opzione è attivata.

5. Fare clic su **applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare una posizione di emergenza per un utente](assign-change-emergency-location-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
