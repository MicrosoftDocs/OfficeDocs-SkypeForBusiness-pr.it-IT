---
title: Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sulle impostazioni di rete che è necessario configurare per il routing basato sulla posizione per il routing diretto e i servizi di emergenza avanzati.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74cf743d41f37cca2b8df4f25cc8f5328db6d776
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615886"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams

Informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili. Questi termini e concetti vengono usati in tutta la documentazione cloud Voice per il [routing basato sulla posizione per il routing diretto](location-based-routing-plan.md) e per le [chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md). Se si stanno distribuendo queste caratteristiche cloud nell'organizzazione, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft teams.

Questo articolo offre una panoramica delle impostazioni di rete comuni al routing basato sulla posizione e alle chiamate di emergenza dinamiche. A seconda della funzionalità cloud Voice e della funzionalità che si sta distribuendo, è possibile configurare alcune o tutte le impostazioni. Per la procedura per la configurazione di queste impostazioni, vedere [gestire la topologia di rete per le caratteristiche del cloud in teams](manage-your-network-topology.md).

> [!NOTE]
> Tutti i requisiti specifici delle funzionalità per le impostazioni di rete sono documentati negli argomenti di configurazione per tale funzionalità.

## <a name="network-region"></a>Area di rete

Un'area di rete contiene una raccolta di siti di rete. Interconnette varie parti di una rete in più aree geografiche. Ad esempio, se nell'organizzazione sono presenti molti siti in India, è possibile scegliere di designare "India" come area di rete. Ogni sito di rete deve essere associato a un'area di rete.

Le stesse aree di rete sono condivise dal routing basato sulla posizione per il routing diretto e i servizi di emergenza avanzati. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per l'altra caratteristica.

## <a name="network-site"></a>Sito di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio un ufficio, un set di edifici o un campus. I siti di rete sono definiti come una raccolta di subnet IP. Ogni sito di rete deve essere associato a un'area di rete.

È anche possibile usare i siti di rete per abilitare e configurare le chiamate di emergenza.

## <a name="network-subnet"></a>Subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. La posizione di un cliente viene determinata in base alla subnet della rete e al sito di rete associato. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet.

Le informazioni sulla subnet vengono usate per determinare il sito di rete in cui si trova un endpoint quando viene avviata una nuova sessione. Quando si conosce la posizione di ogni parte di una sessione, la caratteristica di cloud Voice può applicare tali informazioni per determinare come gestire l'installazione o il routing delle chiamate.

Per ogni sito di rete, collaborare con l'amministratore di rete per determinare le subnet IP assegnate a ogni sito di rete. Ad esempio, il sito di New York nell'area Nord America può essere assegnato alle subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, che lavora di solito a Detroit, si reca all'ufficio di New York per la formazione, accende il computer e si connette alla rete, il computer riceverà un indirizzo IP in uno dei quattro intervalli assegnati per New York, ad esempio 172.29.80.103.

## <a name="trusted-ip-address"></a>Indirizzo IP attendibile

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale. Determinano se l'endpoint dell'utente si trova all'interno della rete aziendale prima di verificare la presenza di una specifica corrispondenza di sito.

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, la caratteristica cloud Voice controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. Una corrispondenza può essere eseguita in base agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete. Se un indirizzo IP pubblico include sia IPv4 che IPv6, è necessario aggiungere entrambi come indirizzi IP attendibili.

Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta.
