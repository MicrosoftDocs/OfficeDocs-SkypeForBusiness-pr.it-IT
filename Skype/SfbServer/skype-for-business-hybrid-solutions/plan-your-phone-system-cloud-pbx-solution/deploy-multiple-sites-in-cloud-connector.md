---
title: Distribuire più siti in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
ms.openlocfilehash: 1276d436a05e5151bdc90c19bbf41b8e90d913bf
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887635"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Distribuire più siti in Cloud Connector
 
Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
  
Questa sezione descrive come distribuire più siti PSTN (Public Switched Telephone Network). I siti vengono distribuiti uno alla volta con gli stessi passaggi della distribuzione di un singolo sito. In questo argomento vengono illustrate le considerazioni relative alle differenze tra i siti in una distribuzione di più siti. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Più siti PSTN (Public Switched Telephone Network)

Di seguito viene illustrata una configurazione di esempio per distribuire Skype for Business Cloud Connector Edition per diversi siti PSTN. Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.
  
Sito PSTN 1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

Sito PSTN 2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Per ogni sito PSTN che si vuole aggiungere, seguire la procedura descritta in [distribuire un singolo sito nel connettore Cloud](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La cartella condivisa per la preparazione della disponibilità elevata (HA) è per ogni sito PSTN. La cartella condivisa **deve** essere diversa tra i siti PSTN. Non usare la stessa cartella condivisa per più siti. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sito singolo con elevata disponibilità (HA) rispetto alle distribuzioni multisito
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

La tabella seguente elenca le differenze tra il sito singolo con il supporto di HA e una distribuzione di più siti.
  
|**Categoria**|**Elemento**|**Singolo sito con HA**|**Multi-sito**|
|:-----|:-----|:-----|:-----|
|Configurare  <br/> |Nome host Appliance <br/> |**Diversi** dispositivi tra loro <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurazione  <br/> |Cartella condivisa  <br/> |Richiede la **stessa** cartella condivisa tra gli elettrodomestici <br/> |Richiede una cartella condivisa **diversa** tra gli elettrodomestici <br/> |
|Configurare  <br/> |VirtualMachineDomain  <br/> |Richiede lo **stesso** dominio tra gli elettrodomestici <br/> |Richiede lo **stesso** dominio nei siti PSTN <br/> |
|Configurare  <br/> |SIPDomains  <br/> |I nomi di dominio e l'ordine devono essere **uguali** per tutti gli elettrodomestici <br/> |I nomi di dominio e l'ordine devono essere **uguali** in tutti i siti PSTN <br/> |
|Configurare  <br/> |Nome sito  <br/> |**Stessa** Nome sito tra gli elettrodomestici <br/> |**Diversi** Nome sito nei siti PSTN <br/> |
|Configurare  <br/> |Nomi dei server  <br/> |**Diversi** dispositivi tra loro <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurare  <br/> |FQDN del pool interno  <br/> |**Stessa** tra gli elettrodomestici <br/> |**Lo stesso** per tutti i siti PSTN <br/> |
|Configurare  <br/> |IPs interno  <br/> |**Diversi** dispositivi tra loro <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurare  <br/> |FQDN esterno  <br/> |**Stessa** tra gli elettrodomestici <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurare  <br/> |IPs esterni  <br/> |**Diversi** dispositivi tra loro <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurare  <br/> |Impostazioni GW PSTN  <br/> |**Stessa** tra gli elettrodomestici <br/> |**Diversi** tra i siti PSTN <br/> |
|Configurare  <br/> |Record DNS  <br/> |Aggiungere record con gli **stessi** FQDN di accesso esterno e indirizzi IP **diversi** <br/> |Aggiungere record con FQDN di accesso esterno **diverso** e indirizzi IP **diversi** <br/> |
|Configurazione  <br/> |Tenant ibrido  <br/> |Impostare HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |Impostare HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |
|Configurazione  <br/> |Gateway  <br/> |Mappatura di MS GW **M:N** in questo sito <br/> |I gateway PSTN in ogni sito PSTN devono connettersi solo ai server di mediazione nello stesso sito  <br/> |
|Configurazione  <br/> |Utente  <br/> |Impostare UserPSTNSettings  <br/> |Impostare UserPSTNSettings  <br/> |
   

