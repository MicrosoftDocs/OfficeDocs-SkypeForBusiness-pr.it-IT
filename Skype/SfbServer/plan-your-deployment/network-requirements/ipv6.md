---
title: Pianificare IPv6 in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Riepilogo: implementare IPv6 prima di installare Skype for Business Server.'
ms.openlocfilehash: 02753ad0e2fee00e548dd2f709dc451373283cae2fe0fe2e30dbae62e77f12f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289674"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Pianificare IPv6 in Skype for Business
 
**Riepilogo:** Implementare IPv6 prima di installare Skype for Business Server.
  
Skype for Business Server include il supporto per gli indirizzi IP versione 6 (IPv6), insieme al supporto continuo degli indirizzi IP versione 4 (IPv4). 

Gli indirizzi IPv4 sono indirizzi a 32 bit che consentono a un computer di comunicare tramite Internet. A causa del numero crescente di dispositivi in tutto il mondo, gli indirizzi IPv4 disponibili si sono eseguiti. Per questo, molti nuovi dispositivi stanno passando all'uso di indirizzi IPv6. Gli indirizzi IPv6 eseguono la stessa funzione degli indirizzi IPv4 (con alcune funzionalità aggiuntive), ma invece di utilizzare solo 32 bit, gli indirizzi IPv6 utilizzano 128 bit. In questo modo non solo viene fornito un nuovo set di indirizzi, ma anche un numero molto maggiore di indirizzi. 

Un indirizzo IPv4 tipico è simile al seguente: 192.0.2.235, mentre un indirizzo IPv6 è simile al seguente: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. La modifica della formattazione e delle funzionalità per i dispositivi che utilizzano indirizzi IPv6 richiede diverse considerazioni sulla distribuzione e sulla configurazione nell Skype for Business Server installazione. 

In questo argomento sono incluse le sezioni seguenti:
  
