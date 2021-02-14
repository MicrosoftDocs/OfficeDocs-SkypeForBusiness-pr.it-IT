---
title: Pianificare la messaggistica istantanea e la presenza in Skype for Business Server
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
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Riepilogo: informazioni su come pianificare la messaggistica istantanea e la presenza in Skype for Business Server.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816276"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Pianificare la messaggistica istantanea e la presenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come pianificare la messaggistica istantanea e la presenza in Skype for Business Server.
  
Pianificare la messaggistica istantanea e la presenza in Skype for Business Server. Per informazioni sulle opzioni di distribuzione specifiche, ad esempio l'abilitazione o la disabilitazione della messaggistica istantanea offline, vedere Distribuire la messaggistica istantanea e la presenza [in Skype for Business Server.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Pianificare la messaggistica istantanea e la presenza in Skype for Business Server

I Front End Server forniscono funzionalità principali di Skype for Business Server, ad esempio la messaggistica istantanea e la presenza, e sono inclusi in ogni distribuzione di Skype for Business Server. Sono disponibili due edizioni: Skype for Business Server Enterprise Edition, progettato principalmente per organizzazioni di grandi dimensioni, e Skype for Business Server Standard Edition, progettato principalmente per le organizzazioni più piccole che desiderano un investimento hardware più piccolo e non richiedono opzioni di disponibilità elevata complete. Entrambe le edizioni supportano tutti i carichi di lavoro di Skype for Business Server, tra cui messaggistica istantanea, presenza, conferenze e VoIP aziendale.
  
La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale mediante i loro computer con messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. Un partecipante a una conversazione di messaggistica istantanea tra due parti può aggiungere un terzo partecipante in qualsiasi momento. In tal caso, la finestra relativa alla conversazione cambia in modo da supportare le funzionalità di conferenza.
  
La presenza fornisce agli utenti informazioni sullo stato di altri utenti della rete. Lo stato di presenza di un utente fornisce informazioni che consentono ad altri di decidere se tentare di contattare l'utente e se utilizzare la messaggistica istantanea, il telefono o la posta elettronica. La presenza induce a scegliere la comunicazione istantanea ma, segnalando anche se un utente è in riunione o fuori ufficio, consente di capire quando la comunicazione istantanea non può essere utilizzata. Questo stato di presenza viene visualizzato come icona di presenza in Skype for Business e in altre applicazioni in grado di riconoscere la presenza, tra cui il client di messaggistica e collaborazione di Microsoft Outlook, le tecnologie Microsoft SharePoint e Microsoft Office. L'icona di presenza rappresenta la disponibilità corrente dell'utente e la disponibilità a comunicare. 
  
### <a name="technical-requirements"></a>Requisiti tecnici

La messaggistica istantanea e la presenza vengono sempre eseguite nei pool Enterprise Edition Front End e nei server Standard Edition. Per informazioni su hardware, sistemi operativi e software di database supportati, vedere [Gateway](../../SfbPartnerCertification/certification/infra-gateways.md)certificati, Requisiti per l'ambiente [Skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)e Requisiti dell'infrastruttura per [Skype for Business Server 2019.](../../SfBServer2019/plan/system-requirements.md)
  
### <a name="enabling-communication-with-external-users"></a>Abilitazione delle comunicazioni con utenti esterni

È possibile aumentare notevolmente i vantaggi dell'investimento in Skype for Business Server consentendo agli utenti di comunicare con utenti esterni. Gli utenti esterni possono essere:
  
- Utenti remoti: gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e usano i laptop o altri dispositivi Skype for Business Server.
    
- Utenti federati: utenti di società con cui si lavora che eseguono anche Skype for Business Server. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società. 
    
- Utenti Skype: gli utenti di Skype for Business possono raggiungere le centinaia di milioni di utenti su Skype con messaggistica istantanea, voce e video.
    
> [!NOTE]
> AOL, Yahoo e Google Talk non sono più supportati. 
  
> [!NOTE]
> Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per consentire comunicazioni sicure tra la distribuzione di Skype for Business Server e gli utenti esterni. Gli utenti remoti dell'organizzazione e gli utenti delle organizzazioni federate saranno in grado di visualizzare la presenza reciproca e comunicare utilizzando la messaggistica istantanea. 
  
> [!NOTE]
> XMPP (Extensible Messaging and Presence Protocol) è supportato solo per gli scenari di certificazione JITC (Joint Interoperability Test Command) UCCP (Unified Capabilities Collaboration Platform). 
  
### <a name="archiving-im-content"></a>Archiviazione del contenuto di messaggistica istantanea

Skype for Business Server offre funzionalità che è possibile utilizzare se l'organizzazione deve rispettare le normative di conformità. È possibile utilizzare l'archiviazione per archiviare il contenuto dei messaggi istantanei per tutti gli utenti dell'organizzazione o solo per determinati utenti specificati. Per informazioni dettagliate, vedere [Pianificare l'archiviazione in Skype for Business Server.](archiving/archiving.md) 
  
Se è stato distribuito anche Microsoft Exchange Server 2013, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Skype for Business Server e utilizzare un singolo strumento per cercare entrambi i tipi di dati archiviati. Per ulteriori informazioni, vedere [Configurare Skype for Business Server per l'utilizzo Exchange Server archiviazione.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>Topologie e componenti

Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:
  
- Front End Server dell'organizzazione (noti come pool) o server Standard Edition. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server. Per ulteriori informazioni sulle topologie e sulla gestione dei pool Front End, vedere [Disponibilità elevata e gestione del pool Front End.](high-availability-and-disaster-recovery/high-availability.md)
    
- Un servizio di bilanciamento del carico, se si dispone di un pool Enterprise Edition Front End.
    
### <a name="supported-collocation"></a>Collocazione supportata

La collocazione è definita come disporre di un singolo server, o gruppo di server, in cui sono installati più ruoli. Per informazioni dettagliate sulla collocazione, vedere [Topology Basics for Skype for Business Server.](topology-basics/topology-basics.md) 
  

