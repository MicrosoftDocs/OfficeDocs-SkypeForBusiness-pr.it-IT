---
title: Scenari di Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Riepilogo: rivedere questi scenari per pianificare la topologia di Edge Server in Skype for Business Server.'
ms.openlocfilehash: 64d38b5c9b4a32991bf87bd6ba8af87c92db115f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754166"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Scenari di Edge Server in Skype for Business Server
 
**Riepilogo:** Esaminare questi scenari per pianificare la topologia di Edge Server in Skype for Business Server.
  
Sono disponibili alcuni diagrammi scenari per facilitare la visualizzazione e la scelta della topologia di Skype for Business Server Edge Server che si vuole implementare. Dopo aver scelto un buon candidato, è possibile leggere i requisiti ambientali che è necessario affrontare. La procedura seguente è applicabile a qualsiasi scenario, quindi la menzioniamo per primo.
  
Queste cifre, visualizzate ad esempio solo per scopi (e come tali contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, ma piuttosto una visualizzazione di alto livello del traffico possibile. I dettagli della porta possono essere visualizzati anche nei diagrammi di porta per ogni scenario seguente.
  
I diagrammi mostrano. com per l'interfaccia esterna e .NET per l'interno, che è anche materiale di esempio; Naturalmente, le tue voci possono essere molto diverse quando si sta mettendo insieme il proprio piano finale.
  
Non includiamo il Director (che è un componente facoltativo) in uno dei diagrammi, ma è possibile leggerlo separatamente (menzionato in altri argomenti della pianificazione).
  
Come indicato in precedenza, nei diagrammi sono presenti dati IPv6 di esempio. La maggior parte della documentazione in [piano per le distribuzioni di Edge Server in Skype for Business Server](edge-server-deployments.md) si riferisce a IPv4, ma si è certamente supportati se si vuole usare IPv6. Tieni presente che ti serviranno indirizzi IPv6 nello spazio di indirizzi assegnato e dovrai usare l'indirizzamento interno ed esterno, come per gli IPs IPv4. Grazie a Windows, è possibile usare la caratteristica dual stack, che è uno stack di rete distinto per IPv4 e IPv6. Questa operazione, se necessario, consente di assegnare contemporaneamente indirizzi IPv4 e IPv6.
  
Esistono dispositivi NAT che consentono di NAT64 (IPv6 a IPv4) e NAT66 (IPv6 to IPv6)) e questo è valido per l'uso con Skype for Business Server.
  
> [!IMPORTANT]
> Se si usa il controllo di ammissione di chiamata (CAC), è necessario usare IPv4 sull'interfaccia interna per farlo funzionare. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Singolo server Edge Skype for business consolidato con indirizzi IP privati e NAT

Con questo scenario, non esiste alcuna opzione per la disponibilità elevata. In questo modo si spende meno sull'hardware e si ha una distribuzione più semplice. Se la disponibilità elevata è necessaria, vedere gli scenari consolidati in scala più avanti.
  
![Scenario Edge per il singolo Edge consolidato con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma di porta

È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per lo scenario Edge Single Edge consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Singolo server Edge Skype for business consolidato con indirizzi IP pubblici

Con questo scenario, non esiste alcuna opzione per la disponibilità elevata. In questo modo si spende meno sull'hardware e si ha una distribuzione più semplice. Se la disponibilità elevata è necessaria, vedere gli scenari consolidati in scala più avanti.
  
![Scenario Edge per il singolo Edge consolidato con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma di porta

È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per lo scenario Edge Single Edge consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>In scala consolidato Skype for Business Server Edge pool, con DNS bilanciamento del carico e indirizzi IP privati e NAT

Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.
  
![Scenario Edge per Edge consolidato in scala, DNS LB con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma di porta

È inoltre presente un diagramma per i pool di bordi consolidati in scala con il bilanciamento del carico DNS.
  
![Perimetro di rete per lo scenario Edge in scala consolidata con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>In scala consolidato Skype for Business Server Edge pool, con DNS di bilanciamento del carico e indirizzi IP pubblici

Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.
  
![Scenario Edge per Edge consolidato in scala, DNS LB con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma di porta

È inoltre presente un diagramma per i pool di bordi consolidati in scala con il bilanciamento del carico DNS.
  
![Perimetro di rete per lo scenario Edge in scala consolidata con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Scala consolidata di Skype for Business Server Edge pool con bilanciamento del carico hardware

Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.
  
![Scenario Edge per il bordo consolidato in scala con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
