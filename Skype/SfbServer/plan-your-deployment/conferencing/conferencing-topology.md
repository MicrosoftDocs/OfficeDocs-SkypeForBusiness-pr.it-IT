---
title: Pianificare la topologia di conferenza per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione della topologia di conferenza in Skype for Business Server.'
ms.openlocfilehash: 39067403513173e3fe26c5767042c62f549e0a7c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187856"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Pianificare la topologia di conferenza per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione della topologia di conferenza in Skype for Business Server.
  
Questo argomento descrive le nozioni fondamentali sulla topologia per le conferenze in Skype for Business Server:
  
- Topologie supportate
    
- Considerazioni sui servizi di conferenza telefonica con accesso esterno
    
- Considerazioni su Web Conferencing
    
- Requisiti per riunioni di grandi dimensioni
    
Per altre informazioni sui requisiti hardware e software, vedere [requisiti hardware e software per i servizi di conferenza in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologie supportate

In Skype for Business Server, il server che gestisce i servizi di conferenza è sempre collocato con i server front-end o i server Standard Edition. Quando si distribuisce Skype for Business Server, le funzionalità di conferenza di messaggistica istantanea vengono distribuite automaticamente. Puoi specificare se distribuire web, audio e video (A/V) e servizi di conferenza telefonica con accesso esterno usando il generatore di topologie. È anche possibile usare generatore di topologie per aggiungere servizi di conferenza a una distribuzione esistente. Per informazioni dettagliate sulle nozioni fondamentali sulla topologia e sulla collocazione, vedere [nozioni fondamentali sulla topologia di Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
È possibile distribuire le conferenze nelle topologie e nelle configurazioni seguenti:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Con o senza VoIP aziendale
    
## <a name="dial-in-conferencing-considerations"></a>Considerazioni sui servizi di conferenza telefonica con accesso esterno

Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario tenere presente quanto segue:
  
- I servizi di conferenza telefonica con accesso esterno richiedono un Mediation Server per tradurre i segnali (e gli elementi multimediali in alcune configurazioni) tra Skype for Business Server e il gateway PSTN e un gateway PSTN per tradurre segnali e elementi multimediali tra il Mediation Server e il gateway PSTN .
    
   Prima di poter configurare i servizi di conferenza telefonica con accesso esterno, è necessario distribuire VoIP aziendale o Mediation Server e almeno una delle opzioni seguenti:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Session Border Controller (SBC) (per un provider di servizi di telefonia Internet a cui ci si connette configurando un trunk SIP)
    
- È possibile distribuire il servizio applicazione, l'applicazione per i servizi di conferenza e l'applicazione di annunci di conferenza in un sito centrale, ma non in un sito di succursale.
    
- È necessario distribuire i servizi di conferenza telefonica con accesso esterno in tutti i pool in cui si distribuiscono le conferenze di Skype for Business Server. Non è necessario assegnare numeri di accesso in tutti i pool, ma è necessario distribuire la funzionalità di conferenza telefonica tramite accesso esterno in tutti i pool. Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Skype for Business Server in un pool diverso. 
    
Per altre informazioni, vedere [pianificare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerazioni su Web Conferencing

Le conferenze Web richiedono le seguenti operazioni: 
  
- Accedere all'archivio file, che viene usato per archiviare il contenuto delle conferenze Web.
    
- Integrazione con Office Web Apps Server/Office Online Server, che è necessario per condividere i file di PowerPoint durante una conferenza.
    
> [!NOTE]
> L'iterazione più recente di Office Web Apps Server è denominata Office Online Server, supportata da Skype for Business Server. Per altre informazioni, vedere la [documentazione del server Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype for Business Server offre i modi seguenti per configurare Office Web Apps Server/Office Online Server. A seconda delle proprie esigenze, è possibile:
  
- **Installare sia Skype for Business Server che Office Web Apps Server/Office Online Server in locale dietro il firewall dell'organizzazione e nella stessa area di rete.** Con questa topologia, l'accesso esterno a Office Web Apps Server/Office Online Server verrà fornito tramite il server proxy inverso. In teoria, è consigliabile installare Office Web Apps Server/Office Online Server nella stessa area di rete di Skype for Business Server.
    
    I client Skype for business esterni possono connettersi a Skype for Business Server e a Office Web Apps Server/Office Online server usando un server proxy inverso, un server che accetta richieste da Internet e le inoltra alla rete interna. I client interni non devono usare il server proxy inverso perché possono connettersi direttamente a Office Web Apps Server/Office Online Server. Questa topologia funziona meglio se si vuole usare un server Office Web Apps dedicato/server farm di Office Online che viene usato solo da Skype for Business Server.
    
- **Usare un server Office Web Apps distribuito esternamente o un server Office Online.** In questa topologia, Skype for Business Server viene distribuito in locale e usa un server di Office Web Apps/un server Office Online distribuito all'esterno dell'area di rete di Skype for Business Server. Questo problema può verificarsi quando Office Web Apps Server/Office Online Server è condiviso tra più applicazioni della società ed è distribuito in una rete che richiede a Skype for Business Server di usare l'interfaccia esterna di Office Web Apps Server/Office Online Server e viceversa.
    
    Non è necessario installare un server proxy inverso; tutte le richieste di Office Web Apps Server/Office Online Server a Skype for Business Server vengono invece instradate tramite il server perimetrale. I client Skype for business interni e quelli esterni si connettono a Office Web Apps Server/Office Online server usando l'URL esterno.
    
    Se il server Office Web Apps Server/Office Online viene distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna** (ovvero perimetro/Internet) in Generatore di topologie.
    
Per altre informazioni, vedere [configurare l'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Indipendentemente dalla topologia selezionata, è fondamentale che vengano aperte le porte del firewall corrette. È necessario assicurarsi che i nomi DNS, gli indirizzi IP e le porte non vengano bloccati dai firewall nel server Office Web Apps/Server Office Online, nel servizio di bilanciamento del carico o in Skype for Business Server.
  
> [!NOTE]
> Un'altra opzione per fornire l'accesso esterno a Office Web Apps Server/Office Online Server consiste nel distribuire il server nella rete perimetrale. Se si sceglie di eseguire questa operazione, ricordare che Office Web Apps Server/Office Online Server Setup richiede che il computer server sia membro del dominio Active Directory. A meno che i criteri di rete non consentano ai computer della rete perimetrale di essere membri del dominio Active Directory, è consigliabile non installare Office Web Apps Server/Office Online Server nella rete perimetrale. È invece necessario installare Office Web Apps Server/Office Online Server nella rete interna e consentire l'accesso degli utenti esterni tramite il server proxy inverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisiti di topologia per riunioni di grandi dimensioni

Una singola riunione di grandi dimensioni richiede almeno un server front-end e un server back-end. Tuttavia, per ottenere una disponibilità elevata, è consigliabile un pool di due front end server con server back-end con mirroring, come illustrato nel diagramma seguente:
  
**Topologia di riunione di grandi dimensioni**

![Topologia di riunione di grandi dimensioni](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
L'utente che ospita le riunioni di grandi dimensioni deve avere il proprio account utente ospitato nel pool Front-end. Tuttavia, non è consigliabile ospitare altri account utente in questo pool. Usalo invece solo per le riunioni di grandi dimensioni. La procedura consigliata consiste nel creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni. Dato che l'impostazione di grande riunione è ottimizzata per le prestazioni, l'uso di un utente normale può avere problemi come l'incapacità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.
  
La gestione di un pool con esattamente due server front-end richiede alcune considerazioni particolari. Per altre informazioni, vedere [nozioni di base sulla topologia per Skype for Business server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) e [topologie di riferimento per Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Inoltre, se si vuole specificare facoltativamente il backup e il failover del ripristino di emergenza per il pool usato per riunioni di grandi dimensioni, è possibile associarlo a un pool di dati in un altro Data Center. Per informazioni dettagliate, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Altre note sulla topologia includono:
  
- È necessaria una condivisione file per archiviare il contenuto della riunione e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione. La condivisione file può essere dedicata al pool o può essere la stessa condivisione di file usata da un altro pool nel sito in cui è distribuito il pool. Per informazioni dettagliate sulla configurazione della condivisione file, vedere [creare una condivisione file in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- È necessario un server Office Web Apps/Server Office Online per abilitare la funzionalità presentazione di PowerPoint in riunioni di grandi dimensioni. Il server Office Web Apps Server/Office Online può essere dedicato al grande pool di riunioni oppure può essere lo stesso server Office Web Apps/Server Office Online usato da altri pool nel sito in cui è distribuito il pool dedicato. Per altre informazioni, vedere [configurare l'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Il bilanciamento del carico dei server front-end richiede il bilanciamento del carico hardware per il traffico HTTP, ad esempio il download del contenuto della riunione. Il bilanciamento del carico DNS è consigliato per il traffico SIP. Per informazioni dettagliate, vedere [requisiti di bilanciamento del carico per Skype for business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se si vuole usare il server di monitoraggio per il pool di grandi riunioni dedicato, è consigliabile usare il server di monitoraggio e il relativo database condivisi in tutti i pool del server front-end nella distribuzione di Skype for Business Server. Per altre informazioni, Vedi [pianificare il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

