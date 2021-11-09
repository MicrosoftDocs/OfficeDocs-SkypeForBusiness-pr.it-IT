---
title: Impostazioni di rete per le funzionalità vocali del cloud
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sulle impostazioni di rete che è necessario configurare per il routing Location-Based routing diretto e i servizi di emergenza migliorati.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 862d696024baa75feefbbae7e4458caad22b5566
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833982"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams

Informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili. Questi termini e concetti vengono usati nella documentazione vocale del cloud per [il routing in base](location-based-routing-plan.md) alla posizione per il routing diretto e per le chiamate di emergenza [dinamiche.](configure-dynamic-emergency-calling.md) Se si distribuiscono queste funzionalità cloud nell'organizzazione, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams.

Questo articolo offre una panoramica delle impostazioni di rete comuni al routing Location-Based chiamate di emergenza dinamiche. A seconda della funzionalità vocale cloud e della funzionalità che si sta distribuendo, è possibile configurare alcune o tutte queste impostazioni. Per la procedura di configurazione di queste impostazioni, vedere Gestire la topologia di rete per le [funzionalità cloud in Teams](manage-your-network-topology.md).

> [!NOTE]
> Gli eventuali requisiti specifici delle caratteristiche per le impostazioni di rete sono documentati negli argomenti di configurazione per tale caratteristica.

## <a name="network-region"></a>Area geografica di rete

Un'area di rete contiene una raccolta di siti di rete. Collega varie parti di una rete in più aree geografiche. Ad esempio, se l'organizzazione ha molti siti situati in India, è possibile scegliere di designare "India" come area di rete. Ogni sito di rete deve essere associato a un'area di rete.

Le stesse aree di rete sono condivise da Location-Based routing per il routing diretto e dai servizi di emergenza migliorati. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per l'altra caratteristica.

## <a name="network-site"></a>Sito di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. I siti di rete sono definiti come una raccolta di subnet IP. Ogni sito di rete deve essere associato a un'area di rete.

È anche possibile usare i siti di rete per abilitare e configurare le chiamate di emergenza.

## <a name="network-subnet"></a>Subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. La posizione di un client viene determinata in base alla subnet di rete e al sito di rete associato. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet.

Le informazioni sulla subnet vengono usate per determinare il sito di rete in cui si trova un endpoint quando viene avviata una nuova sessione. Quando la posizione di ogni parte in una sessione è nota, la funzionalità vocale cloud può applicare queste informazioni per determinare come gestire la configurazione o l'instradamento delle chiamate.

Per ogni sito di rete, collaborare con l'amministratore di rete per determinare quali subnet IP sono assegnate a ogni sito di rete. Ad esempio, al sito di New York nell'area nordamericana possono essere assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Luca, che di solito lavora a Detroit, si reca nell'ufficio di New York per la formazione, accende il computer e si connette alla rete, il computer riceverà un indirizzo IP in uno dei quattro intervalli allocati per New York, ad esempio 172.29.80.103.

## <a name="trusted-ip-address"></a>Indirizzo IP attendibile

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale. Determinano se l'endpoint dell'utente si trova all'interno della rete aziendale prima di verificare la corrispondenza di un sito specifico.

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, la funzionalità voce cloud controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. È possibile trovare una corrispondenza con gli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete. Se un indirizzo IP pubblico ha sia IPv4 che IPv6, è necessario aggiungerli entrambi come indirizzi IP attendibili.

Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta.

> [!Important]
> Le ricerche delle impostazioni di configurazione di rete non sono supportate nelle distribuzioni del servizio proxy cloud che modificano gli indirizzi IP di origine Teams client.
