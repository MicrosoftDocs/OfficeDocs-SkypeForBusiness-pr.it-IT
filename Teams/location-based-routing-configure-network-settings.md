---
title: Configurare le impostazioni di rete - Routing basato sulla posizione
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per il routing Location-Based per il routing diretto.
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

Se non è già stato fatto, leggere Pianificare il [routing Location-Based](location-based-routing-plan.md) per il routing diretto per esaminare gli altri passaggi da eseguire prima di configurare le impostazioni di rete per il routing Location-Based diretto.

Questo articolo descrive come configurare le impostazioni di rete per Location-Based routing. Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete.

## <a name="define-network-regions"></a>Definire le aree di rete

Un'area geografica di rete contiene una raccolta di siti di rete e collega varie parti di una rete in più aree geografiche. Per la procedura di configurazione delle aree geografiche di rete, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams.](manage-your-network-topology.md)

## <a name="define-network-sites"></a>Definire i siti di rete

Un sito di rete rappresenta una posizione fisica per l'organizzazione, ad esempio un ufficio, una serie di edifici o un campus. È necessario associare ogni sito di rete nella topologia a un'area geografica di rete. Per la procedura di configurazione dei siti di rete, vedere [Gestire la topologia di rete per le caratteristiche cloud in Teams.](manage-your-network-topology.md)

La procedura consigliata per Location-Based distribuzione siti consiste nel creare un sito distinto per ogni posizione con connettività PSTN univoca. È possibile creare un sito abilitato per il routing Location-Based siti o un sito non abilitato per il routing Location-Based distribuzione. Ad esempio, è possibile creare un sito non abilitato per il routing di Location-Based per consentire agli utenti abilitati per il routing Location-Based di effettuare chiamate PSTN durante il roaming al sito.

## <a name="define-network-subnets"></a>Definire le subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet. Per la procedura di configurazione delle subnet di rete, vedere Gestire la topologia di rete [per le funzionalità cloud in Teams.](manage-your-network-topology.md)

Per Location-Based routing, le subnet IP nella posizione in cui gli endpoint di Teams possono connettersi alla rete devono essere definite e associate a una rete definita per applicare il bypass a numero verde. Questa associazione di subnet consente Location-Based routing della rete di individuare gli endpoint geograficamente per determinare se una determinata chiamata PSTN deve essere consentita. Sono supportate sia le subnet IPv6 che le subnet IPv4. Quando si determina se un endpoint di Teams si trova in un sito, il routing Location-Based verifica prima la presenza di un indirizzo IPv6 corrispondente. Se non è presente un indirizzo IPv6, Location-Based routing verifica la presenza di un indirizzo IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definire indirizzi IP attendibili (subnet esterne)

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale e vengono usati per determinare se l'endpoint dell'utente si trova all'interno della rete aziendale. Per la procedura di configurazione degli indirizzi IP attendibili, vedere Gestire la topologia di rete [per le funzionalità cloud in Teams.](manage-your-network-topology.md)

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibile, il routing di Location-Based verifica per determinare la subnet interna in cui si trova l'endpoint dell'utente. Se l'indirizzo IP esterno dell'utente non corrisponde ad alcun indirizzo IP definito nell'elenco indirizzi IP attendibile, l'endpoint viene classificato come posta in una posizione sconosciuta e le chiamate PSTN da o verso un utente abilitato per il routing Location-Based vengono bloccate.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Abilita Location-Based per il routing diretto.](location-based-routing-enable.md)

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
