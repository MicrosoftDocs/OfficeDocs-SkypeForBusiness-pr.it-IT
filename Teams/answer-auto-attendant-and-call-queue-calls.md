---
title: Rispondere alle chiamate dell'operatore automatico e in coda di chiamata
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descrive gli operatori automatici cloud e le code di chiamata e spiega come puoi rispondere a queste chiamate in Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766860"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Rispondere alle chiamate degli operatori automatici e delle code delle chiamate direttamente da Teams
===========================================================

Gli utenti di Teams possono ricevere e rispondere alle chiamate dagli operatori automatici cloud e dalle code di chiamata direttamente dal client di Teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>Cosa sono gli operatori automatici e le code di chiamata?

Gli operatori automatici cloud forniscono una serie di comandi vocali o un file audio che i chiamanti ascoltano invece di un operatore umano quando chiamano un'organizzazione. L'operatore automatico consente ai chiamanti di spostarsi nel sistema di menu, effettuare chiamate o individuare utenti mediante tastiera a toni DTMF (Dual Tone Multi-Frequency) o input vocali con riconoscimento vocale.

Le code di chiamata cloud includono i saluti che vengono utilizzati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano la musica di attesa. Puoi creare una o più code di chiamata per la tua organizzazione.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestione di una chiamata in coda o di un operatore automatico

Gli utenti saranno in grado di differenziare le chiamate in arrivo da un operatore automatico o una coda di chiamata prima di rispondere alla chiamata. Oltre al nome e/o al numero del chiamante, ogni chiamata includerà informazioni su chi il chiamante stava cercando di contattare, offrendo agli utenti un contesto migliore per contattare il chiamante.

L'illustrazione seguente mostra come apparirà una chiamata in arrivo da un operatore automatico o una coda di chiamata a un utente.

![Screenshot di una notifica di chiamata in arrivo](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una volta risposto a una chiamata in coda o a un operatore automatico, l'utente può elaborare la chiamata come qualsiasi altra chiamata &#x2014; può aggiungere o conferenza in un altro utente o trasferire la chiamata a un'altra parte. Inoltre, le chiamate dell'operatore automatico verranno inoltrate in base alla configurazione dell'utente.

> [!NOTE] 
> Le chiamate in coda di chiamata non vengono inoltrate in base alla configurazione dell'utente. In questo modo i chiamanti restano in coda finché un agente non può rispondere alla chiamata e non viene inoltrato in modo imprevisto.

## <a name="supported-clients"></a>Client supportati

Il supporto per le chiamate in coda e per gli operatori automatici è disponibile nei seguenti client:

-    Client Microsoft Teams Windows (versioni a 32 e 64 bit)
-    Client Microsoft Teams Mac
-    App Microsoft Teams per iPhone
-    App Microsoft Teams android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurare il supporto per operatori automatici e code di chiamata per Microsoft Teams

Per ricevere chiamate in coda e operatori automatici su Microsoft Teams, è necessario configurare i criteri di interoperabilità e di aggiornamento. Esaminare la [migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business.](migration-interop-guidance-for-teams-with-skype.md) Se non hai configurato un operatore automatico e/o una coda di chiamata e desideri farlo, vedi Configurare un operatore automatico [Cloud](create-a-phone-system-auto-attendant.md) e creare una coda [di chiamata Cloud.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemi noti

Quando un agente di coda di chiamata riceve una chiamata sul proprio dispositivo mobile, le chiamate possono andare in attesa se il dispositivo è bloccato. L'utente deve prima sbloccare il dispositivo e rispondere alla chiamata.


## <a name="related-topics"></a>Argomenti correlati

-    [Che cos'è il Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
-    [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md)
-    [Cosa sono gli operatori automatici cloud?](what-are-phone-system-auto-attendants.md)
-    [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md)

