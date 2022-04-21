---
title: Impostare i numeri di telefono inclusi negli inviti
ms.author: heidip
author: MicrosoftHeidi
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
description: Seguire questa procedura per creare un numero di telefono predefinito per consentire ai chiamanti di partecipare a una riunione Microsoft Teams.
ms.openlocfilehash: 7f22f86a020940caf663b671c81ab7958230db21
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016578"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams

I servizi di audioconferenza in Microsoft 365 e Office 365 consentono agli utenti dell'organizzazione di creare riunioni Microsoft Teams e quindi consentire agli utenti di accedere alle riunioni con un numero di telefono.

Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione. Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.

Oltre ai numeri di telefono inclusi nell'invito alla riunione per un organizzatore della riunione, è presente anche un collegamento nella parte inferiore di ogni invito alla riunione che apre l'elenco completo di tutti i numeri di telefono per l'accesso esterno che possono essere usati per partecipare a una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>Assegnazione iniziale dei numeri di telefono inclusi negli inviti alle riunioni per gli utenti

I numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per le audioconferenze sono definiti nel *TeamsAudioConferencingPolicy* assegnato agli utenti. Quando un *TeamsAudioConferencingPolicy* viene assegnato a un utente, tutti i numeri di telefono a pagamento e gratuiti aggiunti nel criterio vengono inclusi negli inviti alle riunioni per gli utenti che hanno tale criterio. Se a un utente è assegnato un *TeamsAudioConferencingPolicy* e non sono stati aggiunti numeri di telefono a pagamento o numeri verdi al criterio, in questo caso i numeri di telefono visualizzati negli inviti alle riunioni di questi utenti sono definiti dal numero di telefono predefinito per i servizi di conferenza a pagamento e dal numero verde predefinito per le conferenze nelle impostazioni di ciascun utente.

> [!NOTE]
> I numeri verdi o a tariffa aggiunti al *TeamsAudioConferencingPolicy* di un utente hanno la precedenza sui numeri di telefono impostati singolarmente utilizzando il numero di telefono a pagamento predefinito per i servizi di conferenza e il numero verde predefinito per le conferenze nelle impostazioni di un utente.

Come indicato in precedenza, oltre ai numeri di telefono, ogni invito alla riunione contiene un collegamento che apre l'elenco completo di tutti i numeri di telefono per l'accesso esterno che possono essere utilizzati per partecipare a una determinata riunione.

### <a name="new-users"></a>Nuovi utenti

I numeri verdi e a pagamento inclusi negli inviti alle riunioni per i nuovi utenti sono definiti anche dal *TeamsAudioconferencingPolicy* assegnato a tali utenti. Per impostazione predefinita, a tutti i nuovi utenti viene assegnato il Global *TeamsAudioconferencingPolicy*. I criteri globali non prevedono l'aggiunta di numeri di telefono, a meno che non vengano modificati dall'amministratore del tenant. In questo caso, i numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per le audioconferenze sono definiti dal numero di telefono a pagamento predefinito per i servizi di conferenza e dal numero verde predefinito per le conferenze disponibili nelle impostazioni di ciascun utente.

Per un nuovo utente, i numeri a tariffa predefiniti per le conferenze vengono assegnati in base alla posizione di utilizzo impostata nell'interfaccia di amministrazione Microsoft 365 dell'utente quando l'utente è abilitato per il servizio di audioconferenza. Se nel bridge di conferenza è presente un numero a tariffa corrispondente al paese dell'utente, tale numero verrà assegnato automaticamente come numero a tariffa predefinito dell'utente. In caso contrario, il numero definito come numero a pagamento predefinito del bridge di conferenza verrà assegnato come numero a pagamento predefinito dell'utente.  

Dopo aver abilitato l'utente per il servizio Di audioconferenza, i numeri verdi e a tariffa predefiniti dell'utente possono essere modificati dall'amministratore del tenant in base ai valori iniziali in base alle esigenze.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>Impostare o modificare il numero di telefono predefinito per i servizi di audioconferenza per gli utenti in Powershell usando il cmdlet *TeamsAudioConferencingPolicy*

Vedi [Le impostazioni dei criteri per le audioconferenze per i numeri verdi e a pagamento](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>Impostare o modificare il numero di telefono predefinito dei servizi di audioconferenza per un organizzatore o un utente della riunione singolarmente

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](./using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Accedere all'interfaccia di amministrazione di Microsoft Teams.

2. Nel riquadro di spostamento sinistro fare clic su **Utenti**.

    ![Mostra la selezione di utenti nell'interfaccia di amministrazione di Microsoft Teams.](media/Admin-users.png)

3. Fare clic sul nome utente nell'elenco degli utenti disponibili.

4. Accanto a **Audioconferenza**, fai clic su **Modifica**.

    ![Fai clic su Modifica accanto a Audioconferenza.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Usa i campi **Numero a pagamento** o **Numero verde** per immettere i numeri per l'utente.

> [!IMPORTANT]
> Quando si modificano le impostazioni dei servizi di audioconferenza di un utente, le riunioni Microsoft Teams ricorrenti e future devono essere aggiornate e inviate ai partecipanti.

> [!NOTE]
> I numeri di telefono immessi in questa impostazione vengono utilizzati solo se il *criterio TeamsAudioConferencingPolicy* assegnato all'utente non ha alcun numero di telefono aggiunto.

## <a name="want-to-use-windows-powershell"></a>Si vuole usare Windows PowerShell

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che semplifica il lavoro quotidiano quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

Per impostare o modificare il numero di telefono predefinito dei servizi di audioconferenza per un organizzatore o un utente della riunione utilizzando [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps), imposta i **`ServiceNumber`** parametri o **`TollFreeServiceNumber`** del cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) su uno dei numeri disponibili.

## <a name="related-topics"></a>Argomenti correlati

[Prova o acquista i servizi di audioconferenza in Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiare i numeri di telefono del bridge per i servizi di audioconferenza](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
