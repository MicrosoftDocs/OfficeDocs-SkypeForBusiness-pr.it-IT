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
ms.openlocfilehash: e38a566e025c711a9b17a050137e67af7507e63d5c5e829ba4448ee4a1577790
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309245"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>Chiamata e inoltro di chiamata in Teams

In Microsoft Teams, i criteri di chiamata controllano le funzionalità di chiamata e inoltro di chiamata disponibili per gli utenti. I criteri di chiamata determinano se un utente può effettuare chiamate private, utilizzare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, instradare le chiamate alla segreteria telefonica, inviare chiamate ai gruppi di chiamate, utilizzare la delega per le chiamate in ingresso e in uscita e così via.

È possibile utilizzare il criterio globale (predefinito a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare criteri di chiamata personalizzati

Seguire questa procedura per creare un criterio di chiamata personalizzato.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Criteri per**  >  **chiamate vocali.**
2. Selezionare **Aggiungi**.
3. Attivare o disattivare le funzionalità da usare nei criteri di chiamata.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **Abilitato** o **Controllato dall'utente**. Per impedire l'inoltro alla segreteria telefonica, selezionare **Disabilitato**.
5. Selezionare **Salva**.

## <a name="edit-a-calling-policy"></a>Modificare i criteri di chiamata

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione selezionare **Criteri di chiamata**  >  **vocale.**
2. Fare clic accanto al criterio che si desidera modificare e quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-calling-policy-to-users"></a>Assegnare criteri di chiamata personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>Impostazioni dei criteri di chiamata

Ecco le impostazioni che puoi configurare per i criteri di chiamata.

### <a name="make-private-calls"></a>Effettua chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in Teams. Disattivare questa opzione per disabilitare tutte le funzionalità di chiamata in Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo ai numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono squillare contemporaneamente a un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La segreteria telefonica è disponibile per l'instradamento delle chiamate in ingresso

Questa impostazione consente di inviare le chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

- **Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso.
- **Disabilitato**  La segreteria telefonica non è disponibile per le chiamate in ingresso.
- **Controllato dall'utente** Gli utenti possono determinare se desiderano che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradate ai gruppi autorizzati alla risposta

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.

### <a name="delegation-for-inbound-and-outbound-calls"></a>Delega per le chiamate in ingresso e in uscita

Questa impostazione consente di instradare le chiamate in ingresso ai delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali dispongono delle autorizzazioni delegate. Per ulteriori informazioni, vedere [Condividere una linea telefonica con un delegato.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedisci il bypass dei numeri a tariffa e invia le chiamate tramite PSTN 

Se si imposta questo valore su **On,** le chiamate verranno inviate tramite PSTN e verranno effettuate tariffe, anziché inviarle attraverso la rete e ignorare i pedaggi.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>Occupato su occupato è disponibile quando in una chiamata

Busy on Busy (Opzioni occupato) consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o possono essere instradate di conseguenza alle impostazioni senza risposta dell'utente. È possibile abilitare le opzioni di occupato a livello di tenant o a livello di utente. Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o a quelli con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze. L'impostazione è disabilitata per impostazione predefinita.

### <a name="web-pstn-calling"></a>Chiamate PSTN Web

Questa impostazione consente agli utenti di chiamare i numeri PSTN utilizzando il client Teams Web.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>Agli inviti alle riunioni in arrivo viene automaticamente risposto

Questa impostazione controlla se agli inviti alle riunioni in arrivo viene automaticamente risposto. È disattivato per impostazione predefinita. Tenere presente che questa impostazione si applica solo agli inviti alle riunioni in arrivo. Non si applica ad altri tipi di chiamate.

### <a name="allow-music-on-hold"></a>Consenti musica in attesa

Questa impostazione consente di attivare o disattivare la musica di attesa quando un chiamante PSTN viene messo in attesa. L'impostazione è attivata per impostazione predefinita. Questa impostazione non si applica alle funzionalità di parcheggio di chiamata e delegato del capo ed è attualmente disponibile solo tramite PowerShell.

## <a name="related-articles"></a>Articoli correlati

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Assegnare criteri agli utenti in Teams](assign-policies.md)
