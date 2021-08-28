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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
ms.openlocfilehash: 7f771875605ffef130b430fd7c7a00d9d1a63873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613766"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Distribuire più siti in Cloud Connector

> [!Important] 
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
  
In questa sezione viene descritto come distribuire più siti PSTN (Public Switched Telephone Network). I siti vengono distribuiti uno alla volta utilizzando gli stessi passaggi della distribuzione di un singolo sito. In questo argomento vengono descritte le considerazioni e le differenze tra i siti in una distribuzione a più siti. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Più siti PSTN (Public Switched Telephone Network)

Di seguito viene illustrata una configurazione di esempio per la Skype for Business Cloud Connector Edition per siti PSTN diversi. Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.
  
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

Per ogni sito PSTN che si desidera aggiungere, seguire i passaggi descritti in [Deploy a single site in Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> La cartella condivisa per la preparazione della disponibilità elevata è per ogni sito PSTN. La cartella condivisa **deve** essere diversa tra i siti PSTN. Non utilizzare la stessa cartella condivisa per più siti.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sito singolo con disponibilità elevata rispetto alle distribuzioni multisocietà
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Nella tabella seguente sono elencate le differenze tra un singolo sito con supporto ha e una distribuzione a più siti.
  
|**Categoria**|**Elemento**|**Sito singolo con ha**|**Multisnode**|
|:-----|:-----|:-----|:-----|
|Configura  <br/> |Nome host appliance <br/> |**Diversi** tra gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Installazione  <br/> |Cartella condivisa  <br/> |Richiede la **stessa cartella** condivisa tra le appliance <br/> |Richiede una **cartella condivisa** diversa tra le appliance <br/> |
|Configura  <br/> |VirtualMachineDomain  <br/> |Richiede lo **stesso dominio** tra le appliance <br/> |Richiede lo **stesso dominio** tra i siti PSTN <br/> |
|Configura  <br/> |SIPDomains  <br/> |I nomi di dominio e l'ordine devono **essere gli stessi tra** le appliance <br/> |I nomi di dominio e l'ordine devono **essere uguali nei** siti PSTN <br/> |
|Configura  <br/> |Nome sito  <br/> |**Same** Nome sito tra appliance <br/> |**Differente** Nome sito nei siti PSTN <br/> |
|Configura  <br/> |Nomi dei server  <br/> |**Diversi** tra gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Configura  <br/> |FQDN del pool interno  <br/> |**Uguale per** tutti gli appliance <br/> |**Stessa cosa** nei siti PSTN <br/> |
|Configura  <br/> |IP interni  <br/> |**Diversi** tra gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Configura  <br/> |FQDN esterno  <br/> |**Uguale per** tutti gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Configura  <br/> |IP esterni  <br/> |**Diversi** tra gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Configura  <br/> |Impostazioni PSTN GW  <br/> |**Uguale per** tutti gli appliance <br/> |**Diversi** tra i siti PSTN <br/> |
|Configura  <br/> |Record DNS  <br/> |Aggiungere record con gli **stessi** FQDN di accesso esterno e **indirizzi** IP diversi <br/> |Aggiungere record con **fqdn** di accesso esterno diversi e **indirizzi** IP diversi <br/> |
|Installazione  <br/> |Tenant ibrido  <br/> |Set HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |Set HybridPSTNSite  <br/> Impostare PeerDestination per il fallback  <br/> |
|Installazione  <br/> |Gateway  <br/> |Ms GW **M:N** mapping in questo sito <br/> |I gateway PSTN in ogni sito PSTN devono connettersi solo ai Mediation Server nello stesso sito  <br/> |
|Installazione  <br/> |Utente  <br/> |Impostare UserPSTNSettings  <br/> |Impostare UserPSTNSettings  <br/> |
