---
title: Pianificare la topologia di conferenza per Skype for Business Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione della topologia di conferenza in Skype for Business Server.'
ms.openlocfilehash: 711db1309ce31838f02bd705252693a58992e2ee9a21e12931c8a9c5fe064d92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283108"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Pianificare la topologia di conferenza per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione della topologia di conferenza in Skype for Business Server.
  
In questo argomento vengono descritte le nozioni di base sulla topologia per le conferenze in Skype for Business Server:
  
- Topologie supportate
    
- Considerazioni sulle conferenze telefoniche con accesso esterno
    
- Considerazioni sulle conferenze Web
    
- Requisiti per riunioni di grandi dimensioni
    
Per ulteriori informazioni sui requisiti hardware e software, vedere Requisiti hardware e software per le conferenze [in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologie supportate

In Skype for Business Server, il server che esegue i servizi di conferenza è sempre collocato con i Front End Server o edizione Standard server. Quando si distribuisce Skype for Business Server, le funzionalità di conferenza di messaggistica istantanea vengono distribuite automaticamente. È possibile specificare se distribuire conferenze Web, audio e video (A/V) e con accesso esterno utilizzando Generatore di topologie. È inoltre possibile utilizzare Generatore di topologie per aggiungere conferenze a una distribuzione esistente. Per informazioni dettagliate sulle nozioni di base sulla topologia e sugli scenari di collocazione, vedere [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
È possibile distribuire le conferenze nelle topologie e nelle configurazioni seguenti:
  
- Skype for Business Server edizione Standard
    
- Skype for Business Server edizione Enterprise
    
- Con o senza VoIP aziendale
    
## <a name="dial-in-conferencing-considerations"></a>Considerazioni sulle conferenze telefoniche con accesso esterno

Se si distribuiscono conferenze telefoniche con accesso esterno, è necessario considerare quanto segue:
  
- Per le conferenze telefoniche con accesso esterno è necessario un Mediation Server per tradurre la segnalazione (e i supporti in alcune configurazioni) tra Skype for Business Server e il gateway PSTN e un gateway PSTN per tradurre la segnalazione e i supporti tra il Mediation Server e il gateway PSTN.
    
   Prima di configurare le conferenze telefoniche con accesso esterno, è necessario distribuire un VoIP aziendale o un Mediation Server e almeno una delle opzioni seguenti:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - SBC (Session Border Controller), per un provider di servizi di telefonia Internet a cui viene eseguita la connessione tramite la configurazione di un trunk SIP
    
- È possibile distribuire il servizio applicazione, applicazione Operatore conferenza e applicazione Annuncio conferenza in un sito centrale, ma non in un sito di succursale.
    
- È necessario distribuire le conferenze telefoniche con accesso esterno in ogni pool in cui si distribuiscono Skype for Business Server conferenza telefonica. Non è necessario assegnare numeri di accesso in ogni pool, ma è necessario distribuire la caratteristica di conferenza con accesso esterno in ogni pool. Questo requisito supporta la funzionalità dei nomi registrati quando un utente chiama un numero di accesso da un pool per partecipare a una Skype for Business Server conferenza in un pool diverso. 
    
Per ulteriori informazioni, vedere [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerazioni sulle conferenze Web

Le conferenze Web richiedono quanto segue: 
  
- Accesso all'archivio file utilizzato per l'archiviazione del contenuto delle conferenze Web.
    
- Integrazione con Office web apps server/Office Online Server, necessaria per condividere PowerPoint file durante una conferenza.
    
> [!NOTE]
> L'iterazione più recente Office Web Apps Server è denominata Office Online Server, supportata da Skype for Business Server. Per ulteriori dettagli, fare riferimento alla documentazione [Office Online Server .](/officeonlineserver/office-online-server) 
  
Skype for Business Server offre i modi seguenti per configurare Office server/Office Online Server Web Apps. A seconda delle esigenze, è possibile:
  
- **Installare sia Skype for Business Server che Office web apps server/Office Online Server locale dietro il firewall dell'organizzazione e nella stessa area di rete.** Con questa topologia, l'accesso esterno Office web apps server/Office Online Server verrà fornito tramite il server proxy inverso. Idealmente, è consigliabile installare Office web apps server/Office Online Server nella stessa area di rete di Skype for Business Server.
    
    I client Skype for Business esterni possono connettersi a Skype for Business Server e Office Web Apps Server/Office Online Server utilizzando un server proxy inverso, ovvero un server che accetta le richieste da Internet e le inoltra alla rete interna. I client interni non devono utilizzare il server proxy inverso perché possono connettersi direttamente Office server web apps/Office Online Server. Questa topologia è ideale se si desidera utilizzare una farm Office Web Apps Server/Office Online Server dedicata utilizzata solo da Skype for Business Server.
    
- **Usa un server web Office/Office Online Server distribuito esternamente.** In questa topologia, Skype for Business Server viene distribuito in locale e utilizza un server/Office Online Server web apps di Office distribuito all'esterno dell'area di rete Skype for Business Server. Ciò può verificarsi quando Office Web Apps Server/Office Online Server viene condiviso tra più applicazioni dell'azienda e viene distribuito in una rete che richiede a Skype for Business Server di utilizzare l'interfaccia esterna di Office Web Apps Server/Office Online Server e viceversa.
    
    Non è necessario installare un server proxy inverso. al contrario, tutte le richieste dal server web Office/Office Online Server a Skype for Business Server vengono instradati attraverso il server perimetrale. Sia i client interni che i Skype for Business esterni si connettono Office server Web Apps/Office Online Server utilizzando l'URL esterno.
    
    Se il server/Office Online Server di Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Il server Web Apps viene** distribuito in una rete esterna, ovvero perimetrale/Internet, in Generatore di topologie.
    
Per ulteriori informazioni, vedere [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Indipendentemente dalla topologia selezionata, è fondamentale aprire le porte del firewall corrette. È necessario assicurarsi che i nomi DNS, gli indirizzi IP e le porte non siano bloccati dai firewall nel server o nel Office Online Server di Office Web Apps, nel servizio di bilanciamento del carico o Skype for Business Server.
  
> [!NOTE]
> Un'altra opzione per fornire l'accesso esterno Office web apps server/Office Online Server è distribuire il server nella rete perimetrale. Se si sceglie di eseguire questa operazione, tenere presente che per l'installazione di Office Web Apps Server/Office Online Server è necessario che il computer server sia membro del dominio di Active Directory. A meno che i criteri di rete non consentano ai computer della rete perimetrale di essere membri di dominio di Active Directory, è consigliabile non installare Office Web Apps Server/Office Online Server nella rete perimetrale. È invece consigliabile installare Office web apps server/Office Online Server nella rete interna e fornire agli utenti esterni l'accesso tramite il server proxy inverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisiti di topologia per riunioni di grandi dimensioni

Una singola riunione di grandi dimensioni richiede almeno un Front End Server e un server back-end. Tuttavia, per garantire la disponibilità elevata, è consigliabile un pool di due Front End Server con server back-end con mirroring, come illustrato nel diagramma seguente:
  
**Topologia riunioni di grandi dimensioni**

![Topologia riunioni di grandi dimensioni](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
L'utente che ospita riunioni di grandi dimensioni deve disporre dell'account utente nel pool Front End. Non è tuttavia consigliabile ospitare altri account utente in questo pool. Usarlo invece solo per le riunioni di grandi dimensioni. È preferibile creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni. Poiché l'impostazione di riunione di grandi dimensioni è ottimizzata per le prestazioni, l'utilizzo come utente normale potrebbe avere problemi, ad esempio l'impossibilità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.
  
La gestione di un pool con esattamente due server Front End richiede alcune considerazioni speciali. Per ulteriori informazioni, vedere [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) e [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Inoltre, se si desidera fornire facoltativamente backup e failover di ripristino di emergenza per il pool utilizzato per riunioni di grandi dimensioni, è possibile associarlo a un pool dedicato impostato in modo simile in un data center diverso. Per informazioni dettagliate, vedere [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Note aggiuntive sulla topologia:
  
- È necessaria una condivisione file per l'archiviazione del contenuto delle riunioni e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione. La condivisione di file può essere dedicata al pool oppure corrispondere a quella usata da un altro pool nello stesso sito di distribuzione. Per informazioni dettagliate sulla configurazione della condivisione file, vedere [Create a file share in Skype for Business Server 2015.](../../deploy/install/create-a-file-share.md)
    
- È Office server/Office Online Server web apps per abilitare la funzionalità PowerPoint presentazione in riunioni di grandi dimensioni. Il server/Office Online Server web apps Office può essere dedicato al pool di riunioni di grandi dimensioni oppure può essere lo stesso server web apps di Office/Office Online Server utilizzato da altri pool nel sito in cui è distribuito il pool dedicato. Per ulteriori informazioni, vedere [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Il bilanciamento del carico dei Front End Server richiede il bilanciamento del carico hardware per il traffico HTTP (ad esempio, il download del contenuto delle riunioni). Per il traffico SIP è consigliato il bilanciamento del carico DNS. Per informazioni dettagliate, vedere [Requisiti di bilanciamento del carico per Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se si desidera utilizzare Monitoring Server per il pool di riunioni di grandi dimensioni dedicato, è consigliabile utilizzare Monitoring Server e il relativo database condivisi tra tutti i pool Front End Server della distribuzione di Skype for Business Server. Per ulteriori informazioni, vedere [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
