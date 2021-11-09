---
title: Scenari di server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Riepilogo: esaminare questi scenari per pianificare la topologia di server perimetrali in Skype for Business Server.'
ms.openlocfilehash: f70dbf858757469d21ebb8b2e6d1ae5192ed0118
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838528"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Scenari di server perimetrali in Skype for Business Server
 
**Riepilogo:** Esaminare questi scenari per pianificare la topologia di server perimetrali in Skype for Business Server.
  
Alcuni diagrammi di scenari sono utili per visualizzare e decidere Skype for Business Server topologia di server perimetrali che si desidera implementare. Dopo aver scelto un buon candidato, puoi leggere i requisiti ambientali che dovrai soddisfare. Quanto segue è applicabile a uno qualsiasi degli scenari, quindi viene menzionato per primo.
  
Queste cifre, mostrate solo a scopo di esempio (e come tali contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, ma piuttosto una visualizzazione di alto livello del traffico possibile. I dettagli delle porte sono disponibili anche nei diagrammi di porta per ogni scenario seguente.
  
I diagrammi mostrano .com per l'interfaccia esterna e .net per l'interno, che è anche materiale di esempio; Naturalmente, le voci potrebbero essere molto diverse quando si sta mettendo insieme il proprio piano Edge finale.
  
Il Director (che è un componente facoltativo) non è incluso in nessuno dei diagrammi, ma è possibile leggerlo separatamente (è menzionato in altri argomenti relativi alla pianificazione).
  
Come indicato in precedenza, nei diagrammi sono presenti dati IPv6 di esempio. La maggior parte della documentazione in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) farà riferimento a IPv4, ma è sicuramente supportata se si desidera utilizzare IPv6. Si noti che gli indirizzi IPv6 saranno necessari nello spazio di indirizzi assegnato e dovranno funzionare con l'indirizzamento interno ed esterno, come per gli IP IPv4. È possibile, grazie a Windows, utilizzare la funzionalità dual stack, che è uno stack di rete separato e distinto per IPv4 e IPv6. In questo modo, se necessario, sarà possibile assegnare gli indirizzi IPv4 e IPv6 contemporaneamente.
  
Esistono dispositivi NAT che consentono NAT64 (da IPv6 a IPv4) e NAT66 (da IPv6 a IPv6) e questo è valido per l'utilizzo con Skype for Business Server.
  
> [!IMPORTANT]
> Se si utilizza il servizio Controllo di ammissione di chiamata, è necessario utilizzare IPv4 sull'interfaccia interna per farlo funzionare. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Singolo server perimetrale consolidato Skype for Business Server server perimetrale con indirizzi IP privati e NAT

Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata. Ciò significa che si spende meno per l'hardware e si ha una distribuzione più semplice. Se la disponibilità elevata è un elemento necessario, vedere gli scenari consolidati con scalabilità ridotta riportati di seguito.
  
![Scenario edge per singolo server perimetrale consolidato con IP privato tramite NAT.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per edge Scenario singolo consolidato perimetrali.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Singolo server perimetrale Skype for Business Server consolidato con indirizzi IP pubblici

Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata. Ciò significa che si spende meno per l'hardware e si ha una distribuzione più semplice. Se la disponibilità elevata è un elemento necessario, vedere gli scenari consolidati con scalabilità ridotta riportati di seguito.
  
![Scenario edge per singolo server perimetrale consolidato con IP pubblico.](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per edge Scenario singolo consolidato perimetrali.](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Pool di server perimetrali Skype for Business Server con scalabilità consolidata, con bilanciamento del carico DNS e indirizzi IP privati e NAT

Con questo scenario, è possibile disporre di disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto della scalabilità e del failover.
  
![Scenario perimetrale per topologia perimetrale consolidata con scalabilità consolidata, LB DNS con IP privato tramite NAT.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.
  
![Perimetro di rete per server perimetrali topologia perimetrale consolidata con scalabilità orizzontale tramite DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Pool di server perimetrali Skype for Business Server con scalabilità consolidata, con bilanciamento del carico DNS e indirizzi IP pubblici

Con questo scenario, è possibile disporre di disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto della scalabilità e del failover.
  
![Scenario perimetrale per server perimetrale consolidato con scalabilità consolidata, LB DNS con IP pubblico.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.
  
![Perimetro di rete per server perimetrali topologia perimetrale consolidata con scalabilità orizzontale tramite DNS LB.](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Pool di server perimetrali Skype for Business Server con scalabilità consolidata, con bilanciamento del carico hardware

Con questo scenario, è possibile disporre di disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto della scalabilità e del failover.
  
![Scenario edge per server perimetrale consolidato con scalabilità orizzontale con bilanciamento del carico di rete.](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
