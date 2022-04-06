---
title: Piani di chiamata e routing
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Dial plan e routing in Microsoft Teams
ms.openlocfilehash: 1d99b5edef1cf6c4440a218097933e4ff5843f1d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686716"
---
# <a name="overview"></a>Panoramica

Gli articoli di questa sezione descrivono i piani di chiamata e il routing delle chiamate in Microsoft Teams. 

- [Cosa sono i piani di chiamata](what-are-dial-plans.md)
- [Creare e impostare dial plan](create-and-manage-dial-plans.md)
- [Instradare le chiamate a numbi non assegnati](routing-calls-to-unassigned-numbers.md)

Gli articoli di questa sezione si applicano a tutte le opzioni per la connessione alla rete PSTN (Public Switched Telephone Network): Piano per chiamate, Connessione con operatore e Routing diretto. Per altre informazioni su tutte le opzioni di connettività PSTN, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).

Se scegli Piano per chiamate o Connessione con operatore, la maggior parte del routing delle chiamate viene gestita da Microsoft o dal tuo provider. L'instradamento diretto, tuttavia, richiede passaggi aggiuntivi per configurare il routing delle chiamate. 

Per l'instradamento diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti. È possibile configurare piani di chiamata per la traduzione dei numeri a livello di trunk per garantire l'interoperabilità con i controller di session border (SBC). Per altre informazioni, vedere [Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md), [Gestire i criteri di routing vocale](manage-voice-routing-policies.md) e [Tradurre numeri di telefono](direct-routing-translate-numbers.md).

Tieni presente che puoi assegnare un criterio di routing vocale online Direct Routing al piano per chiamate e Connessione con operatore utenti. Questa operazione può essere utile, ad esempio, per consentire agli utenti di accedere direttamente a un call center. È possibile configurare un trunk routing diretto al call center.

Se ad esempio un utente ha una licenza per un piano per chiamate, le chiamate in uscita di quell'utente vengono automaticamente instradate tramite l'infrastruttura PSTN del piano per chiamate Microsoft. Se si configura e assegna all'utente un criterio di routing vocale diretto online, le chiamate in uscita dell'utente vengono controllate per determinare se il numero composizione corrisponde a uno schema numerico definito nel criterio di routing vocale online. Se esiste una corrispondenza, la chiamata viene instradata attraverso il trunk Routing diretto. Se non c'è corrispondenza, la chiamata viene instradata tramite l'infrastruttura PSTN del piano per chiamate.

Per altre informazioni, vedere [Considerazioni sui criteri di routing vocale routing diretto](direct-routing-voice-routing.md#voice-routing-policy-considerations).



