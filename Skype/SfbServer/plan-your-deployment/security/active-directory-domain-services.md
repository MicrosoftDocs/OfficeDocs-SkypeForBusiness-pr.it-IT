---
title: Servizi di dominio Active Directory per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Active Directory Domain Services funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da fondamento in cui è stata creata l'infrastruttura di sicurezza di Skype for Business Server. Lo scopo di questa sezione è descrivere in che modo Skype for Business Server usa i servizi di dominio Active Directory per creare un ambiente affidabile per la messaggistica istantanea, le conferenze Web, i contenuti multimediali e la voce. Per informazioni dettagliate sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere Installare Skype for Business Server nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo dei servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione relativa alla versione del sistema operativo in uso.
ms.openlocfilehash: 4458d49bf2f57284ac29c68bb40f3979761d5c50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194901"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Servizi di dominio Active Directory per Skype for Business Server
 
Active Directory Domain Services funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da fondamento in cui è stata creata l'infrastruttura di sicurezza di Skype for Business Server. Lo scopo di questa sezione è descrivere in che modo Skype for Business Server usa i servizi di dominio Active Directory per creare un ambiente affidabile per la messaggistica istantanea, le conferenze Web, i contenuti multimediali e la voce. Per informazioni dettagliate sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere [installare Skype for Business Server](../../deploy/install/install.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo dei servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione relativa alla versione del sistema operativo in uso.
  
Skype for Business Server usa i servizi di dominio Active Directory per archiviare:
  
- Impostazioni globali che richiedono tutti i server in cui è in uso Skype for Business Server in una foresta.
    
- Informazioni sul servizio che identificano i ruoli di tutti i server che utilizzano Skype for Business Server in una foresta.
    
- Alcune impostazioni utente.
    
## <a name="active-directory-infrastructure"></a>Infrastruttura di Active Directory

I requisiti di infrastruttura per Active Directory includono i seguenti:
  
- Requisiti del sistema operativo per i controller di dominio
    
- Requisiti del livello di funzionalità Domain e Forest
    
- Requisiti del dominio catalogo globale
    
