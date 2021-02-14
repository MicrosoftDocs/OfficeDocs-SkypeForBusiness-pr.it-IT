---
title: Aggiungere, modificare, rimuovere posizioni per le posizioni per gli interventi di emergenza
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
description: Informazioni su come aggiungere, modificare o rimuovere una posizione per gli interventi di emergenza dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806276"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione

A seconda del numero di posizioni fisiche presenti nell'organizzazione, puoi aggiungere posizioni per edifici, piani e uffici per creare una posizione per gli interventi di emergenza più specifica. Per [ulteriori informazioni, consulta Gestire](what-are-emergency-locations-addresses-and-call-routing.md) le chiamate di emergenza.
  
Per informazioni su come ottenere un piano per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

È possibile gestire le posizioni per gli interventi di emergenza dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.
  
## <a name="add-a-place-to-an-emergency-location"></a>Aggiungere una posizione a una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Nell'elenco fare clic sul nome della posizione per cui si vuole aggiungere una posizione.
3. Nella scheda **Posizioni** fare clic su **Aggiungi.**
4. Immettere un nome per il luogo e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [New-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)
    
## <a name="change-a-place-for-an-emergency-location"></a>Modificare un luogo per una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Nell'elenco fare clic sul nome della posizione di cui si vuole modificare una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da modificare e quindi fare clic su **Modifica.**
4. Aggiornare le informazioni sulla posizione e quindi fare clic su **Applica.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)
    
## <a name="remove-a-place-from-an-emergency-location"></a>Rimuovere una posizione da una posizione per gli interventi di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su Indirizzi per** gli interventi di emergenza nelle  >  **posizioni.**
2. Nell'elenco fare clic sul nome della posizione da cui si vuole rimuovere una posizione.
3. Nella scheda **Posizioni** selezionare la posizione da rimuovere e quindi fare clic su **Elimina.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Remove-CsOnlineLisLocation.](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)
    
## <a name="related-topics"></a>Argomenti correlati

- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
