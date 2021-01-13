---
title: Configurare le impostazioni di rete-routing basato sulla posizione
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree geografiche, siti e subnet di rete per Location-Based routing per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822946"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurare le impostazioni di rete per l'instradamento basato sulla posizione

Se non è già stato fatto, leggere [piano Location-Based routing per il routing diretto](location-based-routing-plan.md) per rivedere altri passaggi che è necessario eseguire prima di configurare le impostazioni di rete per Location-Based routing.

Questo articolo descrive come configurare le impostazioni di rete per Location-Based routing. Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.

## <a name="define-network-regions"></a>Definire le aree di rete

Un'area di rete contiene una raccolta di siti di rete e interconnette varie parti di una rete in più aree geografiche. Per istruzioni su come configurare le aree di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definire i siti di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. È necessario associare ogni sito di rete della topologia a un'area di rete. Per istruzioni su come configurare i siti di rete, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Una procedura consigliata per Location-Based routing consiste nel creare un sito separato per ogni posizione con connettività PSTN univoca. È possibile creare un sito abilitato per Location-Based routing o un sito non abilitato per Location-Based routing. Ad esempio, potresti voler creare un sito non abilitato per Location-Based routing per consentire agli utenti abilitati per Location-Based routing di effettuare chiamate PSTN quando si spostano in tale sito.

## <a name="define-network-subnets"></a>Definire le subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet. Per istruzioni su come configurare le subnet di rete, vedere  [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Per Location-Based routing, le subnet IP nella posizione in cui i team endpoint possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a pedaggio. Questa associazione di subnet consente Location-Based routing per individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate sia le subnet IPv6 che IPv4. Per determinare se un endpoint di teams si trova in un sito, Location-Based routing controlla prima di tutto un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, Location-Based il routing controlla l'indirizzo IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definire indirizzi IP attendibili (subnet esterne)

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Per istruzioni su come configurare indirizzi IP attendibili, vedere  [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, Location-Based i controlli di routing per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP definito nell'elenco di indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta e tutte le chiamate PSTN da o verso un utente abilitato per Location-Based routing sono bloccate.

## <a name="next-steps"></a>Passaggi successivi

Accedere a [abilita Location-Based routing per il routing diretto](location-based-routing-enable.md).

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali di cloud in teams](cloud-voice-network-settings.md)
