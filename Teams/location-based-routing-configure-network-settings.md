---
title: Configurare le impostazioni di rete - Routing basato sulla posizione
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per Location-Based routing diretto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bbe82aa178668ab43f279d830984b4a3d5263e5d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829630"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurare le impostazioni di rete per l'instradamento basato sulla posizione

Se non è già stato [fatto,](location-based-routing-plan.md) vedere Pianificare il routing Location-Based per il routing diretto per esaminare gli altri passaggi da eseguire prima di configurare le impostazioni di rete per Location-Based routing.

Questo articolo descrive come configurare le impostazioni di rete per Location-Based routing. Dopo aver distribuito Sistema telefonico routing diretto nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.

## <a name="define-network-regions"></a>Definire le aree di rete

Un'area di rete contiene una raccolta di siti di rete e collega varie parti di una rete in più aree geografiche. Per la procedura di configurazione delle aree di rete, vedere Gestire la topologia di rete per le [funzionalità cloud in Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definire i siti di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. È necessario associare ogni sito di rete della topologia a un'area di rete. Per la procedura di configurazione dei siti di rete, vedere Gestire la topologia di rete per le [caratteristiche cloud in Teams](manage-your-network-topology.md).

Una procedura consigliata per Location-Based routing consiste nel creare un sito separato per ogni posizione con connettività PSTN univoca. È possibile creare un sito abilitato per il routing Location-Based o un sito non abilitato per Location-Based routing. Ad esempio, è possibile creare un sito non abilitato per il routing di Location-Based per consentire agli utenti abilitati per Location-Based Routing di effettuare chiamate PSTN durante il roaming verso il sito.

## <a name="define-network-subnets"></a>Definire subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet. Per la procedura di configurazione delle subnet di rete, vedere Gestire la topologia di rete per le [funzionalità cloud in Teams](manage-your-network-topology.md).

Per Location-Based routing, le subnet IP nella posizione in cui gli endpoint Teams possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a pedaggio. Questa associazione di subnet consente Location-Based routing di individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate sia le subnet IPv6 che le subnet IPv4. Quando si determina se un endpoint Teams si trova in un sito, il routing Location-Based prima verifica la presenza di un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, Location-Based routing verifica la presenza di un indirizzo IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definire indirizzi IP attendibili (subnet esterne)

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Per la procedura di configurazione degli indirizzi IP attendibili, vedere Gestire la topologia di rete per le [funzionalità cloud in Teams](manage-your-network-topology.md).

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, Location-Based Routing controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde ad alcun indirizzo IP definito nell'elenco indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta e le chiamate PSTN da o verso un utente abilitato per il routing Location-Based vengono bloccate.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Abilita Location-Based routing per il routing diretto](location-based-routing-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
