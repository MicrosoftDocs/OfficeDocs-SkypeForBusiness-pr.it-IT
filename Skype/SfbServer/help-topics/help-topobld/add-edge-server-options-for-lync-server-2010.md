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
description: "Si definisce un nuovo server perimetrale o un nuovo pool di server perimetrali e viene offerta l'opportunità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:"
ms.openlocfilehash: c258f87ac3edb38ad72d536b8ccfb2f2870d5d9e09cda65b417e49ba2c87707f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320458"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Aggiungere opzioni Edge Server per Lync Server 2010

Si definisce un nuovo server perimetrale o un nuovo pool di server perimetrali e viene offerta l'opportunità di definire le funzionalità per il nuovo server o pool. Sono disponibili le opzioni seguenti:

- **Usa singola combinazione di FQDN e indirizzo IP**: selezionare la casella di controllo per utilizzare un singolo indirizzo IPv4 o IPv6 (se si sceglie di utilizzare sia IPv4 che IPv6, sarà necessario definire un indirizzo per ogni tipo di indirizzo IP) e un nome di dominio completo (FQDN) per le interfacce perimetrali esterne.

    > [!IMPORTANT]
    > Se si sceglie questa opzione, si utilizzerà solo un indirizzo IP, oppure un indirizzo IPv4 e un indirizzo IPv6, ma sarà necessario assegnare numeri di porta diversi a ogni interfaccia perimetrale.

- **Abilita federazione per pool di server perimetrali (porta 5061)**: selezionare questa casella di controllo se si attuerà la federazione con altre federazioni SIP, con altri provider oppure con offerte ospitate che utilizzano il protocollo SIP (Session Initiation Protocol).

- **L'indirizzo IP** esterno di questo pool di server perimetrali viene convertito da NAT: selezionare questa casella di controllo se si utilizzano indirizzi IP privati per le interfacce esterne perimetrali e si fornirà un dispositivo NAT (Network Address Translation) in cui posizionare logicamente il server perimetrale o il pool di server perimetrali.

## <a name="see-also"></a>Vedere anche

[Pianificazione dell'accesso utente esterno](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[Distribuzione dell'accesso degli utenti esterni](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)