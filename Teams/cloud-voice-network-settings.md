---
title: Impostazioni di rete per le funzionalità vocali del cloud
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sulle impostazioni di rete che è necessario configurare per Location-Based Routing per routing diretto e servizi di emergenza avanzati.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49709c2c3cc8816b404c88970c6ec916470f200e
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790151"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Impostazioni di rete per le funzionalità voce cloud in Microsoft Teams

Informazioni su aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili. Questi termini e concetti vengono usati nella documentazione della voce cloud per [il routing basato sulla posizione per il routing diretto](location-based-routing-plan.md) e [le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md). Se si distribuiscono queste funzionalità cloud nell'organizzazione, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams.

In questo articolo viene fornita una panoramica delle impostazioni di rete comuni per Location-Based Routing e chiamate di emergenza dinamiche. A seconda della funzionalità di voce cloud e delle funzionalità che stai distribuendo, puoi configurare alcune o tutte queste impostazioni. Per istruzioni su come configurare queste impostazioni, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams](manage-your-network-topology.md).

> [!NOTE]
> Gli eventuali requisiti specifici delle caratteristiche per le impostazioni di rete sono documentati negli argomenti di configurazione relativi a tale caratteristica.

## <a name="network-region"></a>Area di rete

Un'area di rete contiene una raccolta di siti di rete. Interconnette varie parti di una rete in più aree geografiche. Ad esempio, se l'organizzazione ha molti siti situati in India, è possibile scegliere di designare "India" come area di rete. Ogni sito di rete deve essere associato a un'area di rete.

Le stesse aree di rete sono condivise da Location-Based Routing per routing diretto e servizi di emergenza avanzati. Se sono già state create aree di rete per una caratteristica, non è necessario crearne di nuove per l'altra.

## <a name="network-site"></a>Sito di rete

Un sito di rete rappresenta una posizione in cui l'organizzazione ha un luogo fisico, ad esempio un ufficio, una serie di edifici o un campus. I siti di rete sono definiti come una raccolta di subnet IP. Ogni sito di rete deve essere associato a un'area di rete.

Puoi anche utilizzare i siti di rete per abilitare e configurare le chiamate di emergenza.

## <a name="network-subnet"></a>Subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. La posizione di un client viene determinata in base alla subnet di rete e al sito di rete associato. È possibile associare più subnet allo stesso sito di rete, ma non più siti alla stessa subnet.

Le informazioni sulla subnet vengono utilizzate per determinare il sito di rete in cui si trova un endpoint quando viene avviata una nuova sessione. Quando si conosce la posizione di ogni parte in una sessione, la funzionalità voce cloud può applicare tali informazioni per determinare come gestire la configurazione o l'instradamento delle chiamate.

Per ogni sito di rete, collaborare con l'amministratore di rete per determinare quali subnet IP sono assegnate a ogni sito di rete. Ad esempio, al sito di New York nell'area America del Nord possono essere assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, che di solito lavora a Detroit, si reca all'ufficio di New York per l'addestramento, accende il suo computer e si connette alla rete, il suo computer otterrà un indirizzo IP in uno dei quattro intervalli assegnati a New York, ad esempio, 172.29.80.103.

## <a name="trusted-ip-address"></a>Indirizzo IP attendibile

Gli indirizzi IP attendibili sono gli indirizzi IP esterni internet della rete aziendale. Determinano se l'endpoint dell'utente è all'interno della rete aziendale prima di verificare la corrispondenza di un sito specifico.

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco di indirizzi IP attendibili, la funzionalità voce cloud controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. È possibile creare una corrispondenza con gli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete. Se un indirizzo IP pubblico include sia IPv4 che IPv6, è necessario aggiungere entrambi come indirizzi IP attendibili.

Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP presente nell'elenco di indirizzi IP attendibili, l'endpoint viene classificato come in una posizione sconosciuta.

> [!Important]
> Le ricerche delle impostazioni di configurazione di rete non sono supportate nelle distribuzioni dei servizi proxy cloud che modificano gli indirizzi IP di origine dai client di Teams.
