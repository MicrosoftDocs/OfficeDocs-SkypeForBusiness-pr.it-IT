---
title: Aggiungere, modificare, rimuovere posizioni per gli interventi di emergenza
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: "Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione nell'Microsoft Teams di amministrazione. "
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62604fc26f91baa77bd205869bbe4251d1a46a8a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602301"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Aggiungere, modificare o rimuovere un percorso per l'organizzazione di emergenza

Una località per gli interventi di emergenza deve essere associata a un numero di telefono, ma quando ciò accade può variare a seconda dei paesi e delle aree geografiche. Ad esempio, negli Stati Uniti è necessario associare una posizione di emergenza quando si assegna il numero di telefono all'utente. Nel Regno Unito, è necessario associare una posizione di emergenza al numero di telefono quando si ottengono i numeri di telefono da Microsoft 365 o Office 365 o si trasferiscono numeri di telefono dal provider di servizi corrente.

Indipendentemente dal paese o dall'area geografica in cui ci si è, è possibile aggiungere un luogo o un luogo in un luogo per gli interventi di emergenza e rimuovere un luogo per gli interventi di emergenza. A seconda del numero di posizioni fisiche dell'organizzazione, è possibile creare luoghi per edifici, piani e uffici. Vedere [Gestire le chiamate di emergenza.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Per informazioni su come ottenere un piano per chiamate e sul costo, vedere Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

È possibile gestire le posizioni di emergenza per l'organizzazione nell'Microsoft Teams di amministrazione o usando PowerShell.
  
## <a name="add-an-emergency-location"></a>Aggiungere una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per la posizione.
4. Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna, è importante comprendere che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo configurato nella posizione di emergenza, usata per acquisire il numero, deve corrispondere al codice di area del numero di telefono.

5. Se l'indirizzo non viene trovato e si vuole modificarlo manualmente, attivare **Modifica l'indirizzo manualmente.**
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modificare la posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Nell'elenco selezionare il percorso da modificare e quindi fare clic su **Modifica.**
3. Apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> È possibile modificare le informazioni sull'indirizzo per una località solo se l'indirizzo non è convalidato. Se l'indirizzo è già convalidato ed è necessario modificare l'indirizzo, eliminare la posizione e quindi creare una nuova posizione con l'indirizzo corretto.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Rimuovere una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Posizioni indirizzi**  >  **di emergenza.**
2. Nell'elenco selezionare il percorso da rimuovere e quindi fare clic su **Elimina.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)