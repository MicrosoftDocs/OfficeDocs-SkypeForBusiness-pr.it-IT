---
title: Pianificare IPv6 in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Riepilogo: implementare IPv6 prima di installare Skype for Business Server.'
ms.openlocfilehash: e4af5403ce416332ec7c75ca26522038fd9c42df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194912"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Pianificare IPv6 in Skype for Business
 
**Riepilogo:** Implementare IPv6 prima di installare Skype for Business Server.
  
Skype for Business Server include il supporto per gli indirizzi IP versione 6 (IPv6), oltre al supporto continuo degli indirizzi IP versione 4 (IPv4). 

Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili sono esauriti. Per questo motivo, molti nuovi dispositivi si spostano nell'uso degli indirizzi IPv6. Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di usare solo 32 bit, gli indirizzi IPv6 usano 128 bit. Questo fornisce non solo un nuovo set di indirizzi, ma anche un numero molto più grande. 

Un indirizzo IPv4 tipico ha un aspetto simile al seguente: 192.0.2.235, mentre un indirizzo IPv6 ha un aspetto simile al seguente: 2001:0DB8:85a3:0000:0000:8a2e: 0370:7334. La modifica della formattazione e della funzionalità per i dispositivi che usano indirizzi IPv6 richiede diverse considerazioni sulla distribuzione e la configurazione nell'installazione di Skype for Business Server. 

Questo argomento include le sezioni seguenti:
  
