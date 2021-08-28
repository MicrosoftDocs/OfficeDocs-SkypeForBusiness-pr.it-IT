---
title: Servizi di dominio Active Directory per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Servizi di dominio Active Directory funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da base per la Skype for Business Server di sicurezza. Lo scopo di questa sezione è descrivere come Skype for Business Server servizi di dominio Active Directory per creare un ambiente attendibile per la messaggistica istantanea, le conferenze Web, i supporti e la voce. Per informazioni dettagliate sulla preparazione dell'ambiente per Servizi di dominio Active Directory, vedere Install Skype for Business Server nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo di Servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione per la versione del sistema operativo in uso.
ms.openlocfilehash: 4af4e4b4dd7a64dd133d36a55ca1c334a12fe97e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604655"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Servizi di dominio Active Directory per Skype for Business Server
 
Servizi di dominio Active Directory funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2. Servizi di dominio Active Directory funge anche da base per la Skype for Business Server di sicurezza. Lo scopo di questa sezione è descrivere come Skype for Business Server servizi di dominio Active Directory per creare un ambiente attendibile per la messaggistica istantanea, le conferenze Web, i supporti e la voce. Per informazioni dettagliate sulla preparazione dell'ambiente per Servizi di dominio Active Directory, vedere [Install Skype for Business Server](../../deploy/install/install.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sul ruolo di Servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione per la versione del sistema operativo in uso.
  
Skype for Business Server utilizza Servizi di dominio Active Directory per archiviare:
  
- Impostazioni globali necessarie per tutti i server Skype for Business Server in una foresta.
    
- Informazioni sul servizio che identificano i ruoli di tutti i server che eseguono Skype for Business Server in una foresta.
    
- Alcune impostazioni utente.
    
## <a name="active-directory-infrastructure"></a>Infrastruttura di Active Directory

I requisiti di infrastruttura per Active Directory includono i seguenti:
  
- Requisiti del sistema operativo per i controller di dominio
    
- Requisiti per il livello funzionale di foresta e dominio
    
- Requisiti di dominio per il catalogo globale
    
