---
title: Configurare le impostazioni di rete per l'instradamento basato sulla posizione
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfa81c0d5856ba97b60f3183ff282bef8c911fda
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836566"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurare le impostazioni di rete per l'instradamento basato sulla posizione

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Se non è già stato fatto, leggere il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) per esaminare gli altri passaggi che è necessario eseguire prima di configurare le impostazioni di rete per il routing basato sulla posizione.

Questo articolo descrive come configurare le impostazioni di rete per il routing basato sulla posizione. Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.

## <a name="define-network-regions"></a>Definire le aree di rete

Un'area di rete contiene una raccolta di siti di rete e interconnette varie parti di una rete in più aree geografiche. Per istruzioni su come configurare le aree di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definire i siti di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. È necessario associare ogni sito di rete della topologia a un'area di rete. Per istruzioni su come configurare i siti di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Una procedura consigliata per il routing basato sulla posizione consiste nel creare un sito separato per ogni posizione con connettività PSTN univoca. È possibile creare un sito abilitato per il routing basato sulla posizione o un sito non abilitato per il routing basato sulla posizione. Ad esempio, potresti voler creare un sito non abilitato per il routing basato sulla posizione per consentire agli utenti abilitati per il routing basato sulla posizione di effettuare chiamate PSTN quando si spostano in tale sito.

## <a name="define-network-subnets"></a>Definire le subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet. Per istruzioni su come configurare le subnet di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Per il routing basato sulla posizione, le subnet IP nella posizione in cui i team endpoint possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a pedaggio. Questa associazione di subnet consente il routing basato sulla posizione per individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate sia le subnet IPv6 che IPv4. Per determinare se un endpoint di teams si trova in un sito, il routing basato sulla posizione controlla prima di tutto un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, il routing basato sulla posizione controlla l'indirizzo IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definire indirizzi IP attendibili (subnet esterne)

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Per istruzioni su come configurare indirizzi IP attendibili, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, il routing basato sulla posizione viene controllato per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP definito nell'elenco di indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta e tutte le chiamate PSTN da o verso un utente abilitato per il routing basato sulla posizione sono bloccate.

## <a name="next-steps"></a>Passaggi successivi

Accedere a [abilitare il routing basato sulla posizione per il routing diretto](location-based-routing-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali di cloud in teams](cloud-voice-network-settings.md)
