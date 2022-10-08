---
title: Configurare le impostazioni di rete - Routing basato sulla posizione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per Location-Based Routing per routing diretto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999331"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurare le impostazioni di rete per l'instradamento basato sulla posizione

Questo articolo descrive come configurare le impostazioni di rete per Location-Based Routing. Se non è già stato fatto, leggere [Plan Location-Based Routing for Direct Routing per](location-based-routing-plan.md) esaminare altri passaggi da eseguire prima di configurare le impostazioni di rete.

Dopo aver distribuito il routing diretto nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.

## <a name="define-network-regions"></a>Definire le aree di rete

Un'area di rete contiene una raccolta di siti di rete e interconnette varie parti di una rete in più aree geografiche. Per i passaggi su come configurare le aree di rete, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definire siti di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha un luogo fisico, ad esempio un ufficio, una serie di edifici o un campus. È necessario associare ogni sito di rete della topologia a un'area di rete. Per istruzioni su come configurare i siti di rete, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams](manage-your-network-topology.md).

Una procedura consigliata per Location-Based Routing consiste nel creare un sito separato per ogni posizione con connettività PSTN (Public Switched Telephone Network) univoca. È possibile creare un sito abilitato per Location-Based Routing o un sito non abilitato per Location-Based Routing. Ad esempio, è consigliabile creare un sito non abilitato per Location-Based Routing per consentire agli utenti abilitati per Location-Based Routing di effettuare chiamate PSTN quando effettuano il roaming nel sito.

## <a name="define-network-subnets"></a>Definire subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. È possibile associare più subnet allo stesso sito di rete, ma non più siti alla stessa subnet. Per istruzioni su come configurare le subnet di rete, vedere  [Gestire la topologia di rete per le funzionalità cloud in Teams](manage-your-network-topology.md).

Per Location-Based Routing, le subnet IP nella posizione in cui gli endpoint di Teams possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a pagamento. Questa associazione delle subnet consente a Location-Based Routing di individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate le subnet IPv6 e IPv4. Quando si determina se un endpoint di Teams si trova in un sito, Location-Based Routing verifica innanzitutto la presenza di un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, Location-Based Routing verifica la presenza di un indirizzo IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definire indirizzi IP attendibili (subnet esterne)

Gli indirizzi IP attendibili sono gli indirizzi IP esterni internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Per istruzioni su come configurare indirizzi IP attendibili, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams](manage-your-network-topology.md).

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco di indirizzi IP attendibili, Location-Based Il routing controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde a nessun indirizzo IP definito nell'elenco di indirizzi IP attendibili, l'endpoint viene classificato come posizione sconosciuta e le chiamate PSTN a o da un utente abilitato per Location-Based Routing vengono bloccate.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Abilita routing Location-Based per routing diretto](location-based-routing-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità voce cloud in Teams](cloud-voice-network-settings.md)
