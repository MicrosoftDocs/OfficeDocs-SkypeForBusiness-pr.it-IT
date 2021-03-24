---
title: Espansione delle impostazioni del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:'
ms.openlocfilehash: c887ffaa16818e377035109632871b7bc7ed25d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108802"
---
# <a name="edge-settings-expander"></a>Espansione delle impostazioni del server perimetrale

Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:

- Impostazioni generali

- Impostazioni per la selezione dell'hop successivo

- Configurazione dei server perimetrali


## <a name="general-settings"></a>Impostazioni generali

Nome di dominio completo (FQDN) interno del pool di server perimetrali. Modificare l'FQDN del pool per cambiare questa impostazione.

Selezionare la casella di controllo Abilita federazione per questo pool di server perimetrali **(porta 5061)** se si configura la federazione con un server Skype for Business Server 2015.

Specificare il numero di porta per **Porta di replica configurazione interna (HTTPS)**.

## <a name="next-hop-selection-settings"></a>Impostazioni per la selezione dell'hop successivo

Per impostare o modificare il **pool hop** successivo che verrà utilizzato dai server perimetrali per comunicare con l'infrastruttura interna, selezionare un server Director, un pool di server Director, un Front End Server o un pool Front End Server dalla casella di riepilogo a discesa. Solo i Director o i Front End configurati in Generatore di topologie verranno visualizzati per la selezione.

## <a name="edge-server-configuration"></a>Configurazione dei server perimetrali

Per modificare o specificare le opzioni per **Impostazioni esterne** per i server perimetrali, è necessario prima di tutto determinare se verranno usati indirizzi IP separati per l'accesso SIP, il servizio Web Conferencing e il servizio Audio/Video.

Se per ognuno si vuole usare indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS corrispondente.

Per ogni servizio con accesso all'esterno, specificare un FQDN e una porta associata. Ad esempio, per **Accesso SIP** è possibile usare sip.contoso.com con la porta 5061 associata.

> [!IMPORTANT]
> Se si selezionano FQDN separati per ognuno dei servizi con accesso all'esterno, a ogni servizio deve essere associato un valore di porta univoco. Per impostazione predefinita, il SIP si trova sulla porta 5061/TLS, il servizio Web Conferencing Edge si trova sulla porta 444/TLS e A/V Conferencing Server è sulla porta 443/TLS. Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di usare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.

> [!IMPORTANT]
> Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Edge, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).