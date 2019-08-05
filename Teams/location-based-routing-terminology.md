---
title: Terminologia di routing basata sulla posizione
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Informazioni sulla terminologia e sui concetti associati al routing basato sulla posizione per il routing diretto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: db6d6892c8a3bda8d30ac61d0458f252a6ac9281
ms.sourcegitcommit: 60c868155c7709df35fad23a41330483f8b59fee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2019
ms.locfileid: "36185014"
---
# <a name="location-based-routing-terminology"></a>Terminologia di routing basata sulla posizione

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Ecco alcuni termini e concetti usati in tutta la documentazione di routing basata sulla posizione. È consigliabile avere familiarità con questi termini e concetti prima di approfondire la documentazione.

|Termine  |Descrizione  |
|---------|---------|
|Aree di rete     | Un'area di rete contiene una raccolta di siti di rete. Ad esempio, se nell'organizzazione sono presenti molti siti in India, è possibile scegliere di designare "India" come area di rete.        |
|Siti di rete    | Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. I siti di rete sono definiti come una raccolta di subnet IP. Una procedura consigliata per il routing basato sulla posizione consiste nel creare un sito separato per ogni posizione con connettività PSTN univoca.  Ogni sito di rete deve essere associato a un'area di rete. È possibile creare un sito abilitato per il routing basato sulla posizione o un sito non abilitato per il routing basato sulla posizione. Ad esempio, potresti voler creare un sito non abilitato per il routing basato sulla posizione per consentire agli utenti abilitati per il routing basato sulla posizione di effettuare chiamate PSTN quando si spostano in tale sito. Tieni presente che i siti di rete possono anche essere usati per abilitare e configurare le chiamate di emergenza.        |
|Subnet di rete     |Le subnet IP nella posizione in cui i team endpoint possono connettersi alla rete devono essere definite e associate a una rete definita per applicare l'esclusione del pedaggio. Più subnet possono essere associate allo stesso sito di rete, ma potrebbe non essere associato più siti a una stessa subnet. Questa associazione di subnet consente il routing basato sulla posizione per individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate sia le subnet IPv6 che IPv4. Per determinare se un endpoint di teams si trova in un sito, il routing basato sulla posizione controlla prima di tutto un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, il routing basato sulla posizione controlla l'indirizzo IPv4. <br><br>
|Indirizzi IP esterni attendibili    |Gli indirizzi IP esterni attendibili sono gli indirizzi IP esterni Internet della rete aziendale. Determinano se l'endpoint dell'utente si trova all'interno della rete aziendale prima di verificare la presenza di una specifica corrispondenza di sito. Se l'IP esterno dell'utente corrisponde a un indirizzo IP definito nell'elenco attendibile, il routing basato sulla posizione viene controllato per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP definito nell'elenco attendibile, l'endpoint viene classificato come in una posizione sconosciuta e tutte le chiamate PSTN da o verso un utente abilitato per il routing basato sulla posizione sono bloccate.          |

### <a name="related-topics"></a>Argomenti correlati
- [Pianificare il routing basato sulla posizione per il routing diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare il routing basato sulla posizione per il routing diretto](location-based-routing-enable.md)