- [Panoramica dei tipi di indirizzo IP](ipv6.md#over)
    
- [Requisiti tecnici per IPv6](ipv6.md#tech)
    
- [Considerazioni sulla migrazione e la coesistenza per IPv6](ipv6.md#migration)
    
Se si decide di usare gli indirizzi IPv6, vedere l'articolo [configurare i tipi di indirizzo IP in Skype for business](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Panoramica dei tipi di indirizzo IP
<a name="over"> </a>

Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Skype for Business Server. Puoi configurare Skype for Business Server per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come stack duale). Esistono diversi problemi da considerare con ogni tipo di configurazione:
  
- **Solo IPv4** IPv6 è stato creato perché il mondo è in esaurimento degli indirizzi IPv4. In definitiva, IPv6 sarà completamente supportato in tutto il mondo, ma in questo momento, molte aziende e dispositivi di cui l'organizzazione potrebbe dover comunicare non supportano ancora IPv6 e potrebbero non essere da qualche tempo. Una configurazione solo IPv4 consentirà di garantire che l'implementazione di Skype for Business Server possa comunicare con la maggior parte dei dispositivi esistenti.
    
- **Solo IPv6** Viceversa, un'implementazione completa di IPv6 escluderà la comunicazione con molti dispositivi esistenti.
    
- **Stack doppio** Dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che IPv6. Questa configurazione è supportata in Skype for Business Server, perché nella maggior parte dei casi la transizione da Full-IPv4 a full-IPv6 avrà diversi anni.
    
Le sezioni seguenti illustrano la compatibilità tra queste tre configurazioni per varie funzionalità di Skype for Business Server.
  
> [!NOTE]
> La configurazione client o server con IPv6 è supportata solo per scopi di laboratorio o di convalida. La configurazione solo IPv6 non è supportata nella distribuzione della produzione. 
  
### <a name="client-registration"></a>Registrazione client
<a name="client"> </a>

|**Rete endpoint client**|**Server di rete**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Stack doppio  <br/> |
|Stack doppio  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |
|Stack doppio  <br/> |IPv6  <br/> |
|IPv6  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Client peer-to-peer
<a name="peer"> </a>

Le comunicazioni peer-to-peer includono audio, audio/video, condivisione applicazioni e trasferimento di file. Dopo aver registrato correttamente entrambi i client, sono supportate le combinazioni seguenti.
  
|**Endpoint client 1**|**Endpoint client 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Stack doppio  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Servizi di conferenza
<a name="conf"> </a>

I servizi di conferenza includono applicazioni audio/video, condivisione applicazioni e collaborazione dati come la lavagna e la condivisione di file.
  
|**Rete endpoint client**|**Server di rete**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Stack doppio  <br/> |
|Stack doppio  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |
|Stack doppio  <br/> |IPv6  <br/> |
|IPv6  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Mediation Server/PSTN
<a name="med"> </a>

Skype for Business Server non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network), se il traffico avviene tramite un'interfaccia IPv6. Se è necessario un bypass multimediale, è consigliabile che il gateway PSTN sia configurato per IPv4. 
  
|**Interfaccia primaria 1**|**Interfaccia PSTN (in Mediation Server)**|**Impostazione del gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Stack doppio  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |IPv6  <br/> |
   
1. L'interfaccia principale è l'interfaccia che comunica con i componenti di Skype for Business Server.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicazioni peer-to-peer degli utenti remoti
<a name="remote"> </a>

Le comunicazioni peer-to-peer con gli utenti remoti includono messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.
  
|**Rete remota degli utenti**|**Edge Server (bordo esterno)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |IPv4  <br/> |
|Stack doppio  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |Stack doppio  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configurazione di pool e Edge pool Front-End
<a name="FE_pool"> </a>

La tabella seguente mostra la matrice di supporto tra il pool del server front-end e il pool di Edge Server interno.
  
**Pool di front end e pool Edge (bordo interno)**

||**Bordo piscina: IPv4** <br/> |**Bordo piscina: doppia pila** <br/> |**Pool Edge: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Front-end: IPv4** <br/> |Sì  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|**Pool Front-end: doppia pila** <br/> |Sì  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|**Pool Front-end: IPv6** <br/> |No  <br/> |No  <br/> |Sì\*  <br/> |
   
\*Usare questa combinazione solo in un ambiente lab.
  
La tabella seguente è una matrice delle combinazioni supportate delle interfacce Edge interne ed esterne.
  
**Matrice pool Edge (bordo interno) e bordo piscina (bordo esterno)**

||**Pool Edge (bordo esterno): IPv4** <br/> |**Pool Edge (bordo esterno): doppia pila** <br/> |**Pool Edge (bordo esterno): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Edge (bordo interno): IPv4** <br/> |Sì  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|**Pool di bordi (bordo interno): doppia pila** <br/> |No  <br/> |Sì  <br/> |Supporto per riunioni private con ID conferenza di riunione dinamici  <br/> |
|**Pool Edge (bordo interno): IPv6** <br/> |No  <br/> |No  <br/> |Sì\*  <br/> |
   
\*Usare questa combinazione solo in un ambiente lab.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Supporto per VoIP aziendale avanzato per IPv6
<a name="Ent_V"> </a>

Le distribuzioni che includono il controllo di ammissione alle chiamate (CAC), il 9-1-1 avanzato (E9-1-1) o l'esclusione multimediale devono essere configurate solo come IPv4 o come implementazione a doppio stack. Gli endpoint che usano solo IPv6 non possono usare queste funzionalità.
  
> [!NOTE]
> In una distribuzione a doppio stack, anche se un client di Skype for Business Server si connette a un server Skype for business usando IPv6, Skype for Business Server è il migliore per eseguire il mapping di un indirizzo IPv4 appropriato per il supporto di E9-1-1. 
  
Il servizio informazioni sulla posizione con indirizzi IPv6 non è supportato.
  
La messaggistica unificata di Exchange non supporta IPv6. Per la messaggistica unificata di Exchange, assicurati che la risoluzione DNS non restituisca un indirizzo IPv6. L'uso di IPv6 può causare un errore quando le chiamate vengono inviate alla segreteria telefonica. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Altre funzionalità del supporto per Skype for Business Server per IPv6
<a name="Ent_V"> </a>

Oltre alle caratteristiche e ai componenti menzionati in precedenza, Skype for Business Server supporta IPv6 per le caratteristiche seguenti:
  
- **Chat persistente**
    
    Si configura IPv6 per la chat persistente usando generatore di topologie. Per informazioni dettagliate sulla configurazione della chat persistente, vedere la documentazione relativa alla distribuzione di Persistent Chat Server.
    
- **Report di qualità dei dati (QoE) e registrazione dei dettagli delle chiamate (CDR)**
    
    I report di monitoraggio includono l'indirizzo IP archiviato nel database del server di monitoraggio, indipendentemente dal tipo IPv4 o IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisiti tecnici per IPv6
<a name="tech"> </a>

Se si prevede di configurare Skype for Business Server per IPv6, tieni presente quanto segue:
  
- Per usare gli indirizzi IPv6 con Skype for Business Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6. DNS IPv6 usa record AAAA (Quad-A) host. Se si usano sia IPv4 che IPv6 nella distribuzione, è consigliabile configurare e gestire sia l'host di un record per IPv4 che i record AAAA host per IPv6. Anche quando si passa completamente la distribuzione a IPv6, è possibile che siano ancora necessari record host DNS IPv4 per gli utenti esterni che usano ancora IPv4.
    
    È possibile distribuire record host DNS IPv6 prima di iniziare a usare IPv6. Se il client o il server non usa IPv6, non verrà fatto riferimento al record. Le tecnologie di transizione consentiranno di decidere quale record usare, in base alla configurazione e ai criteri di tecnologia di transizione.
    
- Ogni indirizzo IPv6 ha un ambito. I tre ambiti che è possibile usare per l'indirizzamento IPv6 sono indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), indirizzi locali univoci di IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e indirizzi locali del collegamento IPv6 (in modo simile agli indirizzi IP privati automatici in Windows Server per IPv4). Tutti i server all'interno di un pool devono avere indirizzi IPv6 con lo stesso ambito. 
    
> [!IMPORTANT]
> IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarti che gli indirizzi assegnati a livello di Windows Server e a livello di Skype for Business Server funzionino come previsto. Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerazioni sulla migrazione e la coesistenza per IPv6
<a name="migration"> </a>

IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server. Per scopi di pilotaggio, è possibile testare la coesistenza di Lync Server 2010 e Skype for Business Server dual-stack. È consigliabile che tutti i pool di un sito centrale vengano aggiornati a Skype for Business Server prima di abilitare IPv6 (dual-stack Network) per tutti i pool. Se è necessario configurare solo un pool per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente lab per i test.
  
Gli scenari seguenti sono supportati durante la migrazione e la coesistenza:
  
- Skype for Business Server, Lync Server 2013 e Lync Server 2010 pool in modalità IPv4, che coesiste con Skype for Business Server in modalità dual-stack.
    
- Pool di Skype for Business Server in modalità solo IPv6, se il pool solo IPv6 è siloed.
    
## <a name="see-also"></a>Vedere anche
<a name="migration"> </a>

[Configurare i tipi di indirizzi IP in Skype for Business](ip-address-types.md)

[Architettura di indirizzamento IP versione 6](https://tools.ietf.org/html/rfc4291)
  
[Formato di indirizzo unicast globale IPv6](https://tools.ietf.org/html/rfc3587)
  
[Indirizzi unicast IPv6 locali univoci](https://tools.ietf.org/html/rfc4193)
