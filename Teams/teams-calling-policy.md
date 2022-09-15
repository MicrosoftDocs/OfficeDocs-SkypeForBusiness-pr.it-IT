---
title: 'Criteri per le chiamate in Microsoft Teams: funzionalità di chiamata e inoltro di chiamata'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti a criteri di chiamata personalizzati in Microsoft Teams, nonché a varie impostazioni dei criteri di chiamata.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c785a6860c1ea45200253e9d2530a80e9dd28f6
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67708296"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Chiamate e inoltro di chiamata in Teams

In Microsoft Teams, i criteri di chiamata controllano le funzionalità di chiamata e inoltro di chiamata disponibili per gli utenti. I criteri per le chiamate determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via.

È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente o creare e assegnare criteri personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare criteri di chiamata personalizzati

Seguire questa procedura per creare criteri di chiamata personalizzati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Criteri per le chiamate** **vocali** > .
2. Selezionare **Aggiungi**.
3. Attiva o disattiva le funzionalità che vuoi usare nei criteri per le chiamate.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **Abilitato** o **Controllato dall'utente**. Per impedire il routing alla segreteria telefonica, selezionare **Disabilitato**.
5. Selezionare **Salva**.

## <a name="edit-a-calling-policy"></a>Modificare i criteri per le chiamate

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams selezionare **Criteri per le chiamate** **vocali** > .
2. Fare clic accanto al criterio da modificare e quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Assegnare criteri di chiamata personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Impostazioni dei criteri per le chiamate

Ecco le impostazioni che è possibile configurare per i criteri di chiamata.

### <a name="make-private-calls"></a>Effettuare chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in Teams. Disattiva questa opzione per disattivare tutte le funzionalità di chiamata in Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono chiamare contemporaneamente un'altra persona.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La segreteria telefonica è disponibile per il routing delle chiamate in ingresso

Questa impostazione consente di inviare le chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

- **Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.
- **Disabili**  La segreteria telefonica non è disponibile per le chiamate in ingresso.
- **Controllo dell'utente** Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradate ai gruppi di chiamate

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delega per le chiamate in ingresso e in uscita

Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali hanno autorizzazioni delegate. Per altre informazioni, vedere [Condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitare il bypass a pagamento e inviare chiamate tramite PSTN

L'impostazione di questa opzione su **Attivato** invierà chiamate tramite PSTN e incorrerà in costi anziché inviarli attraverso la rete e bypassando i pedaggi.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Occupato è disponibile durante una chiamata

Occupato su occupato (Opzioni occupato) consente di configurare come vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o possono essere instradate di conseguenza alle impostazioni senza risposta dell'utente. È possibile abilitare le opzioni relative alla disponibilità a livello di tenant o di utente. Indipendentemente da come sono configurate le opzioni di occupato, agli utenti in una chiamata o conferenza o a quelli con chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze. Questa impostazione è disabilitata per impostazione predefinita.

### <a name="web-pstn-calling"></a>Chiamate PSTN Web

Questa impostazione consente agli utenti di chiamare numeri PSTN usando il client Web di Teams.

### <a name="automatically-answer-incoming-meeting-invites"></a>Rispondere automaticamente agli inviti alle riunioni in arrivo

Questa impostazione controlla se gli inviti alle riunioni in arrivo ricevono automaticamente una risposta. Per impostazione predefinita l'opzione è disattivata. Tenere presente che questa impostazione si applica solo agli inviti alle riunioni in arrivo. Non si applica ad altri tipi di chiamate.

### <a name="allow-music-on-hold"></a>Consentire l'attesa di musica

Questa impostazione consente di attivare o disattivare la musica in attesa quando un chiamante PSTN è messo in attesa. È attivata per impostazione predefinita. Questa impostazione non è applicabile alle funzionalità del parcheggio di chiamata e del delegato del responsabile.

### <a name="allow-sip-devices-calling"></a>Consenti chiamate ai dispositivi SIP

Questa impostazione consente agli utenti di utilizzare un dispositivo SIP per effettuare e ricevere chiamate.

### <a name="spam-filtering"></a>Filtro della posta indesiderata

Questa impostazione consente di controllare il tipo di filtro della posta indesiderata disponibile per le chiamate in arrivo.

### <a name="call-recording-live-captions-and-transcription"></a>Registrazione delle chiamate, sottotitoli in tempo reale e trascrizione

Queste impostazioni consentono di controllare se la registrazione delle chiamate, i sottotitoli in tempo reale e la trascrizione sono disponibili per gli utenti.

## <a name="related-articles"></a>Articoli correlati

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
