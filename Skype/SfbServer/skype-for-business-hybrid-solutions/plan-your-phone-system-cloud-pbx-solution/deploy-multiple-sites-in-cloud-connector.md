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
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358922"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Distribuire più siti in Cloud Connector

> [!Important] 
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
  
In questa sezione viene descritto come distribuire più siti PSTN (Public Switched Telephone Network). I siti vengono distribuiti uno alla volta utilizzando gli stessi passaggi della distribuzione di un singolo sito. In questo argomento vengono illustrate le considerazioni relative alle differenze tra i siti di una distribuzione a più siti. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Più siti PSTN (Public Switched Telephone Network)

Di seguito viene illustrata una configurazione di esempio per la distribuzione di Skype for Business Cloud Connector Edition per diversi siti PSTN. Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.
  
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

Per ogni sito PSTN che si desidera aggiungere, seguire la procedura illustrata in [deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La cartella condivisa per la preparazione della disponibilità elevata (HA) è per ogni sito PSTN. La cartella condivisa **deve** essere diversa tra i siti PSTN. Non utilizzare la stessa cartella condivisa per più siti. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sito singolo con disponibilità elevata (HA) rispetto alle distribuzioni multisito
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Nella tabella seguente sono elencate le differenze tra sito singolo con supporto HA e una distribuzione a più siti.
  
|**Categoria**|**Elemento**|**Sito singolo con HA**|**Multi-sito**|
|:-----|:-----|:-----|:-----|
|Configurazione  <br/> |Nome host dell'accessorio <br/> |**Diversa** tra gli strumenti <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |Cartella condivisa  <br/> |Richiede la **stessa** cartella condivisa tra gli strumenti <br/> |Richiede una cartella condivisa **diversa** tra gli strumenti <br/> |
|Configurazione  <br/> |VirtualMachineDomain  <br/> |Richiede lo **stesso** dominio tra gli strumenti <br/> |Richiede lo **stesso** dominio tra i siti PSTN <br/> |
|Configurazione  <br/> |SIPDomains  <br/> |I nomi di dominio e l'ordine devono essere **uguali** tra gli strumenti <br/> |I nomi di dominio e l'ordine devono essere **uguali** nei siti PSTN <br/> |
|Configurazione  <br/> |Nome sito  <br/> |**Lo stesso** Nome del sito tra gli strumenti <br/> |**Diversa** Nome del sito tra siti PSTN <br/> |
|Configurazione  <br/> |Nomi dei server  <br/> |**Diversa** tra gli strumenti <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |FQDN del pool interno  <br/> |**Stesso** tra gli elettrodomestici <br/> |**Lo stesso** tra i siti PSTN <br/> |
|Configurazione  <br/> |Indirizzi IP interni  <br/> |**Diversa** tra gli strumenti <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |FQDN esterno  <br/> |**Stesso** tra gli elettrodomestici <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |Indirizzi IP esterni  <br/> |**Diversa** tra gli strumenti <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |Impostazioni GW PSTN  <br/> |**Stesso** tra gli elettrodomestici <br/> |**Diversa** tra i siti PSTN <br/> |
|Configurazione  <br/> |Record DNS  <br/> |Aggiungere record con gli **stessi** FQDN di accesso esterno e indirizzi IP **diversi** <br/> |Aggiungere record con nomi FQDN di accesso esterno **diversi** e indirizzi IP **diversi** <br/> |
|Configurazione  <br/> |Tenant ibrido  <br/> |Impostare HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |Impostare HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |
|Configurazione  <br/> |Gateway  <br/> |Mapping di MS GW **M:N** in questo sito <br/> |I gateway PSTN in ciascun sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.  <br/> |
|Configurazione  <br/> |Utente  <br/> |Impostare UserPSTNSettings  <br/> |Impostare UserPSTNSettings  <br/> |
   

