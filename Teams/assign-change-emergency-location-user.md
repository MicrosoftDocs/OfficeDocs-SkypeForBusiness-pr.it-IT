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
localization_priority: Normal
f1.keywords:
- NOCSH
description: In questo articolo imparerai ad assegnare o modificare una posizione per gli interventi di emergenza per gli utenti dell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809566"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Assegnare o modificare una posizione di emergenza per un utente

Quando si configurano i Piani per chiamate, è necessario assegnare una posizione per gli interventi di emergenza a ogni numero di telefono o utente. Nei paesi europei, la posizione per gli interventi di emergenza è associata al numero di telefono quando la ottieni da Microsoft 365 o Office 365 o quando trasferisci un numero di telefono in Microsoft 365 o Office 365. Negli Stati Uniti, la posizione per gli interventi di emergenza viene associata al numero di telefono quando viene assegnata all'utente. L'indirizzo per gli interventi di emergenza può essere modificato se l'utente a cui è assegnato si sposta in una nuova posizione. Per ulteriori informazioni su indirizzi e posizioni per gli interventi di emergenza, consulta Cosa sono il routing delle chiamate, le posizioni e le posizioni [per gli interventi di emergenza?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)
  
Per informazioni su come ottenere un Piano per chiamate e sul loro costo, consulta Licenze [per i componenti aggiuntivi di Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
Puoi assegnare o modificare la posizione per gli interventi di emergenza di un utente nell'interfaccia di amministrazione di Microsoft Teams o tramite PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fai clic **su**  >  **Numeri di telefono vocali.**

2. Nella pagina **Numeri di telefono** fare clic sulla scheda **Numeri,** selezionare un numero utente nell'elenco e quindi fare clic su **Modifica.**

3. Nel riquadro **Modifica,** in **Posizione per gli interventi di** emergenza, eseguire una delle operazioni seguenti:

   - Per assegnare una posizione per gli interventi di emergenza, cercala e selezionala.

   - Per modificare la posizione per gli interventi di emergenza già assegnata all'utente, fare clic su **X** per rimuovere la posizione esistente, quindi cercare e selezionare la posizione da assegnare.

4. A seconda che si voglia inviare un messaggio di posta elettronica con le informazioni sul numero di telefono all'utente, disattivare o attivare l'e-mail con informazioni **sul numero di telefono.** Per impostazione predefinita, questa opzione è on.

5. Fare clic **su Applica.**

## <a name="using-powershell"></a>Utilizzo di PowerShell

Vedi [Set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Aggiungere, modificare o rimuovere un luogo per una posizione di emergenza per l'organizzazione](add-change-remove-emergency-place-organization.md)
- [Assegnare o modificare un luogo per una posizione di emergenza per un utente](assign-change-emergency-place-user.md)
- [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
