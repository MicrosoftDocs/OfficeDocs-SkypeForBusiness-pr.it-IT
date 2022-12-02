---
title: Microsoft piani di chiamata e routing di Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Dial plan e routing in Microsoft Teams
ms.openlocfilehash: b45fd9ec15ae6a9bb8f342096711b58512aead43
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242470"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Microsoft piani di chiamata e routing di Teams

Gli articoli di questa sezione descrivono i piani di chiamata e il routing delle chiamate in Microsoft Teams. 

- [Cosa sono i piani di chiamata](what-are-dial-plans.md)
- [Creare e impostare dial plan](create-and-manage-dial-plans.md)
- [Instradare le chiamate a numbi non assegnati](routing-calls-to-unassigned-numbers.md)

Gli articoli di questa sezione si applicano a tutte le opzioni per la connessione alla rete PSTN (Public Switched Telephone Network): Piano per chiamate, Operator Connect, Teams Phone Mobile e Routing diretto. Per altre informazioni su tutte le opzioni di connettività PSTN, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).

Se si sceglie Piano per chiamate, Operator Connect o Teams Phone Mobile, la maggior parte del routing delle chiamate viene gestita da Microsoft o dal provider. L'instradamento diretto, tuttavia, richiede passaggi aggiuntivi per configurare il routing delle chiamate. 

Per l'instradamento diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti. È possibile configurare piani di chiamata per la traduzione dei numeri a livello di trunk per garantire l'interoperabilità con i controller di session border (SBC). Per altre informazioni, vedere [Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md), [Gestire i criteri di routing vocale](manage-voice-routing-policies.md) e [Tradurre numeri di telefono](direct-routing-translate-numbers.md).

Tieni presente che puoi assegnare un criterio di routing vocale online Direct Routing agli utenti del piano per chiamate e di Operator Connect. Questa operazione può essere utile, ad esempio, per consentire agli utenti di accedere direttamente a un call center. È possibile configurare un trunk routing diretto al call center.

Se ad esempio un utente dispone di una licenza per il Piano per chiamate, le chiamate in uscita di quell'utente vengono automaticamente instradate tramite l'infrastruttura PSTN del piano per chiamate Microsoft. Se si configura e assegna all'utente un criterio di routing vocale diretto online, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composizione corrisponde a uno schema numerico definito nel criterio di routing vocale online. Se esiste una corrispondenza, la chiamata viene instradata attraverso il trunk Routing diretto. Se non c'è corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano per chiamate.

Per altre informazioni, vedere [Considerazioni sui criteri di routing vocale routing diretto](direct-routing-voice-routing.md#voice-routing-policy-considerations).