Per informazioni dettagliate, vedere [requisiti ambientali per i requisiti di Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Gruppi universali

Durante la preparazione della foresta, Skype for Business Server crea diversi gruppi universali all'interno di servizi di dominio Active Directory con l'autorizzazione per accedere e gestire le impostazioni e i servizi globali. Questi gruppi universali includono:
  
- **Gruppi amministrativi**. Questi gruppi definiscono i ruoli di amministratore fondamentali per una rete di Skype for Business Server. Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai gruppi di infrastruttura di Skype for Business Server.
    
- **Gruppi di servizi**. Questi gruppi sono account di servizio necessari per accedere a vari servizi forniti da Skype for Business Server.
    
- **Gruppi di infrastrutture**. Questi gruppi conferiscono l'autorizzazione per accedere ad aree specifiche dell'infrastruttura di Skype for Business Server. Funzionano come componenti di gruppi amministrativi e non devono essere modificati o aggiunti direttamente agli utenti. Durante la preparazione della foresta, i gruppi di servizi e di amministrazione specifici vengono aggiunti ai gruppi di infrastruttura appropriati.
    
Per informazioni dettagliate sui gruppi universali specifici creati durante la preparazione di annunci per Skype for Business Server, nonché i gruppi di servizi e di amministrazione aggiunti ai gruppi di infrastrutture, vedere [modifiche apportate dalla preparazione della foresta in Skype for business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.
  
> [!NOTE]
> Skype for Business Server supporta i gruppi universali in Windows Server 2012, nonché i sistemi operativi Windows Server 2003 per i controller di dominio. I membri dei gruppi universali possono includere altri gruppi e account da qualsiasi dominio nell'albero di dominio o nella foresta e possono essere assegnate autorizzazioni in qualsiasi dominio nell'albero o nella foresta del dominio. Il supporto del gruppo universale, combinato con la delega dell'amministratore, semplifica la gestione di una distribuzione di Skype for Business Server. Ad esempio, non è necessario aggiungere un dominio a un altro per consentire a un amministratore di gestire entrambe le proprie esigenze. 
  
## <a name="role-based-access-control"></a>Controllo dell'accesso basato sui ruoli

Oltre a creare gruppi di servizi e di amministrazione universali e ad aggiungere gruppi di servizi e di amministrazione ai gruppi universali appropriati, la preparazione della foresta crea anche gruppi di controllo di accesso basati sui ruoli. Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione. Per altre informazioni sui gruppi RBAC, vedere [controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Voci di controllo di accesso (ACE) ed ereditarietà

La preparazione della foresta crea sia gli assi privati che quelli pubblici e, aggiungendo le voci ACE per i gruppi universali creati. Crea specifiche Ace private nel contenitore di impostazioni globali usato da Skype for Business Server. Questo contenitore viene usato solo da Skype for Business Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui si archiviano le impostazioni globali.
  
Il passaggio preparazione del dominio aggiunge le voci di controllo di accesso (ACE) necessarie ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio. La preparazione del dominio crea ACE nella radice del dominio e tre contenitori predefiniti: User, computer e Domain controller.
  
Per informazioni dettagliate sulle ACE pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [modifiche apportate dalla preparazione della foresta in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) e [modifiche apportate dalla preparazione del dominio in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) nella pagina Documentazione di distribuzione.
  
Le organizzazioni spesso bloccano i servizi di dominio Active Directory (AD DS) per ridurre i rischi per la sicurezza. Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni richieste da Skype for Business Server. Questa operazione può includere la rimozione di Ace da contenitori e unità organizzative e la disabilitazione dell'ereditarietà delle autorizzazioni per gli oggetti utente, contatto, InetOrgPerson o computer. In un ambiente Active Directory bloccato è necessario impostare manualmente le autorizzazioni sui contenitori e le UO che le richiedono.
  
## <a name="server-information"></a>Informazioni sul server

Durante l'attivazione, Skype for Business Server pubblica le informazioni sul server nei tre percorsi seguenti in servizi di dominio Active Directory:
  
- Un punto di connessione del servizio (SCP) in ogni oggetto computer di Active Directory corrispondente a un computer fisico in cui è installato Skype for Business Server.
    
- Oggetti server creati nel contenitore della classe **msRTCSIP-Pools** .
    
- Server attendibili specificati in Generatore di topologia.
    
## <a name="service-connection-points"></a>Punti di connessione del servizio

Ogni oggetto di Skype for Business Server in servizi di dominio Active Directory ha un SCP chiamato RTC Services, che a sua volta contiene un numero di attributi che identificano ogni computer e specificano i servizi forniti. Tra gli attributi SCP più importanti ci sono *serviceDNSName* , *serviceDNSNameType* , *serviceClassName* e *serviceBindingInformation* . Le applicazioni di Asset Management di terze parti possono recuperare le informazioni sul server in una distribuzione eseguendo una query su questi e altri attributi SCP.
  
## <a name="active-directory-server-objects"></a>Oggetti server di Active Directory

Ogni ruolo del server di Skype for Business Server include un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo. Inoltre, quando viene attivato un server Standard Edition o quando viene creato un pool di Enterprise Edition, Skype for Business Server crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-** pools. La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool. Un server Standard Edition viene considerato come un pool logico di cui le estremità anteriore e posteriore sono collocate in un singolo computer.
  
## <a name="trusted-servers"></a>Server attendibili

In Skype for Business Server i server attendibili sono quelli specificati quando si esegue Generatore di topologie e si pubblica la topologia. La topologia pubblicata, incluse tutte le informazioni sul server, è archiviata in Central Management store. Solo i server definiti nell'Central Management store sono attendibili. In Skype for Business Server un server attendibile è quello che soddisfa i criteri seguenti:
  
- Il nome di dominio completo del server si trova nella topologia archiviata in Central Management store.
    
- Il server presenta un certificato valido da una CA attendibile. Per informazioni dettagliate, vedere [requisiti ambientali per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisiti di sistema per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Se uno di questi criteri non è presente, il server non è attendibile e la connessione viene rifiutata. Questo doppio requisito impedisce un attacco possibile, se improbabile, in cui un server Rogue tenti di assumere il nome di dominio completo del server valido.
  
Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server Skype for Business Server, Skype for Business Server crea contenitori durante la preparazione della foresta per contenere elenchi di server attendibili per le versioni precedenti. La tabella seguente descrive i contenitori creati per consentire la compatibilità con le distribuzioni precedenti.
  
**Elenchi di server attendibili e relativi contenitori di Active Directory per la compatibilità con le versioni precedenti**

|**Elenco di server attendibili**|**Contenitore di Active Directory**|
|:-----|:-----|
|Server Standard Edition e server front-end del pool Enterprise  <br/> |RTC Service/impostazioni globali  <br/> |
|Server di conferenza  <br/> |RTC Service/trusted MCU  <br/> |
|Server Web Components  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Mediation Server e server Communicator Web Access, server applicazioni, registrar con QoE, servizio di conferenza A/V (anche server SIP di terze parti)  <br/> |Servizio RTC/servizi attendibili  <br/> |
|Server proxy  <br/> |Skype for Business Server non supporta la compatibilità con le versioni precedenti per i server proxy  <br/> |
   

## <a name="see-also"></a>Vedere anche

[Preparare Active Directory per Skype for Business Server](../../deploy/install/prepare-active-directory.md)
