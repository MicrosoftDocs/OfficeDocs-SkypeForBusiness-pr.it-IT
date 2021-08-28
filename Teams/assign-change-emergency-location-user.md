---
title: Assegnare o modificare una posizione di emergenza per un utente
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
description: Questo articolo illustra come assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36be65ef14cfe0fc97ce49dfa9227fe50daa18f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588378"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Assegnare o modificare una posizione di emergenza per un utente

Durante la configurazione dei Piani per le chiamate, è necessario assegnare una posizione di emergenza a ogni numero di telefono o utente. Nei paesi europei, la posizione di emergenza è associata al numero di telefono quando lo ricevi da Microsoft 365 o Office 365 o quando trasferisci un numero di telefono a Microsoft 365 o Office 365. Negli Stati Uniti, la posizione di emergenza è associata al numero di telefono quando viene assegnato all'utente. L'indirizzo per gli interventi di emergenza può essere modificato se l'utente a cui è assegnato si sposta in una nuova posizione. Per altre informazioni sugli indirizzi e le posizioni per gli interventi di emergenza, vedere Che cosa sono le località [di emergenza, i luoghi e il routing delle chiamate?](./what-are-emergency-locations-addresses-and-call-routing.md).
  
Per informazioni su come ottenere un Piano per chiamate e sul costo, vedere Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
È possibile assegnare o modificare una posizione per gli interventi di emergenza per un utente nell'interfaccia di amministrazione Microsoft Teams o usando PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic **su** Numeri Telefono  >  **vocali**.

2. Nella pagina **Telefono numeri** fare clic sulla **scheda Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**

3. Nel riquadro **Modifica,** in **Posizione emergenza,** eseguire una delle operazioni seguenti:

   - Per assegnare una posizione per gli interventi di emergenza, cercare e selezionare una posizione per gli interventi di emergenza.

   - Per modificare la posizione di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente e quindi cercare e selezionare la posizione da assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica all'utente con le informazioni sul numero di telefono, disattivare o attivare l'utente di posta elettronica **con informazioni sul numero di telefono.** Per impostazione predefinita, questa opzione è impostata su .

5. Fare clic **su Applica**.

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare un luogo per una posizione di emergenza per un utente](assign-change-emergency-place-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)