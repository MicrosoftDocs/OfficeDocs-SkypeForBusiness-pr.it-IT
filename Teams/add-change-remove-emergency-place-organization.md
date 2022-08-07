---
title: Aggiungere, modificare e rimuovere i luoghi per gli interventi di emergenza
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Informazioni su come aggiungere, modificare o rimuovere un luogo per una posizione per gli interventi di emergenza per l'organizzazione.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1f142d7053a8254446d76dfab276baf9f6f12363
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269273"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione

A seconda del numero di posizioni fisiche nell'organizzazione, è possibile aggiungere *luoghi* per edifici, piani e uffici per creare una posizione più specifica per gli interventi di emergenza.

A seconda dell'opzione di connettività PSTN, tuttavia, la modalità di gestione delle posizioni di emergenza e dei requisiti di posizione può variare. Per ulteriori informazioni, vedi [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).

Questo articolo descrive come aggiungere, modificare o rimuovere un *luogo* per una posizione per gli interventi di emergenza per l'organizzazione.

Questo articolo si applica ai Piani per chiamate Microsoft, Operator Connect e Routing diretto.

Gestisci le posizioni per gli interventi di emergenza per la tua organizzazione nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Aggiungere un luogo a una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Nell'elenco fare clic sul nome della posizione per cui si vuole aggiungere una posizione.
3. Nella scheda **Posizioni** fare clic su **Aggiungi**.
4. Immettere un nome di località e quindi fare clic su **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Modificare un luogo per una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Nell'elenco fare clic sul nome della posizione per cui si vuole modificare una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da modificare e quindi fare clic su **Modifica**.
4. Aggiornare le informazioni sulla posizione e quindi fare clic su **Applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Rimuovere un luogo da una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Nell'elenco fare clic sul nome della posizione per cui si vuole rimuovere una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da rimuovere e quindi fare clic su **Elimina**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)