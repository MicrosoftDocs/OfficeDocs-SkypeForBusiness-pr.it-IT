---
title: Espansione delle impostazioni del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:'
ms.openlocfilehash: 7f202dc03d0c83c324f4dc2a75928e022a68250c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828576"
---
# <a name="edge-settings-expander"></a>Espansione delle impostazioni del server perimetrale

Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:

- Impostazioni generali

- Impostazioni per la selezione dell'hop successivo

- Configurazione dei server perimetrali



## <a name="general-settings"></a>Impostazioni generali

Nome di dominio completo (FQDN) interno del pool di server perimetrali. Modificare l'FQDN del pool per cambiare questa impostazione.

Selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061)** se si configura la federazione con un partner attendibile Lync Server 2013, Microsoft Lync Server 2010 o Microsoft Office Communications Server 2007 R2.

Selezionare **Abilita la federazione XMPP per questo pool di server perimetrali (porta 5269)** per abilitare la federazione XMPP.

Specificare il numero di porta per **Porta di replica configurazione interna (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Impostazioni per la selezione dell'hop successivo

Per impostare o modificare il pool hop successivo che verrà utilizzato dai server perimetrali per comunicare con l'infrastruttura interna, selezionare un **director,** un pool di server Director, un Front End Server o un pool Front End Server dalla casella di riepilogo a discesa. Solo i Director o i Front End Server configurati in Generatore di topologie verranno visualizzati per la selezione.

## <a name="edge-server-configuration"></a>Configurazione dei server perimetrali

Per modificare o specificare le opzioni per **Impostazioni esterne** per i server perimetrali, è necessario prima di tutto determinare se verranno usati indirizzi IP separati per l'accesso SIP, il servizio Web Conferencing e il servizio Audio/Video.

Se per ognuno si vuole usare indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS corrispondente.

Per ogni servizio con accesso all'esterno, specificare un FQDN e una porta associata. Ad esempio, per **Accesso SIP** è possibile usare sip.contoso.com con la porta 5061 associata.

> [!IMPORTANT]
> Se si selezionano FQDN separati per ognuno dei servizi con accesso all'esterno, a ogni servizio deve essere associato un valore di porta univoco. Per impostazione predefinita, sip è sulla porta 5061/TLS, il servizio Web Conferencing Edge si trova sulla porta 444/TLS e A/V Conferencing Server è sulla porta 443/TLS. Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di usare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.

> [!IMPORTANT]
> Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Edge, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


