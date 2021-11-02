---
title: Aggiungere, modificare, rimuovere luoghi per le posizioni di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fec188634377b04cb4149d3680acc07eef797149
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634875"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione

A seconda del numero di posizioni fisiche  dell'organizzazione, è possibile aggiungere luoghi per edifici, piani e uffici per creare una posizione più specifica per gli interventi di emergenza.

A seconda dell'opzione di connettività PSTN, tuttavia, la modalità di gestione delle posizioni e dei requisiti di posizione per gli interventi di emergenza può variare. Per altre informazioni, vedere [Gestire le chiamate di emergenza.](what-are-emergency-locations-addresses-and-call-routing.md)

Questo articolo descrive come aggiungere, modificare  o rimuovere una posizione per gli interventi di emergenza per l'organizzazione.

Questo articolo si applica a Piani per chiamate Microsoft, Connessione con operatore e Routing diretto.

È possibile gestire le posizioni di emergenza per l'organizzazione nell'Microsoft Teams di amministrazione o usando PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Aggiungere un luogo a un luogo per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Nell'elenco fare clic sul nome della posizione per cui si vuole aggiungere una posizione.
3. Nella scheda **Posizioni** fare clic su **Aggiungi.**
4. Immettere un nome di luogo e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Cambiare un luogo per un luogo per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Nell'elenco fare clic sul nome della posizione di cui si vuole modificare una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da modificare e quindi fare clic su **Modifica.**
4. Aggiornare le informazioni sulla posizione e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Rimuovere un luogo da un luogo per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Nell'elenco fare clic sul nome della posizione di cui si vuole rimuovere una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da rimuovere e quindi fare clic su **Elimina.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)