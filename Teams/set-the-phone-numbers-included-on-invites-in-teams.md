---
title: Impostare i numeri di telefono inclusi negli inviti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Seguire questa procedura per creare un numero di telefono predefinito che i chiamanti possono utilizzare per partecipare a una riunione di Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372185"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams

Le audioconferenze in Microsoft 365 e Office 365 consentono agli utenti dell'organizzazione di creare riunioni di Microsoft Teams e quindi di accedere a tali riunioni tramite telefono.
  
Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione. Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.
  
> [!NOTE]
> Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Assegnazione iniziale dei numeri di telefono inclusi negli inviti alle riunioni per i nuovi utenti

I numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per i servizi di audioconferenza sono definiti dal numero di telefono a numero verde predefinito per i servizi di conferenza e dalle impostazioni predefinite per il numero verde per le conferenze. Ogni impostazione specifica quale numero a pedaggio e numero verde verrà incluso nell'invito alla riunione di un determinato utente. Come già detto, ogni invito alla riunione contiene un numero verde, un numero verde facoltativo e un collegamento che apre l'elenco completo di tutti i numeri di telefono per l'accesso esterno che possono essere utilizzati per partecipare a una determinata riunione.

Per un nuovo utente, i numeri di conferenza predefiniti vengono assegnati in base alla posizione di utilizzo impostata nell'interfaccia di amministrazione di Microsoft 365 dell'utente quando l'utente è abilitato per il servizio di audioconferenza. Se nel bridge di conferenza è presente un numero a numero verde corrispondente al paese dell'utente, tale numero verrà assegnato automaticamente come numero a pedaggio predefinito dell'utente. In caso contrario, come numero a pedaggio predefinito del bridge di conferenza verrà assegnato il numero a pedaggio predefinito dell'utente.  

Una volta che l'utente è stato abilitato per il servizio di audioconferenza, i numeri di telefono a pedaggio e verde predefiniti dell'utente possono essere modificati dall'amministratore del tenant dai loro valori iniziali in qualsiasi momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Impostare o modificare il numero di telefono predefinito per i servizi di audioconferenza per un utente o un organizzatore della riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

Per apportare queste modifiche, è necessario essere un amministratore dei servizi di Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) e leggere come ottenere i ruoli di amministratore e le autorizzazioni.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams.

2. Nel riquadro di spostamento sinistro fare clic **su Utenti.**

    ![Mostra la selezione di utenti nell'interfaccia di amministrazione di Microsoft Teams](media/Admin-users.png)

3. Fare clic sul nome utente nell'elenco di utenti disponibili.

4. Accanto a **Audioconferenza,** fai clic **su Modifica.**

    ![Fare clic su Modifica accanto a Audioconferenza](media/teams-set-phone-numbers-on-invites-image3.png)

5. Usare i **campi Numero a numero verde** o **Numero** verde per immettere i numeri per l'utente.

> [!IMPORTANT]
> Quando si modificano le impostazioni delle audioconferenze di un utente, le riunioni ricorrenti e future di Microsoft Teams devono essere aggiornate e inviate ai partecipanti.

## <a name="want-to-use-windows-powershell"></a>Si vuole usare Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
