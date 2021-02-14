---
title: Configurare la funzionalità Chiamami per gli utenti
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come impostare la funzionalità Chiama in Teams in modo che gli utenti possano accedere alla parte audio tramite telefono quando usano il computer per l'audio potrebbe non essere possibile.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821096"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurare la funzionalità Chiamami per gli utenti

In Microsoft Teams, la **funzione Chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione tramite telefono. Questo è utile negli scenari in cui potrebbe non essere possibile usare un computer per l'audio. Gli utenti ottengono la parte audio della riunione tramite telefono cellulare o rete mobile e il contenuto della riunione, ad esempio quando un altro partecipante alla riunione condivide lo schermo o riproduce un video tramite il &mdash; &mdash; proprio computer.

> [!IMPORTANT]
> 
> Nei periodi in cui il volume di riunioni è elevato (come abbiamo sperimentato durante l'epidemia di COVID-19), si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante <strong>Partecipa alla riunione di Teams</strong> anziché chiamare utilizzando i numeri di conferenza PSTN o utilizzando <strong>Chiamami a</strong>. In questo modo la qualità dell’audio è migliore durante i periodi in cui il numero elevato delle riunioni causa una congestione della rete PSTN. 

> [!IMPORTANT]
> Nel corso dell'epidemia di COVID-19, si consiglia agli utenti di partecipare alle riunioni facendo clic sul pulsante **Partecipa alla riunione di Teams** anziché chiamare utilizzando i numeri della conferenza PSTN o utilizzando **Chiamami a**</strong>. Ciò è principalmente dovuto alla congestione delle infrastrutture telefoniche dei paesi colpiti da COVID-19. Evitando le chiamate PSTN, la qualità audio sarà probabilmente migliore. 

## <a name="the-user-experience"></a>Esperienza utente

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Partecipare a una riunione tramite telefono per l'audio

Fare **clic** su Partecipa per partecipare a una riunione e quindi su **Audio telefono** nella schermata per la scelta delle impostazioni audio e **video.** Da qui, gli utenti possono effettuare la chiamata alla riunione e parteciparvi o accedere manualmente alla riunione.

![Schermata dell'opzione Audio telefono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Consentire la chiamata alla riunione di Teams**

Nella schermata **Usa il telefono per l'audio,** l'utente immette il suo numero di telefono e quindi fa clic su **Chiama.** La riunione chiama l'utente e lo partecipa alla riunione.

![Schermata dell'opzione Chiamami nella schermata Usa il telefono per l'audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Accesso manuale**

Un altro modo per partecipare è effettuare l'accesso diretto alla riunione. Nella schermata Usa il telefono  **per l'audio,** fai clic su Accesso esterno manualmente per ottenere un elenco di numeri di telefono da utilizzare per accedere alla riunione tramite telefono.

![Schermata dell'opzione Accesso manuale con accesso manuale](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Ricevere una chiamata in caso di problemi con l'audio durante una riunione

Se si verificano problemi audio durante l'uso del computer durante una riunione, l'utente può passare facilmente all'uso del telefono per l'audio. Teams rileva quando si verifica un problema audio o del dispositivo e reindirizza l'utente all'uso del telefono visualizzando un'opzione **Richiamami.**

Ecco un esempio del messaggio  e dell'opzione Richiamami che viene visualizzata quando Teams non rileva un microfono.

![Schermata dell'opzione Richiama](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L'utente fa **clic su Richiama,** per vedere lo schermo **Usa il telefono per l'audio.** Da qui, possono immettere il proprio numero di telefono e avere la chiamata alla riunione di Teams e unirli alla riunione o accedere manualmente alla riunione.

## <a name="set-up-the-call-me-feature"></a>Impostare la funzionalità Chiama

Per abilitare la funzionalità Chiamami per gli utenti dell'organizzazione, è necessario configurare quanto segue:

- L'audioconferenza è abilitata per gli utenti dell'organizzazione che pianificano riunioni (organizzatori di riunioni). Per ulteriori informazioni, consulta [Configurare le audioconferenze per Teams](set-up-audio-conferencing-in-teams.md) e gestire le impostazioni di [audioconferenza per un utente in Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Gli utenti possono effettuare chiamate in uscita dalle riunioni. Per ulteriori informazioni, consulta [Gestire le impostazioni di audioconferenza per un utente in Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Se un utente non ha la chiamata  in uscita dalle riunioni abilitata, l'opzione Chiama non è disponibile e l'utente non riceverà una chiamata per parteciparvi alla riunione. L'utente vede invece un elenco di numeri di telefono nello schermo Usa il telefono per **l'audio,** che può usare per accedere manualmente alla riunione sul proprio telefono.
