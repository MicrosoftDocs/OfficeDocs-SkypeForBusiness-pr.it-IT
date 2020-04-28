---
title: Criteri di chiamata in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
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
ms.openlocfilehash: a94bf072aa4db0ba0b3f65fb5340c22ab09581e4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43914062"
---
<a name="calling-policies-in-microsoft-teams"></a>Criteri di chiamata in Microsoft Teams
===================================

In Microsoft teams, i criteri di chiamata controllano quali funzionalità di inoltro delle chiamate e di chiamata sono disponibili per gli utenti. I criteri di chiamata determinano se un utente può effettuare chiamate private, usare l'inoltro di chiamata o lo squillo simultaneo ad altri utenti o numeri di telefono esterni, inoltrare chiamate alla segreteria telefonica, inviare chiamate a gruppi di chiamate, usare la delega per le chiamate in ingresso e in uscita e così via. Viene creato automaticamente un criterio globale predefinito, ma gli amministratori possono anche creare e assegnare criteri di chiamata personalizzati.

## <a name="create-a-custom-calling-policy"></a>Creare un criterio di chiamata personalizzato

Seguire questa procedura per creare un criterio di chiamata personalizzato.

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .
2. Selezionare **nuovo criterio**.
3. Attivare le funzionalità che si desidera utilizzare nei criteri di chiamata. Tutte le selezioni sono **disattivate** per impostazione predefinita.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **sempre abilitato** o **controllato dall'utente**. Per impedire il routing alla segreteria telefonica, selezionare **sempre disabilitato**.
5. Selezionare **Salva**.

## <a name="modify-an-existing-calling-policy"></a>Modificare un criterio di chiamata esistente

Seguire questa procedura per modificare un criterio di chiamata esistente.

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .
2. Fare clic su accanto al criterio che si vuole modificare e quindi selezionare **modifica**.
3. Attivare le funzionalità che si desidera utilizzare nei criteri di chiamata. Tutte le selezioni sono **disattivate** per impostazione predefinita.
4. Per controllare se gli utenti possono instradare le chiamate in ingresso alla segreteria telefonica, selezionare **sempre abilitato** o **controllato dall'utente**. Per impedire il routing alla segreteria telefonica, selezionare **sempre disabilitato**.
5. Selezionare **Salva**.

## <a name="assign-a-calling-policy-to-a-user"></a>Assegnare un criterio di chiamata a un utente

Seguire questa procedura per assegnare un criterio di chiamata personalizzato a un utente.

1. Nell'interfaccia di amministrazione di Microsoft teams selezionare criteri per le**chiamate** **vocali** > .
2. Fare clic su accanto al nome del criterio per selezionarlo e quindi selezionare **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare il nome dell'utente. È necessario immettere almeno tre caratteri.
4. Selezionare il nome dell'utente e quindi fare clic su **Aggiungi**.
5. Selezionare **Salva**.

## <a name="calling-policy-settings"></a>Impostazioni dei criteri di chiamata

Usare le impostazioni seguenti per creare criteri di chiamata personalizzati.

### <a name="user-can-make-private-calls"></a>L'utente può effettuare chiamate private

Questa impostazione controlla tutte le funzionalità di chiamata in teams. Disattivare questa opzione per disattivare tutte le funzionalità di chiamata in teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>Inoltro di chiamata e squillo simultaneo ad altri utenti

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate ad altri utenti o possono chiamare un'altra persona contemporaneamente. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un numero esterno o possono chiamare contemporaneamente un numero esterno.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>La segreteria telefonica è disponibile per il routing delle chiamate in ingresso agli utenti

Questa impostazione consente l'invio di chiamate in ingresso alla segreteria telefonica. Le opzioni valide sono:

   - **Sempre abilitato** La segreteria telefonica è sempre disponibile per le chiamate in ingresso. 
   - **Sempre disabilitato**  La segreteria telefonica non è disponibile per le chiamate in ingresso. 
   - **Utente controllato**. Gli utenti possono determinare se vogliono che la segreteria telefonica sia disponibile.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>Le chiamate in ingresso possono essere instradate a gruppi di chiamate 

> [!Include [feature preview](includes/preview-feature.md)]

Questa impostazione controlla se le chiamate in arrivo possono essere inoltrate a un gruppo di chiamate.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>Consentire la delega per le chiamate in ingresso e in uscita

> [!Include [feature preview](includes/preview-feature.md)]

Questa impostazione consente alle chiamate in ingresso di essere instradate a delegati, consentendo ai delegati di effettuare chiamate in uscita per conto degli utenti per i quali sono state delegate le autorizzazioni. Per altre informazioni, vedere [condividere una linea telefonica con un delegato](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN 

Se si imposta questa opzione **su** attivato, le chiamate verranno inviate tramite la rete PSTN e incorreremo in spese piuttosto che inviarle tramite il network e aggirare i pedaggi.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>La disponibilità di occupato è disponibile durante una chiamata

Occupato in occupato (opzioni di occupato)) è una nuova impostazione nei criteri di chiamata dei team che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa. Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato. È possibile abilitare le opzioni di occupato a livello di tenant o a livello di utente. Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o di una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze. Questa impostazione è disabilitata per impostazione predefinita.

### <a name="allow-music-on-hold"></a>Consenti musica in attesa

Questa impostazione consente di attivare o disattivare la musica in attesa quando un chiamante PSTN viene posizionato in attesa. È attivata per impostazione predefinita. Questa impostazione non si applica alle caratteristiche di Call Park e boss delegate ed è attualmente disponibile solo tramite PowerShell. 

## <a name="see-also"></a>Vedere anche

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
