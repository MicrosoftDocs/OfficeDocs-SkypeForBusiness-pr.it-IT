---
title: Criteri per le chiamate in Microsoft Teams
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti a criteri di chiamata personalizzati in Microsoft Teams, nonché varie impostazioni dei criteri di chiamata.
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
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465296"
---
<a name="calling-policies-in-microsoft-teams"></a>Criteri per le chiamate in Microsoft Teams
===================================

In Microsoft Teams, i criteri di chiamata controllano quali funzionalità di chiamata e inoltro di chiamata sono disponibili per gli utenti. I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamata, utilizzare la delega per le chiamate in entrata e in uscita e così via.

È possibile usare il criterio globale (impostazione predefinita a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare un criterio di chiamata personalizzato

Seguire questa procedura per creare un criterio di chiamata personalizzato.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Criteri per le chiamate**  >  **vocali.**
2. Selezionare **Aggiungi**.
3. Attivare o disattivare le funzionalità da usare nel criterio di chiamata.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, seleziona **Abilitato** o **Controllato dall'utente.** Per impedire l'instradamento alla segreteria telefonica, seleziona **Disabilitato.**
5. Selezionare **Salva**.

## <a name="edit-a-calling-policy"></a>Modificare un criterio di chiamata

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, seleziona **Criteri per le chiamate**  >  **vocali.**
2. Fare clic accanto al criterio da modificare e quindi selezionare **Modifica.**
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Assegnare un criterio di chiamata personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Impostazioni dei criteri di chiamata

Ecco le impostazioni che è possibile configurare per i criteri di chiamata.

### <a name="make-private-calls"></a>Effettuare chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in Teams. Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La segreteria telefonica è disponibile per l'instradamento delle chiamate in entrata

Questa impostazione consente l'invio delle chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

- **Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in entrata.
- **Disabilitato**  La segreteria telefonica non è disponibile per le chiamate in entrata.
- **Utente controllato** Gli utenti possono stabilire se vogliono che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradati ai gruppi di chiamata 

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamata.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Consentire la delega per le chiamate in ingresso e in uscita

Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali hanno autorizzazioni delegate. Per altre informazioni, vedere [Condividere una linea telefonica con un delegato.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Evitare il bypass a pedaggio e inviare chiamate tramite PSTN 

Impostando questa opzione **su On,** le chiamate vengono inviate tramite PSTN e vengono sostenute le chiamate invece di inviarle tramite la rete, senza superare i caselli a pagamento.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>Occupato in Stato di occupato è disponibile durante una chiamata

Occupato in Disponibilità (Opzioni occupato) è una nuova impostazione che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato. È possibile abilitare le opzioni di occupato a livello di tenant o di utente. Indipendentemente da come sono configurate le opzioni di occupato, gli utenti in una chiamata o conferenza o gli utenti con chiamata in attesa non possono avviare nuove chiamate o conferenze. Questa impostazione è disabilitata per impostazione predefinita.

### <a name="allow-web-pstn-calling"></a>Consenti chiamate PSTN Web

Questa impostazione consente agli utenti di chiamare i numeri PSTN utilizzando il client Web di Teams.

### <a name="allow-music-on-hold"></a>Consenti musica durante l'attesa

Questa impostazione consente di attivare o disattivare l'attesa di musica quando un chiamante PSTN è in attesa. È attivata per impostazione predefinita. Questa impostazione non si applica alle funzionalità per i delegati del parco chiamate e del responsabile ed è attualmente disponibile solo tramite PowerShell.

## <a name="related-topics"></a>Argomenti correlati

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)
