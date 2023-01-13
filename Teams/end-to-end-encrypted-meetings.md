---
title: Richiedere la crittografia end-to-end per le riunioni sensibili di Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Informazioni su come abilitare la crittografia end-to-end per le riunioni di Teams.
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800140"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>Richiedere la crittografia end-to-end per le riunioni sensibili di Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

End-to-end crittografia è la crittografia delle informazioni alla sua origine e decrittografia presso la sua destinazione prevista senza la capacità per i nodi intermedi di decrittografare. Quando le riunioni in Teams sono crittografate end-to-end, nessuno tranne i partecipanti alla riunione può ascoltare o vedere la comunicazione. Nessun'altra parte, inclusa Microsoft, ha accesso alla conversazione decrittografata.

Le riunioni crittografate end-to-end possono essere organizzate tra due parti quando: le parti usano l'ultima versione del client desktop di Teams per Windows o Mac, si trovano su un dispositivo mobile con l'aggiornamento più recente per iOS e Android o su un Teams Rooms su dispositivo Windows usando l'aggiornamento più recente. La crittografia end-to-end per la partecipazione alla riunione tramite il browser non è supportata.

> [!Note]
> La crittografia end-to-end delle riunioni richiede Teams Premium.

Se non si abilita la crittografia end-to-end, Teams garantisce comunque le riunioni usando la crittografia in base agli standard di settore. I dati scambiati durante le riunioni sono sempre al sicuro durante i trasporti e inattivi. Per altre informazioni, vedere [Crittografia multimediale per Teams](teams-security-guide.md#media-encryption).

Durante una riunione crittografata end-to-end, Teams protegge le seguenti funzionalità:

- Audio

- Video

- Condivisione dello schermo.

[La crittografia in Microsoft 365](/microsoft-365/compliance/encryption) protegge chat, condivisione di file, presenza e altri contenuti nella riunione. App, avatar, reazioni, chat e domande&A non sono crittografati end-to-end.

Le caratteristiche seguenti non sono disponibili durante una riunione crittografata end-to-end:

- Sottotitoli e trascrizioni in tempo reale

- Registrazione

- Modalità Insieme, modalità complementare, raccolta di grandi dimensioni

- Stanze per i gruppi di lavoro

Se l'organizzazione usa la registrazione della conformità, la crittografia end-to-end non è disponibile. Per altre informazioni su come Teams supporta la registrazione della conformità, vedere [Introduzione alla registrazione basata su criteri di Teams per chiamate e riunioni](teams-recording-policy.md).

## <a name="enable-end-to-end-encryption-for-meetings"></a>Abilitare la crittografia end-to-end per le riunioni

Per impostazione predefinita, la crittografia end-to-end per le riunioni non è abilitata. È possibile abilitarlo usando un criterio di crittografia avanzata dell'amministratore di Teams.

Una volta abilitata la crittografia end-to-end, gli organizzatori delle riunioni possono scegliere la crittografia end-to-end e quindi creare una riunione. È anche possibile applicare la crittografia end-to-end usando un modello di riunione o un'etichetta di riservatezza.

Per abilitare la crittografia end-to-end per le riunioni

1. Nell'interfaccia di amministrazione di Teams selezionare **Criteri di crittografia avanzata**.

1. Selezionare il criterio da aggiornare.

1. Impostare **la crittografia riunione end-to-end** su **Non abilitato, ma gli utenti possono eseguire l'override**.

1. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Usare la crittografia end-to-end per le chiamate uno-a-uno di Microsoft Teams](teams-end-to-end-encryption.md)
