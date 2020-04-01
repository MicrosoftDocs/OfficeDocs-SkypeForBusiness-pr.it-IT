---
title: Configurare la funzionalità Chiamami per gli utenti
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare la funzionalità Chiamami in teams in modo che gli utenti possano partecipare alla parte audio tramite telefono in scenari in cui l'uso del proprio computer per l'audio potrebbe non essere possibile.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cee6937a1bdc2bef6d2184066cb32a4aa94d8e6
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096851"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurare la funzionalità Chiamami per gli utenti

In Microsoft teams, la funzionalità **chiamami** offre agli utenti un modo per partecipare alla parte audio di una riunione tramite telefono. Questa operazione è utile in scenari in cui l'uso di un computer per l'audio potrebbe non essere possibile. Gli utenti ottengono la parte audio della riunione tramite il telefono cellulare o la linea di terra e la parte di contenuto&mdash;della riunione, quando un altro partecipante alla riunione condivide lo schermo&mdash;o riproduce un video nel computer.

> [!IMPORTANT]
> Durante la durata del focolaio di COVID-19, è consigliabile che gli utenti partecipino alle riunioni facendo clic sul pulsante **partecipa alla riunione teams** invece di effettuare la chiamata tramite i numeri di conferenza PSTN o usando **chiama**</strong>. Questo vale principalmente per la congestione delle infrastrutture di telefonia dei paesi interessati da COVID-19. Evitando chiamate PSTN, è probabile che si verifichi una qualità audio migliore. 

## <a name="the-user-experience"></a>Esperienza utente

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Partecipare a una riunione tramite telefono per l'audio

Fare clic su **partecipa** per partecipare a una riunione e quindi fare clic su **audio telefono** nella schermata **Scegli impostazioni audio e video** . Da qui gli utenti possono avere la chiamata di riunione e unirli o connettersi manualmente alla riunione.

![Screenshot dell'opzione audio telefono](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Consentire la chiamata alla riunione Teams**

Nella schermata **Usa telefono per l'audio** l'utente immette il proprio numero di telefono e quindi fa clic su **chiamami**. La riunione chiama l'utente e li unisce alla riunione.

![Screenshot dell'opzione chiamami nella schermata Usa telefono per l'audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Componi manualmente**

Un altro modo per partecipare consiste nel connettersi direttamente alla riunione. Nella schermata **Usa telefono per audio** fare clic su **Componi manualmente** per ottenere un elenco di numeri di telefono da usare per connettersi alla riunione.

![Screenshot dell'opzione Componi manualmente](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Ottenere una chiamata quando si verifica un problema con l'audio durante una riunione

Se un utente avverte problemi di audio quando si usa il proprio computer durante una riunione, l'utente può facilmente passare a usare il telefono per l'audio. Teams rileva quando si verifica un problema di audio o dispositivo e reindirizza l'utente a usare il telefono visualizzando l'opzione **chiamami** .

Ecco un esempio del messaggio e l'opzione **chiamami di nuovo** visualizzata quando i team non rilevano un microfono.

![Schermata dell'opzione chiamami di nuovo](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L'utente fa clic su **richiama me back**, che porta in alto il **telefono uso per** lo schermo audio. Da qui è possibile immettere il proprio numero di telefono e convocare la riunione di teams per partecipare alla riunione o connettersi manualmente alla riunione.

## <a name="set-up-the-call-me-feature"></a>Configurare la caratteristica chiamami

Per abilitare la funzionalità chiamami per gli utenti dell'organizzazione, è necessario configurare le operazioni seguenti:

- I servizi di audioconferenza sono abilitati per gli utenti dell'organizzazione che pianificano riunioni (organizzatori di riunioni). Per altre informazioni, vedere [configurare le conferenze audio per i team](set-up-audio-conferencing-in-teams.md) e [gestire le impostazioni di audioconferenza per un utente in teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Gli utenti possono effettuare la chiamata fuori dalle riunioni. Per altre informazioni, vedere [gestire le impostazioni di audioconferenza per un utente in teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Se un utente non ha attivato la chiamata in uscita dalle riunioni, l'opzione **chiamami** non è disponibile e l'utente non riceverà una chiamata per partecipare alla riunione. L'utente vede invece un elenco di numeri di telefono nella schermata **Usa telefono per l'audio** che possono usare per effettuare la chiamata manualmente alla riunione sul telefono.
