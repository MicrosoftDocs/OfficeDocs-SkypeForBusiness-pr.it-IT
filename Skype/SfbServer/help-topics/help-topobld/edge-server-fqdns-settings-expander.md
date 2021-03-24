---
title: Espansione delle impostazioni dei nomi di dominio completi (FQDN) per il server perimetrale
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
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Per modificare o specificare le impostazioni esterne per i server perimetrali, è innanzitutto necessario determinare se si utilizzeranno indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095561"
---
# <a name="edge-server-fqdns-settings-expander"></a>Espansione delle impostazioni dei nomi di dominio completi (FQDN) per il server perimetrale

Per modificare  o specificare le impostazioni esterne per i server perimetrali, è innanzitutto necessario determinare se si utilizzeranno indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.

Se si intende utilizzare per ognuno indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS (Domain Name System) corrispondente.

Per ogni servizio con accesso all'esterno, specificare un nome di dominio completo (FQDN) e una porta associata. Ad esempio, per **Accesso SIP** è possibile utilizzare sip.contoso.com con la porta 5061 associata.

> [!IMPORTANT]
> Se si selezionano FQDN distinti per ognuno dei servizi con accesso all'esterno, a ciascun servizio deve essere associato un valore di porta univoco. Per impostazione predefinita, SIP è sulla porta 5061/TLS, il servizio Web Conferencing Edge è sulla porta 444/TLS e il servizio A/V Conferencing Edge è sulla porta 443/TLS. Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.

> [!IMPORTANT]
> Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.

Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Perimetrali, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).