Per informazioni dettagliate, vedere [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Gruppi universali

Durante la preparazione della foresta, Skype for Business Server diversi gruppi universali all'interno di Servizi di dominio Active Directory che dispongono dell'autorizzazione per accedere e gestire le impostazioni e i servizi globali. Questi gruppi universali includono:
  
- **Gruppi amministrativi**. Questi gruppi definiscono i ruoli di amministratore fondamentali per una Skype for Business Server rete. Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai Skype for Business Server dell'infrastruttura.
    
- **Gruppi di servizi**. Questi gruppi sono account di servizio necessari per accedere a vari servizi forniti da Skype for Business Server.
    
- **Gruppi di infrastrutture**. Questi gruppi forniscono l'autorizzazione per accedere ad aree specifiche dell'Skype for Business Server aziendale. Fungono da componenti dei gruppi amministrativi ed è consigliabile non modificarli o aggiungervi direttamente utenti. Durante la preparazione della foresta, specifici gruppi di servizi e di amministrazione vengono aggiunti ai gruppi di infrastruttura appropriati.
    
Per informazioni dettagliate sui gruppi universali specifici creati durante la preparazione di Active Directory per Skype for Business Server, nonché sui gruppi di servizi e di amministrazione che vengono aggiunti ai gruppi di infrastruttura, vedere Changes made by forest preparation in Skype for Business Server nella documentazione relativa alla [distribuzione.](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)
  
> [!NOTE]
> Skype for Business Server supporta i gruppi universali nel Windows Server 2012, nonché i sistemi operativi Windows Server 2003 per i controller di dominio. Ai membri dei gruppi universali, che possono includere altri gruppi e account di qualsiasi dominio della foresta o dell'albero di dominio, è possibile assegnare autorizzazioni in qualsiasi dominio della foresta o dell'albero di dominio. Il supporto dei gruppi universali, combinato con la delega dell'amministratore, semplifica la gestione di una Skype for Business Server distribuzione. Non è più necessario, ad esempio, aggiungere un dominio a un altro per consentire a un amministratore di gestirli entrambi. 
  
## <a name="role-based-access-control"></a>Controllo di accesso basato sui ruoli

Oltre a creare gruppi di amministrazione e servizi universali e aggiungere gruppi di servizi e di amministrazione ai gruppi universali appropriati, la preparazione della foresta crea anche Role-Based gruppi di controllo di accesso (RBAC). Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione. Per ulteriori informazioni sui gruppi RBAC, vedere [Role-based access control (RBAC) for Skype for Business Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Voci di controllo di accesso ed ereditarietà

Il processo di preparazione della foresta prevede la creazione sia di voci di controllo di accesso pubbliche che private e l'aggiunta delle voci di controllo di accesso per i gruppi universali creati. Vengono create voci di controllo di accesso private specifiche nel contenitore delle impostazioni globali utilizzato Skype for Business Server. Questo contenitore viene utilizzato solo da Skype for Business Server e si trova nel contenitore Configurazione o nel contenitore Sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali.
  
Questa operazione comporta l'aggiunta delle voci di controllo di accesso necessarie ai gruppi universali che concedono autorizzazioni per ospitare e gestire gli utenti nell'ambito del dominio. Con la preparazione del dominio vengono create voci di controllo di accesso nella radice del dominio e tre contenitori predefiniti per utenti, computer e controller di dominio.
  
Per informazioni dettagliate sulle voci di controllo di accesso pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) e Changes made by domain preparation in Skype for Business Server nella documentazione relativa alla [distribuzione.](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md)
  
Le organizzazioni scelgono spesso di bloccare Servizi di dominio Active Directory per ridurre i rischi per la sicurezza. Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni Skype for Business Server necessarie. Ciò può includere la rimozione delle voci di controllo di accesso dai contenitori e dalle unità organizzative, nonché la disabilitazione dell'ereditarietà delle autorizzazioni negli oggetti User, Contact, InetOrgPerson o Computer. In un ambiente Active Directory bloccato, le autorizzazioni devono essere impostate manualmente nei contenitori e nelle unità organizzative per cui sono necessarie.
  
## <a name="server-information"></a>Informazioni sui server

Durante l'Skype for Business Server le informazioni sul server vengono pubblicate nei tre percorsi seguenti in Servizi di dominio Active Directory:
  
- Un punto di connessione del servizio (SCP) in ogni oggetto computer Active Directory corrispondente a un computer fisico in cui Skype for Business Server è installato.
    
- Oggetti server creati nel contenitore della classe **msRTCSIP-Pools**.
    
- Server attendibili specificati in Generatore di topologie.
    
## <a name="service-connection-points"></a>Punti di connessione del servizio

Ogni Skype for Business Server in Servizi di dominio Active Directory dispone di un SCP denominato RTC Services, che a sua volta contiene una serie di attributi che identificano ogni computer e specificano i servizi che fornisce. Tra gli attributi SCP più importanti ci sono *serviceDNSName,* *serviceDNSNameType,* *serviceClassname* e *serviceBindingInformation.* Le applicazioni di terze parti per la gestione delle risorse possono recuperare le informazioni sui server in una distribuzione eseguendo una query a fronte di questi e altri attributi SCP.
  
## <a name="active-directory-server-objects"></a>Oggetti server Active Directory

Ogni Skype for Business Server server dispone di un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo. Inoltre, quando viene attivato un server edizione Standard o quando viene creato un pool di edizione Enterprise, Skype for Business Server crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-Pools.** La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool. Un server Standard Edition viene considerato un pool logico i cui componenti front-end e back-end sono collocati in un solo computer.
  
## <a name="trusted-servers"></a>Server trusted

In Skype for Business Server, i server attendibili sono quelli specificati quando si esegue Generatore di topologie e si pubblica la topologia. La topologia pubblicata, incluse tutte le informazioni del server, viene archiviata nell'archivio di gestione centrale. Solo i server definiti nell'archivio di gestione centrale sono trusted. In Skype for Business Server, un server attendibile è uno che soddisfa i criteri seguenti:
  
- Il nome FQDN del server compare nella topologia archiviata nell'archivio di gestione centrale.
    
- Il server presenta un certificato valido da un'autorità di certificazione attendibile. Per informazioni dettagliate, vedere [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o System requirements for Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
    
Se uno di questi criteri non risulta soddisfatto, il server non è trusted e la connessione viene rifiutata. Questo doppio requisito impedisce un possibile attacco, se improbabile, in cui un server non autorizzato tenta di assumere il nome di dominio completo di un server valido.
  
Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server Skype for Business Server, Skype for Business Server crea contenitori durante la preparazione della foresta per l'archiviazione di elenchi di server attendibili per le versioni precedenti. Nella tabella seguente vengono descritti i contenitori creati per abilitare la compatibilità con le distribuzioni precedenti.
  
**Elenchi di server trusted e contenitori Active Directory corrispondenti per la compatibilità con le versioni precedenti**

|**Elenco di server trusted**|**Contenitore di Active Directory**|
|:-----|:-----|
|Server Standard Edtion e Front End Server del pool Enterprise  <br/> |RTC Service/Global Settings  <br/> |
|Conferencing Server  <br/> |RTC Service/Trusted MCUs  <br/> |
|Web Components Server  <br/> |RTC Service/TrustedWebComponentsServers  <br/> |
|Mediation Server e Communicator Web Access Server, server applicazioni, funzione di registrazione con QoE, servizio A/V Conferencing (anche server SIP di terze parti)  <br/> |RTC Service/Trusted Services  <br/> |
|Server proxy  <br/> |Skype for Business Server non supporta la compatibilità con le versioni precedenti per i server proxy  <br/> |
   

## <a name="see-also"></a>Vedere anche

[Preparare Active Directory per Skype for Business Server](../../deploy/install/prepare-active-directory.md)
