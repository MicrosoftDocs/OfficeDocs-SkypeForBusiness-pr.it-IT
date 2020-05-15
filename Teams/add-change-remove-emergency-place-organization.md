---
title: Aggiungere, modificare, rimuovere posizioni per i percorsi di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per un luogo di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232497"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione

A seconda del numero di posizioni fisiche nell'organizzazione, è possibile aggiungere posizioni per edifici, pavimenti e uffici per creare un percorso di emergenza più specifico. Per altre informazioni, vedere [gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md) .
  
Per informazioni su come ottenere un piano per le chiamate e sulla quantità di costi, vedere licenze per i [componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)per i team.

È possibile gestire le posizioni di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft teams oppure usando PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Aggiungere una posizione in un luogo di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Nell'elenco fare clic sul nome della posizione per la quale si vuole aggiungere un luogo.
3. Nella scheda **posizioni** fare clic su **Aggiungi posizione**.
4. Immettere un nome di posizione e quindi fare clic su **applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).
    
## <a name="change-a-place-for-an-emergency-location"></a>Modificare una posizione per un percorso di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Nell'elenco fare clic sul nome della posizione per la quale si desidera modificare un punto.
3. Nella scheda **posizioni** selezionare la posizione che si vuole modificare e quindi fare clic su **modifica**.
4. Aggiornare le informazioni sulla posizione e quindi fare clic su **applica**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).
    
## <a name="remove-a-place-from-an-emergency-location"></a>Rimuovere una posizione da un percorso di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **fare clic su**  >  **indirizzi di emergenza**.
2. Nell'elenco fare clic sul nome della posizione per la quale si desidera rimuovere un luogo.
3. Nella scheda **posizioni** selezionare la posizione che si desidera rimuovere e quindi fare clic su **Elimina**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).
    
## <a name="related-topics"></a>Argomenti correlati

- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
