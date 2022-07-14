---
title: Configurare la funzionalità Chiamami per gli utenti
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare la funzionalità Chiama in Teams in modo che gli utenti possano partecipare alla parte audio tramite telefono quando usano il computer per l'audio potrebbe non essere possibile.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794534"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurare la funzionalità Chiamami per gli utenti

In Microsoft Teams, la funzione **Chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione tramite telefono. Questo è utile negli scenari in cui l'uso di un computer per l'audio potrebbe non essere possibile. Gli utenti ricevono la parte audio della riunione tramite il cellulare o la linea fissa e la parte di contenuto della riunione, ad esempio quando un altro partecipante alla riunione&mdash;condivide lo schermo o riproduce un video&mdash;tramite computer.

> [!IMPORTANT]
> 
> Nei periodi in cui il volume di riunioni è elevato (come abbiamo sperimentato durante l'epidemia di COVID-19), si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante <strong>Partecipa alla riunione di Teams</strong> anziché chiamare utilizzando i numeri di conferenza PSTN o utilizzando <strong>Chiamami a</strong>. In questo modo la qualità dell’audio è migliore durante i periodi in cui il numero elevato delle riunioni causa una congestione della rete PSTN.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>L'esperienza utente

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Partecipare a una riunione usando il telefono per l'audio

Fare clic su **Partecipa** per partecipare a una riunione, quindi su **Audio telefono** nella schermata **Scegli le opzioni audio e video** e fare clic su **Partecipa ora**. Da qui, gli utenti possono effettuare la chiamata alla riunione e parteciparvi oppure effettuare l'accesso manualmente alla riunione.

![Schermata dell'opzione Audio telefono.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Consentire la chiamata alla riunione di Teams**

Nella schermata **Usa telefono per l'audio**, l'utente immette il proprio numero di telefono e quindi fa clic su **Chiama.** La riunione chiama l'utente e vi partecipa.

![Screenshot dell'opzione Chiama nella schermata Usa telefono per l'audio.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Effettuare l'accesso manualmente**

Un altro modo per partecipare consiste nell'accedere direttamente alla riunione. Nella schermata **Usa telefono per l'audio** , fai clic su **Accedi manualmente** per ottenere un elenco dei numeri di telefono da usare per accedere alla riunione.

![Schermata dell'opzione Componi manualmente.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Ricevere una richiamata quando si verifica un problema con l'audio durante una riunione

Se un utente riscontra problemi audio durante l'uso del computer durante una riunione, può passare facilmente all'uso del telefono per l'audio. Teams rileva quando si verifica un problema audio o del dispositivo e reindirizza l'utente all'uso del telefono visualizzando un'opzione **Richiamami** .

Ecco un esempio del messaggio e dell'opzione **Richiama che** viene visualizzata quando Teams non rileva un microfono.

![Screenshot dell'opzione Richiama.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L'utente fa clic su **Richiamami**, che visualizza la schermata **Usa telefono per l'audio** . Da qui, possono immettere il proprio numero di telefono e fare in modo che la riunione di Teams chiami e partecipino alla riunione o compa esterno manualmente alla riunione.

## <a name="set-up-the-call-me-feature"></a>Configurare la funzionalità Chiama

Per abilitare la funzionalità Chiamami per gli utenti dell'organizzazione, è necessario configurare quanto segue:

- I servizi di audioconferenza sono abilitati per gli utenti dell'organizzazione che pianificare riunioni (organizzatori di riunioni). Per ulteriori informazioni, consulta [Configurare le audioconferenze per Teams](set-up-audio-conferencing-in-teams.md) e [Gestire le impostazioni dei servizi di audioconferenza per un utente in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- L'organizzatore della riunione può effettuare chiamate in uscita dalle riunioni. Per altre informazioni, vedere [Gestire le impostazioni delle audioconferenze per un utente in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Se l'organizzatore della riunione non ha abilitato la chiamata in uscita dalle riunioni, l'opzione **Audio telefono** nella schermata **Scegli le opzioni video e audio** non è disponibile per nessuno e gli altri utenti non possono ricevere una chiamata per partecipare alla riunione. Per gli utenti con chiamata in uscita abilitata, dopo aver effettuato l'accesso alla riunione, possono partecipare ad altri utenti componendo il proprio numero dall'icona **Mostra partecipanti** .
