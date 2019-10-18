---
title: Provare o acquistare servizi di audioconferenza in Office 365 per Microsoft Teams
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.CpcGettingStarted
ms.custom:
- Audio Conferencing
description: 'Vedi come provare o acquistare le licenze di Audioconferenza (conferenze PSTN) per Office 365 per configurare le conferenze telefoniche a cui gli utenti possono connettersi. '
ms.openlocfilehash: ce20d72ff7d4d797c8e0689472cd483c5f06036b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571492"
---
# <a name="try-or-purchase-audio-conferencing-in-office-365-for-microsoft-teams"></a>Provare o acquistare servizi di audioconferenza in Office 365 per Microsoft Teams

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Microsoft teams include la funzionalità di conferenza audio per questa situazione. Gli utenti possono chiamare riunioni di Microsoft teams usando un telefono, invece di usare l'app Microsoft teams su un dispositivo mobile o un PC.

È necessario configurare solo i servizi di audioconferenza per gli utenti che intendono pianificare o condurre riunioni. Le persone che partecipano alla riunione tramite telefono non hanno bisogno che le venga assegnata alcuna licenza o di altre impostazioni.

Per informazioni sui prezzi, consulta [Prezzi per Audioconferenza](https://products.office.com/skype-for-business/audio-conferencing#Requirements).

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>Passaggio 1: acquistare e assegnare licenze per i servizi di audioconferenza

Per eseguire questa procedura è necessario essere un amministratore [globale o un amministratore della fatturazione](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>Per acquistare e assegnare licenze utente di Audioconferenza:

1. Verificare se i servizi di **audioconferenza** sono disponibili nel proprio paese/area geografica. [Disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Ottenere le licenze di **Audioconferenza**. Se vuoi:

   - **Provare** prima di acquistarlo: è possibile iscriversi a una versione di valutazione gratuita di Office 365 Enterprise E5 che include servizi di audioconferenza. Consulta [Versione di valutazione di Office 365 Enterprise E5](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3).

   - **Acquista**: Vedi [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

3. [Assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article//997596b5-4173-4627-b915-36abac6786dc) che hai acquistato per gli utenti dell'organizzazione che intendono pianificare o condurre riunioni.

4. Se hai acquistato licenze del componente aggiuntivo Audioconferenza e licenze di Credito per la comunicazione, assegna anche quelle. Per istruzioni, vedere [assegnare licenze di Microsoft teams](assign-teams-licenses.md).

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>Per acquistare e assegnare licenze Audioconferenza con tariffa al minuto:

Se si è un cliente di licenze a volume, è possibile ottenere le licenze di Audioconferenza con tariffa al minuto. Per ulteriori informazioni sulle licenze di Audioconferenza con tariffa al minuto, consulta [Audioconferenza con tariffa al minuto](audio-conferencing-pay-per-minute.md). 
  
1. Verificare se i servizi di **audioconferenza** sono disponibili nel proprio paese/area geografica. [Disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Ottenere le licenze di **Audioconferenza**. Per acquistare le licenze di tariffa al minuto, contattare il proprio rappresentante dell'account.
    
3. [Configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md) per l'organizzazione. Per impostare il Credito per la comunicazione, consulta [Cosa è il Credito per la comunicazione?](what-are-communications-credits.md)
    
    > [!IMPORTANT]
    > Se i Crediti per la comunicazione non sono stati impostati, l'Audioconferenza non funzionerà per tutti gli utenti con le licenze di tariffa al minuto.

4. [Assegnare o rimuovere licenze di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) che hai acquistato per gli utenti dell'organizzazione che intendono pianificare o condurre riunioni.

    > [!NOTE]
    > Se si dispongono delle licenze di tariffa al minuto per Audioconferenza, non è necessario assegnare licenze di Credito per la comunicazione separatamente per ogni utente per l'utilizzo di servizi di Audioconferenza (potrebbe ancora essere necessario assegnarli per altri servizi).

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>Passo 2: Impostare il provider di servizi di audioconferenza per gli utenti che conducono o pianificano riunioni

Quando si assegna una licenza di audioconferenza per gli utenti dell'organizzazione che non dispongono di Skype for business integrato con un provider di servizi di audioconferenza di terze parti, sono tutti impostati e pronti per l' **accesso** . (Non è necessario impostare il provider di audioconferenza.)

Se gli utenti sono abilitati con un provider di servizi di audioconferenza di terze parti, è necessario modificare il provider di tali utenti in Microsoft. Per modificare il provider per un utente, vedere [assegnare Microsoft come provider di servizi di audioconferenza](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="step-3-other-admin-tasks"></a>Passo 3: Altri compiti dell'amministratore

La procedura seguente è **facoltativa**, ma molti amministratori preferiscono eseguirla:

1. [Personalizzare gli inviti alle riunioni](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). I numeri di accesso impostati per l'utente verranno aggiunti automaticamente agli inviti alle riunioni inviati ai partecipanti. Tuttavia, puoi aggiungere una guida o collegamenti legali personalizzati, un messaggio di testo e una piccola immagine aziendale.

2. [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites-in-teams.md). Questo è il numero di telefono che verrà visualizzato nelle riunioni pianificate dall'utente.

3. [Impostare le lingue dell'operatore automatico per Audioconferenza](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) che utilizza l'operatore automatico di Audioconferenza per salutare un utente quando quest'ultimo chiama un numero di telefono di audioconferenza. Questo passaggio si applica solo se si utilizza Microsoft come provider di audioconferenza.

4. [Impostare la lunghezza del PIN per le riunioni di audioconferenza](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).


> [!NOTE]
> Questa funzionalità non è ancora disponibile per i clienti con Office 365 gestito da 21Vianet in Cina. Per ulteriori informazioni, consulta [Informazioni su Office 365 gestito da 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

## <a name="related-topics"></a>Argomenti correlati

[Abilitare i team nell'organizzazione](office-365-set-up.md)

[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing-in-teams.md)

[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
