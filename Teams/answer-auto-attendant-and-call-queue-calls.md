---
title: Rispondere alle chiamate all'operatore automatico e alla coda di chiamata
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descrive gli operatori automatici del cloud e le code di chiamata e spiega come rispondere alle chiamate in teams.
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
ms.openlocfilehash: 80400d9e9d7ab1519a15ab299f07896f55342eaf
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190870"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>Rispondere alle chiamate degli operatori automatici e delle code delle chiamate direttamente da Teams
===========================================================

Gli utenti del team possono ricevere e rispondere alle chiamate dagli operatori automatici del cloud e chiamare le code direttamente dal client teams.

## <a name="what-are-auto-attendants-and-call-queues"></a>Cosa sono gli operatori automatici e le code di chiamata?

Gli operatori automatici Cloud includono una serie di richieste vocali o un file audio che i chiamanti sentono al posto di un operatore umano quando chiamano un'organizzazione. L'operatore automatico consente ai chiamanti di spostarsi nel sistema di menu, effettuare chiamate o individuare utenti mediante tastiera a toni DTMF (Dual Tone Multi-Frequency) o input vocali con riconoscimento vocale.

Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa. È possibile creare code di chiamata singole o multiple per l'organizzazione.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>Gestione di una chiamata tramite operatore automatico o coda di chiamata

Gli utenti potranno distinguere le chiamate in arrivo da un operatore automatico o da una coda di chiamata prima di rispondere alla chiamata. Insieme al nome e/o al numero del chiamante, ogni chiamata includerà informazioni su chi il chiamante stava provando a raggiungere, offrendo agli utenti un contesto migliore per l'indirizzamento del chiamante.

La figura seguente mostra come verrà visualizzata una chiamata in arrivo da un operatore automatico o da una coda di chiamata a un utente.

![Schermata di una notifica di chiamata in arrivo](media/answer-auto-attendant-and-call-queue-calls-image1.png)

Una volta risolta una chiamata tramite operatore automatico o coda di chiamata, l'utente può elaborare la chiamata come qualsiasi altra chiamata &#x2014; può aggiungere o effettuare una conferenza in un altro utente o trasferire la chiamata a un'altra persona. Inoltre, le chiamate all'operatore automatico verranno inoltrate in base alla configurazione dell'utente.

> [!NOTE] 
> Le chiamate delle code di chiamata non vengono inoltrate in base alla configurazione dell'utente. In questo modo, i chiamanti rimarranno nella coda finché un agente non può rispondere alla chiamata e il chiamante non viene inoltrato inaspettatamente.

## <a name="supported-clients"></a>Client supportati

Il supporto per le chiamate all'operatore automatico e alla coda di chiamata è disponibile nei client seguenti:

-    Client Microsoft Teams Windows (versioni a 32 e 64 bit)
-    Client Microsoft Teams Mac
-    App per iPhone di Microsoft Teams
-    App Microsoft teams Android

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Configurare l'operatore automatico e il supporto delle code di chiamata per Microsoft Teams

Per ricevere le chiamate all'operatore automatico e alla coda di chiamata in Microsoft teams, è necessario configurare i criteri di interoperabilità e i criteri di aggiornamento. Verificare [la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md). Se non si dispone di un operatore automatico e/o di una coda di chiamata configurata e si desidera eseguire questa operazione, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md) e [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).

## <a name="related-topics"></a>Argomenti correlati

-    [Che cos'è il sistema telefonico in Office 365](what-is-phone-system-in-office-365.md)
-    [Creare una coda di chiamata cloud](create-a-phone-system-call-queue.md)
-    [Cosa sono gli operatori automatici cloud?](what-are-phone-system-auto-attendants.md)
-    [Configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md)

