---
title: Aggiungere, modificare, rimuovere posizioni per gli interventi di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c0a195a221bff5b008f5754592450f4f2b1e42e6
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606635"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Aggiungere, modificare o rimuovere un percorso per l'organizzazione di emergenza

Indipendentemente [dall'opzione di connettività PSTN](pstn-connectivity.md), è possibile associare&mdash;a un numero di telefono i piani per chiamate Microsoft, Operator Connect, Connessione con operatore di telefonia mobile (versione di anteprima pubblica) o le posizioni per gli interventi di emergenza Direct Routing&mdash;.

Tuttavia, a seconda dell'opzione di connettività PSTN, la modalità di gestione delle posizioni di emergenza e dei requisiti di posizione può variare. Per ulteriori informazioni, vedi [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md).

Questo articolo descrive come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione. 

Questo articolo si applica a Piani per chiamate Microsoft, Operator Connect, Connessione con operatore di telefonia mobile (versione di anteprima pubblica) e Routing diretto.

Gestisci le posizioni per gli interventi di emergenza per la tua organizzazione nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

Per assegnare una posizione per gli interventi di emergenza, gli utenti, i numeri di telefono e le posizioni per gli interventi di emergenza devono trovarsi nello stesso paese. Per altre informazioni, vedi [Assegnare o modificare una posizione per gli interventi di emergenza per un utente](assign-change-emergency-location-user.md).
  
## <a name="add-an-emergency-location"></a>Aggiungi una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il luogo.
4. Seleziona il paese o l'area geografica e quindi immetti l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna, è importante capire che per attivare correttamente un numero di telefono in Microsoft 365, l'indirizzo configurato nella posizione per gli interventi di emergenza, usato per acquisire il numero, deve corrispondere al prefisso del numero di telefono.

5. Se l'indirizzo non viene trovato e si vuole modificare manualmente l'indirizzo, attivare **Modifica manualmente l'indirizzo**.
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress).
    
## <a name="change-an-emergency-location"></a>Modificare la posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Nell'elenco selezionare il percorso da modificare e quindi fare clic su **Modifica**.
3. Apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> È possibile modificare le informazioni relative all'indirizzo per una località solo se l'indirizzo non è convalidato. Se l'indirizzo è già convalidato ed è necessario cambiarlo, eliminarlo e quindi creare una nuova posizione con l'indirizzo corretto.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress).
    
## <a name="remove-an-emergency-location"></a>Rimuovere una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Indirizzi di emergenza** **posizioni** > .
2. Nell'elenco selezionare il percorso da rimuovere e quindi fare clic su **Elimina**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)