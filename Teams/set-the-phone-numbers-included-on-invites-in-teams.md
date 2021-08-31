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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Seguire questa procedura per creare un numero di telefono predefinito per consentire ai chiamanti di partecipare a una Microsoft Teams riunione.
ms.openlocfilehash: 4c740147e551dade443852a98c5cdafac047815f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732715"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams

Le audioconferenze in Microsoft 365 e Office 365 consentono agli utenti dell'organizzazione di creare riunioni Microsoft Teams e quindi consentire agli utenti di accedere a tali riunioni usando un telefono.
  
Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione. Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.
  
> [!NOTE]
> Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Assegnazione iniziale dei numeri di telefono inclusi negli inviti alla riunione per i nuovi utenti

I numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per le audioconferenze sono definiti dal numero a numero verde di conferenza predefinito e dalle impostazioni predefinite dell'utente per i numeri di telefono gratuiti. Ogni impostazione specifica quale numero a pedaggio e numero verde verrà incluso nell'invito alla riunione di un determinato utente. Come indicato in precedenza, ogni invito alla riunione contiene un numero a pedaggio, un numero verde facoltativo e un collegamento che apre l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere usati per partecipare a una determinata riunione.

Per un nuovo utente, i numeri a pedaggio predefiniti per le conferenze vengono assegnati in base alla posizione di utilizzo impostata nell'interfaccia di amministrazione di Microsoft 365 dell'utente quando l'utente è abilitato per il servizio di audioconferenza. Se nel bridge di conferenza è presente un numero a pedaggio corrispondente al paese dell'utente, tale numero verrà assegnato automaticamente come numero a pedaggio predefinito dell'utente. Se non ce n'è uno, il numero definito come numero a pedaggio predefinito del bridge di conferenza verrà assegnato come numero a pedaggio predefinito dell'utente.  

Dopo aver abilitato l'utente per il servizio di audioconferenza, i numeri di telefono a numero verde e a pedaggio predefiniti dell'utente possono essere modificati dall'amministratore del tenant dai valori iniziali in qualsiasi momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Impostare o modificare il numero di telefono di audioconferenza predefinito per un organizzatore o un utente della riunione

![Icona che mostra il Microsoft Teams logo.](media/teams-logo-30x30.png) **Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.**

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](./using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Accedere all'interfaccia Microsoft Teams di amministrazione.

2. Nel riquadro di spostamento sinistro fare clic su **Utenti.**

    ![Mostra la selezione degli utenti nell'Microsoft Teams di amministrazione.](media/Admin-users.png)

3. Fare clic sul nome utente nell'elenco degli utenti disponibili.

4. Accanto a **Audioconferenza** fare clic su **Modifica.**

    ![Fare clic su Modifica accanto a Audioconferenza.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Usare i campi  **Numero a pedaggio** o Numero verde per immettere i numeri per l'utente.

> [!IMPORTANT]
> Quando si modificano le impostazioni di audioconferenza di un utente, le riunioni ricorrenti e future Microsoft Teams devono essere aggiornate e inviate ai partecipanti.

## <a name="want-to-use-windows-powershell"></a>Si vuole usare Windows PowerShell

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per impostare o modificare il numero di telefono di audioconferenza predefinito per un organizzatore o un utente che usa [Microsoft Teams PowerShell,](/powershell/module/teams/?view=teams-ps)impostare i parametri o del **`ServiceNumber`** cmdlet **`TollFreeServiceNumber`** [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) su uno dei numeri disponibili.

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
