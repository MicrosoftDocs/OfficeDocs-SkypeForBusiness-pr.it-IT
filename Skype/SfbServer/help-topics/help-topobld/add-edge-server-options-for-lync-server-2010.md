---
title: Aggiungere opzioni per i server perimetrali per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'È possibile definire un nuovo server perimetrale o un pool di Edge e presentare la possibilità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:'
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835516"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Aggiungere opzioni Edge Server per Lync Server 2010

È possibile definire un nuovo server perimetrale o un pool di Edge e presentare la possibilità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:

- **Usa singola combinazione di FQDN e indirizzo IP**: selezionare la casella di controllo per utilizzare un singolo indirizzo IPv4 o IPv6 (se si sceglie di utilizzare sia IPv4 che IPv6, sarà necessario definire un indirizzo per ogni tipo di indirizzo IP) e un nome di dominio completo (FQDN) per le interfacce perimetrali esterne.

    > [!IMPORTANT]
    > Se si sceglie questa opzione, si utilizzerà solo un indirizzo IP, oppure un indirizzo IPv4 e un indirizzo IPv6, ma sarà necessario assegnare numeri di porta diversi a ogni interfaccia perimetrale.

- **Abilita federazione per pool di server perimetrali (porta 5061)**: selezionare questa casella di controllo se si attuerà la federazione con altre federazioni SIP, con altri provider oppure con offerte ospitate che utilizzano il protocollo SIP (Session Initiation Protocol).

- **L'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**: selezionare questa casella di controllo se si utilizzano indirizzi IP privati per le interfacce esterne perimetrali e viene fornito un dispositivo NAT (Network Address Translation) per posizionare il server perimetrale o il pool di Edge logicamente dietro.

## <a name="see-also"></a>Vedere anche

[Pianificazione dell'accesso utente esterno](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Distribuzione dell'accesso degli utenti esterni](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
