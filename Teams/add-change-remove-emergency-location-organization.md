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
localization_priority: Normal
f1.keywords:
- NOCSH
description: "Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza per l'organizzazione nell'interfaccia di amministrazione di Microsoft Teams. "
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a470a75d367bc47d4063a2a99171a4a09e052fca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799946"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>Aggiungere, modificare o rimuovere un percorso per l'organizzazione di emergenza

La posizione per gli interventi di emergenza deve essere associata a un numero di telefono, ma il momento in cui ciò avviene può variare a seconda del paese e dell'regione. Negli Stati Uniti, ad esempio, è necessario associare una posizione per gli interventi di emergenza quando si assegna il numero di telefono all'utente. Nel Regno Unito, è necessario associare una posizione per gli interventi di emergenza al numero di telefono quando si ottengono i numeri di telefono da Microsoft 365 o Office 365 o si trasferiscono numeri di telefono dal provider di servizi corrente.

Indipendentemente dal paese o dalla regione in cui ti posizioni, puoi aggiungere una o più posizioni in una posizione per gli interventi di emergenza e rimuovere una posizione per gli interventi di emergenza. A seconda del numero di posizioni fisiche presenti nell'organizzazione, è possibile creare posizioni per edifici, piani e uffici. Vedi [Gestire le chiamate di emergenza.](what-are-emergency-locations-addresses-and-call-routing.md)
  
Per informazioni su come ottenere un piano per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

È possibile gestire le posizioni per gli interventi di emergenza dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.
  
## <a name="add-an-emergency-location"></a>Aggiungere una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il luogo.
4. Selezionare il paese o l'area geografica e quindi immettere l'indirizzo.

   > [!NOTE]
   > In Belgio, Francia, Germania, Irlanda, Paesi Bassi e Spagna, è importante sapere che per attivare correttamente un numero di telefono in Microsoft 365 o Office 365, l'indirizzo configurato nella posizione di emergenza, usata per acquisire il numero, deve corrispondere al codice di area del numero di telefono.

5. Se l'indirizzo non viene trovato e si vuole modificarlo manualmente, attivare **Modifica l'indirizzo manualmente.**
6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)
    
## <a name="change-an-emergency-location"></a>Modificare la posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Nell'elenco selezionare il percorso da modificare e quindi fare clic su **Modifica.**
3. Apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> È possibile modificare le informazioni relative all'indirizzo per una località solo se l'indirizzo non è convalidato. Se l'indirizzo è già convalidato ed è necessario cambiarlo, eliminare la posizione e quindi creare una nuova posizione con l'indirizzo corretto.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)
    
## <a name="remove-an-emergency-location"></a>Rimuovere una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Nell'elenco selezionare la posizione da rimuovere e quindi fare clic su **Elimina.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Remove-CsOnlineLisCivicAddress.](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)

## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