- [Panoramica dei tipi di indirizzi IP](ipv6.md#over)
    
- [Requisiti tecnici per IPv6](ipv6.md#tech)
    
- [Considerazioni sulla migrazione e la coesistenza per IPv6](ipv6.md#migration)
    
Se si determina che verranno utilizzati indirizzi IPv6, vedere l'articolo Configurare i tipi di indirizzi [IP in Skype for Business.](ip-address-types.md)
  
## <a name="overview-of-ip-address-types"></a>Panoramica dei tipi di indirizzi IP
<a name="over"> </a>

Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Skype for Business Server. È possibile configurare Skype for Business Server per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come dual stack). Per ogni tipo di configurazione è necessario considerare diversi problemi:
  
- **Solo IPv4** IPv6 è stato creato perché gli indirizzi IPv4 non sono più disponibili. In futuro IPv6 sarà completamente supportato in tutto il mondo, ma al momento molte aziende e molti dispositivi con cui potrebbe essere necessario comunicare non lo supportano ancora. Una configurazione solo IPv4 consente di garantire che l'implementazione Skype for Business Server possa comunicare con la maggior parte dei dispositivi esistenti.
    
- **Solo IPv6** Al contrario, un'implementazione IPv6 completa escluderà la comunicazione con molti dispositivi esistenti.
    
- **Dual Stack** Dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che gli indirizzi IPv6. Questa configurazione è supportata in Skype for Business Server perché nella maggior parte dei casi la transizione da full-IPv4 a full-IPv6 avrà diversi anni.
    
Nelle sezioni seguenti viene illustrata la compatibilità tra queste tre configurazioni per Skype for Business Server funzionalità.
  
> [!NOTE]
> La configurazione client o server con il solo protocollo IPv6 è supportata solo per fini di ricerca e di convalida. La configurazione Solo IPv6 non è supportata nella distribuzione di produzione. 
  
### <a name="client-registration"></a>Registrazione client
<a name="client"> </a>

|**Rete endpoint client**|**Rete server**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dual stack  <br/> |
|Dual stack  <br/> |IPv4  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |
|Dual stack  <br/> |IPv6  <br/> |
|IPv6  <br/> |Dual stack  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Client peer-to-peer
<a name="peer"> </a>

La comunicazione peer-to-peer include audio, audio/video, condivisione di applicazioni e trasferimento di file. Dopo la corretta registrazione di entrambi i client, sono supportate le combinazioni seguenti.
  
|**Endpoint client 1**|**Endpoint client 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dual stack  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |
|IPv6  <br/> |Dual stack  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Conferenze
<a name="conf"> </a>

Le conferenze includono applicazioni audio/video, condivisione applicazioni e collaborazione dati come lavagna e condivisione file.
  
|**Rete endpoint client**|**Rete server**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dual stack  <br/> |
|Dual stack  <br/> |IPv4  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |
|Dual stack  <br/> |IPv6  <br/> |
|IPv6  <br/> |Dual stack  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Mediation Server/PSTN
<a name="med"> </a>

Skype for Business Server non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network) se il traffico è attraverso un'interfaccia IPv6. Se il bypass multimediale è necessario, è consigliabile configurare il gateway PSTN su IPv4. 
  
|**Interfaccia principale 1**|**Interfaccia PSTN (in Mediation Server)**|**Impostazioni del gateway PSTN**|
|:-----|:-----|:-----|
|IPv4  <br/> |Dual stack  <br/> |IPv4  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |IPv4  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |IPv6  <br/> |
   
1. L'interfaccia principale è l'interfaccia che comunica con i Skype for Business Server componenti.
  
### <a name="remote-user-peer-to-peer-communications"></a>Comunicazioni peer-to-peer con utenti remoti
<a name="remote"> </a>

La comunicazione peer-to-peer con utenti remoti include messaggistica istantanea, audio/video, condivisione di applicazioni e trasferimento di file.
  
|**Rete utenti remoti**|**Server perimetrale (perimetro esterno)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Dual stack  <br/> |IPv4  <br/> |
|Dual stack  <br/> |Dual stack  <br/> |
|IPv6  <br/> |Dual stack  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Configurazione di pool Front End e di pool di server perimetrali
<a name="FE_pool"> </a>

Nella tabella seguente viene illustrata la matrice di supporto tra il pool Front End Server e il pool di server perimetrali interno.
  
**Matrice di pool Front End e di pool di server perimetrali (perimetro interno)**

||**Pool di server perimetrali: IPv4** <br/> |**Pool di server perimetrali: Dual Stack** <br/> |**Pool di server perimetrali: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool Front End: IPv4** <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|**Pool Front End: Dual Stack** <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|**Pool Front End: IPv6** <br/> |No  <br/> |No  <br/> |Sì\*  <br/> |
   
\* Utilizzare questa combinazione solo in un ambiente lab.
  
La tabella seguente è una matrice delle combinazioni supportate di interfacce di server perimetrali interni ed esterni.
  
**Matrice di pool di server perimetrali (perimetro interno) e di pool di server perimetrali (perimetro esterno)**

||**Pool di server perimetrali (perimetro esterno): IPv4** <br/> |**Pool di server perimetrali (perimetro esterno): Dual Stack** <br/> |**Pool di server perimetrali (perimetro esterno): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Pool di server perimetrali (perimetro interno): IPv4** <br/> |Sì  <br/> |Sì  <br/> |No  <br/> |
|**Pool di server perimetrali (perimetro interno): Dual Stack** <br/> |No  <br/> |Sì  <br/> |No  <br/> |
|**Pool di server perimetrali (perimetro interno): IPv6** <br/> |No  <br/> |No  <br/> |Sì\*  <br/> |
   
\* Utilizzare questa combinazione solo in un ambiente lab.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Supporto vocale aziendale avanzato per IPv6
<a name="Ent_V"> </a>

Le distribuzioni che includono il servizio Controllo di ammissione di chiamata, Enhanced 9-1-1 (E9-1-1) o il bypass multimediale devono essere configurate come implementazioni Solo IPv4 o Dual Stack. Gli endpoint che usano solo IPv6 non possono usare nessuna di queste funzionalità.
  
> [!NOTE]
> In una distribuzione a doppio stack, anche se un client Skype for Business Server si connette a un Skype for Business Server utilizzando IPv6, Skype for Business Server si impementerà nel mappare un indirizzo IPv4 appropriato per supportare E9-1-1. 
  
Il servizio informazioni percorso con indirizzi IPv6 non è supportato.
  
La messaggistica unificata di Exchange non supporta IPv6. Per la messaggistica unificata di Exchange, assicurasi che la risoluzione DNS non restituisca un indirizzo IPv6. L'utilizzo di IPv6 può causare errori quando le chiamate vengono inviate alla segreteria telefonica. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Altre Skype for Business Server funzionalità per IPv6
<a name="Ent_V"> </a>

Oltre alle funzionalità e ai componenti menzionati in precedenza, Skype for Business Server supporta IPv6 per le funzionalità seguenti:
  
- **Chat persistente**
    
    È possibile configurare IPv6 per Persistent Chat utilizzando Generatore di topologie. Per informazioni dettagliate sulla configurazione di Persistent Chat, vedere la documentazione relativa alla distribuzione del server Chat persistente.
    
- **Rapporti qualità percepita dagli utenti (QoE) e registrazione dettagli chiamata (CDR)**
    
    Le relazioni di monitoraggio includono l'indirizzo IP così com'è archiviato nel database di Monitoring Server, che sia di tipo IPv4 o IPv6.
    
## <a name="technical-requirements-for-ipv6"></a>Requisiti tecnici per IPv6
<a name="tech"> </a>

Se si prevede di configurare Skype for Business Server per IPv6, tenere presenti i requisiti seguenti:
  
- Per utilizzare gli indirizzi IPv6 con Skype for Business Server, è necessario creare record DNS (Domain Name System) per i record che devono essere individuati e risolti in un indirizzo IPv6. Il DNS IPv6 utilizza record AAAA (A quadrupla) dell'host. Se si utilizzano entrambi gli indirizzamenti IPv4 e IPv6 nella distribuzione, è consigliabile configurare e gestire sia i record A dell'host per IPv4 che i record AAAA dell'host per IPv6. Anche in caso di transizione completa della distribuzione a IPv6, è possibile che siano comunque necessari record dell'host DNS IPv4 per gli utenti esterni che continuano a utilizzare IPv4.
    
    È possibile distribuire record DNS IPv6 prima di iniziare a utilizzare IPv6. Se il client o il server non utilizza IPv6, il record non verrà utilizzato come riferimento. Le tecnologie transitorie sceglieranno quale record utilizzare in base alla configurazione e ai criteri della tecnologia.
    
- Ogni indirizzo IPv6 prevede un ambito. I tre ambiti che è possibile utilizzare per l'indirizzamento IPv6 sono gli indirizzi globali IPv6 (simili agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (simili agli intervalli di indirizzi IPv4 privati) e gli indirizzi IPv6 locali dei collegamenti (simili agli indirizzi IP privati automatici in Windows Server per IPv4). Tutti i server di un pool devono disporre di indirizzi IPv6 con lo stesso ambito. 
    
> [!IMPORTANT]
> IPv6 è un argomento complesso e richiede un'attenta pianificazione con il team di rete e il provider Internet per garantire che gli indirizzi assegnati a livello di Windows Server e a livello di Skype for Business Server funzionino come previsto. Vedere i collegamenti alla fine dell'argomento per risorse aggiuntive sull'indirizzamento IPv6 e la pianificazione. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Considerazioni sulla migrazione e la coesistenza per IPv6
<a name="migration"> </a>

IP versione 6 (IPv6) non è supportato in Lync Server 2010 o Office Communications Server. A scopo pilota, è possibile testare Lync Server 2010 e Skype for Business Server coesistenza dual stack. È consigliabile aggiornare tutti i pool per un determinato sito centrale a Skype for Business Server prima di abilitare IPv6 (rete dual stack) per uno qualsiasi dei pool. Se è necessario configurare un pool solo per IPv6, è consigliabile configurare un pool solo IPv6 nell'ambiente di prova a fini di test.
  
Durante la migrazione e in caso di coesistenza sono supportati gli scenari seguenti:
  
- Skype for Business Server, Lync Server 2013 e Lync Server 2010 in modalità IPv4, coesistono con Skype for Business Server in modalità dual stack.
    
- Skype for Business Server pool in modalità solo IPv6, se il pool solo IPv6 è in silo.
    
## <a name="see-also"></a>Vedere anche
<a name="migration"> </a>

[Configurare i tipi di indirizzi IP in Skype for Business](ip-address-types.md)

[Architettura di indirizzamento IP versione 6](https://tools.ietf.org/html/rfc4291)
  
[Formato indirizzo unicast globale IPv6](https://tools.ietf.org/html/rfc3587)
  
[Indirizzi unicast IPv6 locali univoci](https://tools.ietf.org/html/rfc4193)
