---
title: Scenari di server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Riepilogo: esaminare questi scenari per pianificare la topologia dei server perimetrali in Skype for Business Server.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813792"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Scenari di server perimetrali in Skype for Business Server
 
**Riepilogo:** Esaminare questi scenari per pianificare la topologia dei server perimetrali in Skype for Business Server.
  
Alcuni diagrammi di scenari sono utili per visualizzare e decidere quale topologia di Server perimetrale di Skype for Business Server si desidera implementare. Dopo aver scelto un buon candidato, puoi leggere i requisiti ambientali che dovrai soddisfare. Quanto segue è applicabile a uno qualsiasi degli scenari, quindi viene menzionato per primo.
  
Queste figure, mostrate solo a scopo di esempio (e che contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, ma piuttosto una visualizzazione di alto livello del traffico possibile. I dettagli sulle porte sono disponibili anche nei diagrammi delle porte per ogni scenario seguente.
  
I diagrammi mostrano .com per l'interfaccia esterna e .net per l'interno, che è anche materiale di esempio; Naturalmente, le voci potrebbero essere molto diverse quando si sta mettendo insieme il proprio piano Edge finale.
  
Non è incluso il Director (che è un componente facoltativo) in nessuno dei diagrammi, ma è possibile leggerlo separatamente (è menzionato in altri argomenti relativi alla pianificazione).
  
Come indicato in precedenza, sono presenti dati IPv6 di esempio nei diagrammi. La maggior parte della documentazione in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) farà riferimento a IPv4, ma sei sicuramente supportato se vuoi usare IPv6. Si noti che gli indirizzi IPv6 saranno necessari nello spazio di indirizzi assegnato e dovranno funzionare con l'indirizzamento interno ed esterno, come con gli INDIRIZZI IP IPv4. È possibile, grazie a Windows, utilizzare la funzionalità dual stack, che è uno stack di rete separato e distinto per IPv4 e IPv6. In questo modo, se necessario, sarà possibile assegnare gli indirizzi IPv4 e IPv6 contemporaneamente.
  
Esistono dispositivi NAT che consentono NAT64 (da IPv6 a IPv4) e NAT66 (da IPv6 a IPv6) e questo è valido per l'uso con Skype for Business Server.
  
> [!IMPORTANT]
> Se si utilizza il servizio Controllo di ammissione di chiamata, è necessario utilizzare IPv4 sull'interfaccia interna per il funzionamento. 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>Singolo server perimetrale di Skype for Business Server consolidato con indirizzi IP privati e NAT

Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata. Questo significa che spendi meno sull'hardware e hai una distribuzione più semplice. Se la disponibilità elevata è un'opzione importante, vedere gli scenari consolidati con scalabilità orizzontale riportati di seguito.
  
![Scenario perimetrale per singola topologia perimetrale consolidata con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per server perimetrali Singolo server perimetrale consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>Singolo server perimetrale di Skype for Business Server consolidato con indirizzi IP pubblici

Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata. Questo significa che spendi meno sull'hardware e hai una distribuzione più semplice. Se la disponibilità elevata è un'opzione importante, vedere gli scenari consolidati con scalabilità orizzontale riportati di seguito.
  
![Scenario perimetrale per singola topologia perimetrale consolidata con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.
  
![Perimetro di rete per server perimetrali Singolo server perimetrale consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>Pool di server perimetrali Skype for Business Server consolidato con scalabilità verticale, con bilanciamento del carico DNS, indirizzi IP privati e NAT

Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.
  
![Scenario perimetrale per topologia perimetrale consolidata con scalabilità consolidata, DNS LB con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.
  
![Perimetro di rete per server perimetrale consolidato con scalabilità orizzontale utilizzando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>Pool di server perimetrali Skype for Business Server consolidato con scalabilità consolidata, con bilanciamento del carico DNS e indirizzi IP pubblici

Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.
  
![Scenario perimetrale per topologia perimetrale consolidata con scalabilità orizzontale, DNS LB con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>Diagramma delle porte

È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.
  
![Perimetro di rete per server perimetrale consolidato con scalabilità orizzontale utilizzando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>Pool di server perimetrali Skype for Business Server consolidato con scalabilità consolidata, con bilanciamento del carico hardware

Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.
  
![Scenario perimetrale per server perimetrale consolidato con scalabilità orizzontale con bilanciamento del carico di rete](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
