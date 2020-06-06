---
title: Criteri di chiamata in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informazioni su come creare, modificare e aggiungere utenti ai criteri per le chiamate personalizzate in Microsoft teams, nonché varie impostazioni dei criteri di chiamata.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592861"
---
<a name="calling-policies-in-microsoft-teams"></a>Criteri di chiamata in Microsoft Teams
===================================

In Microsoft teams, i criteri di chiamata controllano quali funzionalità di inoltro delle chiamate e di chiamata sono disponibili per gli utenti. I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, inoltrare chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via. Viene creato automaticamente un criterio globale predefinito, ma gli amministratori possono anche creare e assegnare criteri di chiamata personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare un criterio di chiamata personalizzato

Seguire questa procedura per creare un criterio di chiamata personalizzato.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**scegliere criteri per le  >  **chiamate**vocali.
2. Selezionare **Aggiungi**.
3. Attivare o disattivare le caratteristiche che si desidera utilizzare nei criteri di chiamata.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **abilitato** o **controllato dall'utente**. Per impedire il routing alla segreteria telefonica, selezionare **disabled**.
5. Selezionare **Salva**.

## <a name="modify-an-existing-calling-policy"></a>Modificare un criterio di chiamata esistente

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le **Voice**  >  **chiamate**vocali.
2. Fare clic su accanto al criterio che si vuole modificare e quindi selezionare **modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-calling-policy-to-users"></a>Assegnare un criterio di chiamata personalizzato agli utenti

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. In **criteri di chiamata**selezionare il criterio di chiamata che si vuole assegnare e quindi fare clic su **applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Applica**.  

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**scegliere criteri per le  >  **chiamate**vocali.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo avere aggiunto gli utenti, selezionare **Salva**.

## <a name="calling-policy-settings"></a>Impostazioni dei criteri di chiamata

Ecco le impostazioni che è possibile configurare per i criteri di chiamata.

### <a name="make-private-calls"></a>Effettuare chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in teams. Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono chiamare un'altra persona contemporaneamente. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono chiamare contemporaneamente un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>La segreteria telefonica è disponibile per il routing delle chiamate in ingresso

Questa impostazione consente l'invio di chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

- **Abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso. 
- **Disabilitata**  La segreteria telefonica non è disponibile per le chiamate in ingresso. 
- **Utente controllato** Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradate a gruppi di chiamate 

> [!Include [feature preview](includes/preview-feature.md)]

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Consentire la delega per le chiamate in ingresso e in uscita

> [!Include [feature preview](includes/preview-feature.md)]

Questa impostazione consente alle chiamate in ingresso di essere instradate a delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali sono state delegate le autorizzazioni. Per altre informazioni, vedere [condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN 

Se si imposta questa opzione **su** attivato, le chiamate verranno inviate tramite la rete PSTN e incorreremo in spese piuttosto che inviarle tramite il network e aggirare i pedaggi.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>La disponibilità di occupato è disponibile durante una chiamata

Occupato in occupato (le opzioni di occupato) è una nuova impostazione che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato. È possibile abilitare le opzioni di occupato a livello di tenant o a livello di utente. Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o di una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze. Questa impostazione è disabilitata per impostazione predefinita.

### <a name="allow-web-pstn-calling"></a>Consenti chiamate PSTN Web

Questa impostazione consente agli utenti di chiamare numeri PSTN tramite il client Web teams.

### <a name="allow-music-on-hold"></a>Consenti musica in attesa

Questa impostazione consente di attivare o disattivare la musica in attesa quando un chiamante PSTN viene posizionato in attesa. È attivato per impostazione predefinita. Questa impostazione non si applica alle caratteristiche di Call Park e boss delegate ed è attualmente disponibile solo tramite PowerShell.

## <a name="see-also"></a>Vedere anche

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
