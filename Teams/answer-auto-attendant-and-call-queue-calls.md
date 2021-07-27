---
title: Rispondere alle chiamate in coda e all'operatore automatico
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descrive gli operatori automatici cloud e le code di chiamata e spiega come rispondere a queste chiamate in Teams.
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
ms.openlocfilehash: 6e7f20bc34b22449a115b0742a7cfdac88792f4c
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506395"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Rispondere alle chiamate degli operatori automatici e delle code delle chiamate direttamente da Teams

Teams gli utenti possono ricevere e rispondere alle chiamate dagli operatori automatici cloud e dalle code di chiamata direttamente dal Teams client.

## <a name="what-are-auto-attendants-and-call-queues"></a>Che cosa sono gli operatori automatici e le code di chiamata?

Gli operatori automatici cloud forniscono una serie di istruzioni vocali o un file audio che i chiamanti sentono invece di un operatore umano quando chiamano a un'organizzazione. L'operatore automatico consente ai chiamanti di spostarsi nel sistema di menu, effettuare chiamate o individuare utenti mediante tastiera a toni DTMF (Dual Tone Multi-Frequency) o input vocali con riconoscimento vocale.

Le code di chiamata cloud includono i messaggi di saluto usati quando qualcuno chiama a un numero di telefono per l'organizzazione, la possibilità di mettere automaticamente in attesa le chiamate e la possibilità di cercare il successivo agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare una o più code di chiamata per l'organizzazione.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestione di un operatore automatico o di una chiamata in coda

Gli utenti potranno distinguere le chiamate in arrivo da un operatore automatico o da una coda di chiamata prima di rispondere alla chiamata. Oltre al nome e/o al numero del chiamante, ogni chiamata includerà informazioni su chi il chiamante stava cercando di raggiungere, offrendo agli utenti un contesto migliore per l'indirizzamento del chiamante.

La figura seguente mostra come apparirà a un utente una chiamata in arrivo da un operatore automatico o una coda di chiamata.

![Screenshot di una notifica di chiamata in arrivo](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Dopo aver risposto a una chiamata in coda o a un operatore automatico, l'utente può elaborare la chiamata come qualsiasi altra chiamata &#x2014; può aggiungere o conferenza in un altro utente o trasferire la chiamata a un'altra parte. Inoltre, le chiamate dell'operatore automatico verranno inoltrate in base alla configurazione dell'utente.

> [!NOTE] 
> Le chiamate in coda di chiamata non vengono inoltrate in base alla configurazione dell'utente. In questo modo i chiamanti rimangono in coda finché un agente non può rispondere alla chiamata e il chiamante non viene inoltrato in modo imprevisto.

> Gli agenti non vengono avvisati delle chiamate perse o dei messaggi vocali per le chiamate in coda di chiamata.

## <a name="supported-clients"></a>Client supportati

Il supporto per l'operatore automatico e le chiamate in coda di chiamata è disponibile nei client seguenti:

-    Client Microsoft Teams Windows (versioni a 32 e 64 bit)
-    Client Microsoft Teams Mac
-    Microsoft Teams iPhone app
-    Microsoft Teams App Android

Il Teams client è supportato solo con una [modalità di coesistenza di Teams solo](/microsoftteams/setting-your-coexistence-and-upgrade-settings).

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurare il supporto dell'operatore automatico e della coda di chiamata per Microsoft Teams

Per ricevere chiamate in coda e operatore automatico Microsoft Teams, è necessario configurare i criteri di interoperabilità e di aggiornamento. Vedere Migrazione [e interoperabilità per le](migration-interop-guidance-for-teams-with-skype.md)organizzazioni che usano Teams insieme a Skype for Business . Se l'operatore automatico e/o la coda di chiamata non sono configurati e si vuole farlo, vedere Configurare un operatore automatico [cloud](create-a-phone-system-auto-attendant.md) e [Creare una coda di chiamata cloud.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>Problemi noti

Quando un agente della coda di chiamata riceve una chiamata sul dispositivo mobile, le chiamate potrebbero bloccarsi se il dispositivo è bloccato. L'utente deve prima sbloccare il dispositivo e rispondere alla chiamata.


## <a name="related-topics"></a>Argomenti correlati

-    [Che cosa Sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md)
-    [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md)
-    [Cosa sono gli operatori automatici cloud?](what-are-phone-system-auto-attendants.md)
-    [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md)

