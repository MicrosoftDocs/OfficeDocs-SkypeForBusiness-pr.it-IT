---
title: 'Criteri di chiamata in Microsoft Teams: funzionalità di chiamata e inoltro di chiamata'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti ai criteri di chiamata personalizzati in Microsoft Teams, oltre a varie impostazioni dei criteri di chiamata.
localization_priority: Normal
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
ms.openlocfilehash: f4502d76bbb2e12f38ba79d0848ecd06739417cc
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53596607"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Chiamate e inoltro di chiamata in Teams

In Microsoft Teams, i criteri di chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti. I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via.

È possibile usare i criteri globali (predefiniti a livello di organizzazione) creati automaticamente oppure creare e assegnare criteri personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare criteri di chiamata personalizzati

Seguire questa procedura per creare un criterio di chiamata personalizzato.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a Criteri  >  **per le chiamate vocali.**
2. Selezionare **Aggiungi**.
3. Attivare o disattivare le funzionalità da usare nei criteri di chiamata.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **Abilitato** o **Controllato dall'utente.** Per impedire l'instradamento alla segreteria telefonica, selezionare **Disabilitato.**
5. Selezionare **Salva**.

## <a name="edit-a-calling-policy"></a>Modificare un criterio di chiamata

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare **Criteri per le chiamate**  >  **vocali.**
2. Fare clic accanto al criterio da modificare e quindi selezionare **Modifica.**
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Assegnare un criterio di chiamata personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Impostazioni dei criteri di chiamata

Ecco le impostazioni che è possibile configurare per i criteri di chiamata.

### <a name="make-private-calls"></a>Effettuare chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in Teams. Disattiva questa opzione per disattivare tutte le funzionalità di chiamata in Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La segreteria telefonica è disponibile per il routing delle chiamate in ingresso

Questa impostazione consente di inviare chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

- **Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.
- **Disabilitato**  La segreteria telefonica non è disponibile per le chiamate in ingresso.
- **Controllato dall'utente** Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradati ai gruppi di chiamate 

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Consentire la delega per le chiamate in ingresso e in uscita

Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per cui hanno autorizzazioni delegate. Per altre informazioni, vedere [Condividere una linea telefonica con un delegato.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitare il bypass a pedaggio e inviare chiamate tramite PSTN 

Se si imposta questa opzione **su Attivata,** le chiamate verranno inviate tramite PSTN e verranno sostenute spese invece di inviarle tramite la rete e ignorare i pedaggi.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Occupato su Occupato è disponibile durante una chiamata

Occupato (Opzioni occupato) è una nuova impostazione che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o instradate di conseguenza alle impostazioni senza risposta dell'utente. È possibile abilitare le opzioni di disponibilità a livello di tenant o a livello di utente. Indipendentemente dal modo in cui vengono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non possono avviare nuove chiamate o conferenze. Questa impostazione è disabilitata per impostazione predefinita.

### <a name="allow-web-pstn-calling"></a>Consenti chiamate PSTN Web

Questa impostazione consente agli utenti di chiamare i numeri PSTN usando Teams web client.

### <a name="allow-music-on-hold"></a>Consentire la musica in attesa

Questa impostazione consente di attivare o disattivare il blocco della musica quando un chiamante PSTN viene sospeso. È attivata per impostazione predefinita. Questa impostazione non si applica alle funzionalità di parcheggio di chiamata e delegato del responsabile ed è attualmente disponibile solo tramite PowerShell.

## <a name="related-topics"></a>Argomenti correlati

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
