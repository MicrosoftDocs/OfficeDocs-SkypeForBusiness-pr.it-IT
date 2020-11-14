---
title: Provare o acquistare servizi di audioconferenza in Microsoft 365 per Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: 'Informazioni su come provare o acquistare licenze per servizi di audioconferenza (servizi di conferenza PSTN) per Microsoft 365 o Office 365 per configurare le chiamate in conferenza a cui gli utenti possono effettuare la chiamata. '
ms.openlocfilehash: 8f2aa7d8fdbf6c3088c483e4d5f941625e2a8da8
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031272"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>Provare o acquistare servizi di audioconferenza in Microsoft 365 per Microsoft Teams

A volte le persone all'interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft teams include la funzionalità di conferenza audio per questa situazione. Gli utenti possono chiamare riunioni di Microsoft teams usando un telefono, invece di usare l'app Microsoft teams su un dispositivo mobile o un PC.

È necessario configurare solo i servizi di audioconferenza per gli utenti che intendono pianificare o condurre riunioni. Le persone che partecipano alla riunione tramite telefono non hanno bisogno che le venga assegnata alcuna licenza o di altre impostazioni.

Per informazioni sui prezzi, consulta [Prezzi per Audioconferenza](https://products.office.com/skype-for-business/audio-conferencing#Requirements).

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>Passaggio 1: acquistare e assegnare licenze per i servizi di audioconferenza

Per eseguire questa procedura è necessario essere un amministratore [globale o un amministratore della fatturazione](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>Per acquistare e assegnare licenze per i servizi di audioconferenza degli utenti

1. Verificare se i servizi di **audioconferenza** sono disponibili nel proprio paese/area geografica. [Disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

2. Ottenere le licenze di **Audioconferenza**. Se vuoi:

   - **Provare** prima di acquistarlo: è possibile iscriversi a una versione di valutazione gratuita di Office 365 Enterprise E5 che include servizi di audioconferenza. Consulta [Versione di valutazione di Office 365 Enterprise E5](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3).

   - **Acquista** : vedere [licenze per i componenti aggiuntivi Microsoft Team] https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) .

3. [Assegnare le licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.

4. Se hai acquistato licenze del componente aggiuntivo Audioconferenza e licenze di Credito per la comunicazione, assegna anche quelle. Per istruzioni, vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>Per acquistare e assegnare licenze per i servizi di audioconferenza in pay-per-minute

Se si è un cliente di licenze a volume, è possibile ottenere le licenze di Audioconferenza con tariffa al minuto. Per ulteriori informazioni sulle licenze di Audioconferenza con tariffa al minuto, consulta [Audioconferenza con tariffa al minuto](audio-conferencing-pay-per-minute.md).
  
1. Verificare se i servizi di **audioconferenza** sono disponibili nel proprio paese/area geografica. [Disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

2. Ottenere le licenze di **Audioconferenza**. Per acquistare le licenze di tariffa al minuto, contattare il proprio rappresentante dell'account.

3. [Configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md) per l'organizzazione. Per impostare il Credito per la comunicazione, consulta [Cosa è il Credito per la comunicazione?](what-are-communications-credits.md)

    > [!IMPORTANT]
    > Se i Crediti per la comunicazione non sono stati impostati, l'Audioconferenza non funzionerà per tutti gli utenti con le licenze di tariffa al minuto.

4. [Assegnare le licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.

    > [!NOTE]
    > Se si hanno licenze pay-per-minute per i servizi di audioconferenza, è necessario assegnare una licenza per i crediti di comunicazione separatamente anche a ogni utente.

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>Passo 2: Impostare il provider di servizi di audioconferenza per gli utenti che conducono o pianificano riunioni

Quando si assegna una licenza di audioconferenza per gli utenti dell'organizzazione che non dispongono di Skype for business integrato con un provider di servizi di audioconferenza di terze parti, sono tutti impostati e pronti per l' **accesso** . (Non è necessario impostare il provider di audioconferenza.)

Se gli utenti sono abilitati con un provider di servizi di audioconferenza di terze parti, è necessario modificare il provider di tali utenti in Microsoft. Per modificare il provider per un utente, vedere [assegnare Microsoft come provider di servizi di audioconferenza](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="step-3-other-admin-tasks"></a>Passo 3: Altri compiti dell'amministratore

La procedura seguente è **facoltativa** , ma molti amministratori preferiscono eseguirla:

1. [Personalizzare gli inviti alle riunioni](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). I numeri di accesso impostati per l'utente verranno aggiunti automaticamente agli inviti alle riunioni inviati ai partecipanti. Tuttavia, puoi aggiungere una guida o collegamenti legali personalizzati, un messaggio di testo e una piccola immagine aziendale.

2. [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites-in-teams.md). Questo è il numero di telefono che verrà visualizzato nelle riunioni pianificate dall'utente.

3. [Impostare le lingue dell'operatore automatico per Audioconferenza](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che utilizza l'operatore automatico di Audioconferenza per salutare un utente quando quest'ultimo chiama un numero di telefono di audioconferenza. Questo passaggio si applica solo se si utilizza Microsoft come provider di audioconferenza.

4. [Impostare la lunghezza del PIN per le riunioni di audioconferenza](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).

> [!NOTE]
> Questa funzionalità non è ancora disponibile per i clienti con Office 365 gestito da 21Vianet in Cina. Per ulteriori informazioni, consulta [Informazioni su Office 365 gestito da 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

## <a name="related-topics"></a>Argomenti correlati

[Abilitare i team nell'organizzazione](office-365-set-up.md)

[Numeri di telefono per Audioconferenza](phone-numbers-for-audio-conferencing-in-teams.md)

[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
