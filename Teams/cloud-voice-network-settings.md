---
title: Impostazioni di rete per le funzionalità vocali del cloud
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sulle impostazioni di rete che è necessario configurare per il routing Location-Based per il routing diretto e i servizi di emergenza avanzato.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834336"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams

Informazioni su aree geografiche, siti di rete, subnet di rete e indirizzi IP attendibili. Questi termini e concetti vengono utilizzati nella documentazione vocale del cloud per il routing basato sulla posizione per [il routing diretto](location-based-routing-plan.md) e le chiamate di emergenza [dinamiche.](configure-dynamic-emergency-calling.md) Se stai distribuendo queste funzionalità cloud nella tua organizzazione, devi configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams.

In questo articolo viene fornita una panoramica delle impostazioni di rete comuni al routing Location-Based chiamate di emergenza dinamiche. A seconda della funzionalità vocale del cloud e della funzionalità che si sta distribuendo, è possibile configurare alcune o tutte queste impostazioni. Per la procedura di configurazione di queste impostazioni, vedere [Gestire la topologia di rete per le funzionalità cloud in Teams.](manage-your-network-topology.md)

> [!NOTE]
> I requisiti specifici delle caratteristiche per le impostazioni di rete sono documentati negli argomenti di configurazione per tale caratteristica.

## <a name="network-region"></a>Area geografica della rete

Un'area di rete contiene una raccolta di siti di rete. Collega varie parti di una rete in più aree geografiche. Ad esempio, se l'organizzazione ha molti siti situati in India, è possibile scegliere di designare "India" come area di rete. Ogni sito di rete deve essere associato a un'area geografica di rete.

Le stesse aree geografiche di rete sono condivise Location-Based routing per l'instradamento diretto e servizi di emergenza migliorati. Se sono già state create aree di rete per una caratteristica, non è necessario creare nuove aree di rete per l'altra caratteristica.

## <a name="network-site"></a>Sito di rete

Un sito di rete rappresenta una posizione fisica per l'organizzazione, ad esempio un ufficio, una serie di edifici o un campus. I siti di rete sono definiti come una raccolta di subnet IP. Ogni sito di rete deve essere associato a un'area geografica di rete.

Puoi inoltre utilizzare i siti di rete per abilitare e configurare le chiamate di emergenza.

## <a name="network-subnet"></a>Subnet di rete

Ogni subnet deve essere associata a un sito di rete specifico. La posizione di un client viene determinata in base alla subnet di rete e al sito di rete associato. È possibile associare più subnet allo stesso sito di rete, ma non è possibile associare più siti alla stessa subnet.

Le informazioni sulla subnet vengono usate per determinare il sito di rete in cui si trova un endpoint quando viene avviata una nuova sessione. Quando la posizione di ciascuna parte in una sessione è nota, la funzionalità cloud vocale può applicare queste informazioni per determinare come gestire la configurazione o l'instradamento delle chiamate.

Per ogni sito di rete, collaborare con l'amministratore di rete per determinare quali subnet IP sono assegnate a ogni sito di rete. Ad esempio, al sito di New York nell'area nordamericana possono essere assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, che in genere lavora a D auditorium, si reca nell'ufficio di New York per la formazione, accende il computer e si connette alla rete, il suo computer riceverà un indirizzo IP in uno dei quattro intervalli assegnati a New York, ad esempio 172.29.80.103.

## <a name="trusted-ip-address"></a>Indirizzo IP attendibile

Gli indirizzi IP attendibili sono gli indirizzi IP esterni Internet della rete aziendale. Determinano se l'endpoint dell'utente si trova all'interno della rete aziendale prima di verificare la corrispondenza di uno specifico sito.

Se l'indirizzo IP esterno dell'utente corrisponde a un indirizzo IP presente nell'elenco indirizzi IP attendibile, la funzionalità Voce cloud controlla per determinare la subnet interna in cui si trova l'endpoint dell'utente. Una corrispondenza può essere effettuata rispetto agli indirizzi IP IPv4 o IPv6 e dipende dal formato del pacchetto IP inviato alle impostazioni di rete. Se un indirizzo IP pubblico include sia IPv4 che IPv6, è necessario aggiungerli entrambi come indirizzi IP attendibili.

Se l'indirizzo IP esterno dell'utente non corrisponde a un indirizzo IP in elenco indirizzi IP attendibile, l'endpoint viene classificato come in una posizione sconosciuta.
