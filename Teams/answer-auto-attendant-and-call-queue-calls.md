---
title: Rispondere alle chiamate dell'operatore automatico e della coda di chiamata
ms.reviewer: colongma
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descrive gli operatori automatici cloud e le code di chiamata e spiega come rispondere a queste chiamate in Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb621661ab8b5b8ace8a965e77513cd72966cf23
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880370"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Rispondere alle chiamate degli operatori automatici e delle code delle chiamate direttamente da Teams

Gli utenti di Teams possono ricevere e rispondere alle chiamate dagli operatori automatici cloud e dalle code di chiamata direttamente dal client di Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>Cosa sono gli operatori automatici e le code di chiamata?

Gli operatori automatici cloud forniscono una serie di comandi vocali o un file audio che i chiamanti ascoltano invece di un operatore umano quando chiamano un'organizzazione. L'operatore automatico consente ai chiamanti di spostarsi nel sistema di menu, effettuare chiamate o individuare utenti mediante tastiera a toni DTMF (Dual Tone Multi-Frequency) o input vocali con riconoscimento vocale.

Le code di chiamata cloud includono i saluti usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare una o più code di chiamata per l'organizzazione.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestione di un operatore automatico o di una chiamata in coda

Gli utenti potranno differenziare le chiamate in arrivo da un operatore automatico o da una coda di chiamata prima di rispondere alla chiamata. Oltre al nome e/o al numero del chiamante, ogni chiamata includerà informazioni sulle persone che il chiamante stava cercando di raggiungere, offrendo agli utenti un contesto migliore per indirizzare il chiamante.

La figura seguente mostra come apparirà una chiamata in arrivo da un operatore automatico o una coda di chiamata a un utente.

![Screenshot della notifica di una chiamata in arrivo.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una volta risposto a una chiamata in coda o a un operatore automatico, l'utente può elaborare la chiamata come qualsiasi altra chiamata &#x2014; può aggiungere o conferenza in un altro utente o trasferire la chiamata a un'altra parte. Inoltre, le chiamate dell'operatore automatico verranno inoltrate in base alla configurazione dell'utente.

> [!NOTE] 
> Le chiamate in coda di chiamata non vengono inoltrate in base alla configurazione delle regole di risposta alle chiamate dell'utente. Questo per garantire che i chiamanti rimangano in coda fino a quando un agente non può rispondere alla chiamata e il chiamante non viene inoltrato in modo imprevisto.
>
> Gli utenti che ricevono chiamate da code di chiamata riceveranno il nome del chiamante solo se viene fornito dalla rete PSTN o se il numero del chiamante corrisponde ai contatti client del team locale dell'utente di destinazione.
>
> Gli agenti non ricevono alcuna notifica delle chiamate perse o dei messaggi vocali per le chiamate in coda di chiamata.

## <a name="supported-clients"></a>Client supportati

Il supporto per le chiamate dell'operatore automatico e della coda di chiamata è disponibile nei seguenti client:

-    Client Microsoft Teams Windows (versioni a 32 e 64 bit)
-    Client Microsoft Teams Mac
-    App Microsoft Teams per iPhone
-    App Microsoft Teams per Android

Il client Teams è supportato solo con una [modalità di coesistenza di Solo Teams](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurare il supporto dell'operatore automatico e della coda di chiamata per Microsoft Teams

Per ricevere chiamate dell'operatore automatico e della coda di chiamata su Microsoft Teams, è necessario configurare i criteri di interoperabilità e di aggiornamento. Consultare [Migrazione e interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md). Se non hai configurato l'operatore automatico e/o la coda di chiamata e desideri farlo, vedi [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md) e [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).

## <a name="known-issues"></a>Problemi noti

Quando un agente della coda di chiamata riceve una chiamata sul suo dispositivo mobile, la chiamata potrebbe entrare in attesa se il dispositivo è bloccato. Gli utenti devono prima sbloccare il dispositivo e quindi rispondere alla chiamata.


## <a name="related-topics"></a>Argomenti correlati

[Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md)

[Cosa sono gli operatori automatici cloud?](what-are-phone-system-auto-attendants.md)

[Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md)

