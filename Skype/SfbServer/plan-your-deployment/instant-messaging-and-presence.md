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
  
Pianificare la messaggistica istantanea e la presenza in Skype for Business Server. Per informazioni sulle opzioni di distribuzione specifiche, ad esempio l'abilitazione o la disabilitazione della messaggistica istantanea offline, vedere [distribuire la messaggistica istantanea e la presenza in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Pianificare la messaggistica istantanea e la presenza in Skype for Business Server

I Front End Server offrono funzionalità di base di Skype for Business Server quali messaggistica istantanea e presenza e sono incluse in ogni distribuzione di Skype for Business Server. Sono disponibili due edizioni: Skype for Business Server Enterprise Edition, che è stato creato principalmente per organizzazioni di grandi dimensioni, e Skype for Business Server Standard Edition, che è stato creato principalmente per organizzazioni di piccole dimensioni che desiderano un investimento hardware inferiore e che non richiedono opzioni di disponibilità elevata complete. Entrambe le edizioni supportano tutti i carichi di lavoro di Skype for Business Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.
  
La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale mediante i loro computer con messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. Un partecipante a una conversazione di messaggistica istantanea tra due parti può aggiungere un terzo partecipante in qualsiasi momento. In tal caso, la finestra relativa alla conversazione cambia in modo da supportare le funzionalità di conferenza.
  
La presenza fornisce informazioni agli utenti sullo stato di altre persone sulla rete. Lo stato di presenza di un utente fornisce informazioni utili per consentire ad altri utenti di decidere se provare a contattare l'utente e se utilizzare la messaggistica istantanea, il telefono o la posta elettronica. La presenza induce a scegliere la comunicazione istantanea ma, segnalando anche se un utente è in riunione o fuori ufficio, consente di capire quando la comunicazione istantanea non può essere utilizzata. Questo stato di presenza viene visualizzato come icona presenza in Skype for business e in altre applicazioni in grado di riconoscere la presenza, tra cui il client di messaggistica e collaborazione di Microsoft Outlook, Microsoft SharePoint Technologies e Microsoft Office. L'icona presenza rappresenta la disponibilità corrente e la disponibilità dell'utente per la comunicazione. 
  
### <a name="technical-requirements"></a>Requisiti tecnici

La messaggistica istantanea e la presenza vengono sempre eseguite su pool Enterprise Edition front end e server Standard Edition. Per informazioni sull'hardware, i sistemi operativi e il software di database supportati, vedere  [Certified Gateways](../../SfbPartnerCertification/certification/infra-gateways.md),  [requirements for your skype for business 2015 Environment](requirements-for-your-environment/requirements-for-your-environment.md)e [Infrastructure requirements for Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Abilitazione delle comunicazioni con gli utenti esterni

È possibile aumentare notevolmente i vantaggi dell'investimento in Skype for Business Server, consentendo agli utenti di comunicare con gli utenti esterni. Gli utenti esterni possono essere:
  
- Utenti remoti: gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e utilizzano i propri laptop o altri dispositivi Skype for Business Server.
    
- Utenti federati: utenti provenienti da società con cui si lavora, che eseguono anche Skype for Business Server. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società. 
    
- Utenti Skype: gli utenti di Skype for business possono raggiungere centinaia di milioni di utenti su Skype con messaggistica istantanea, vocale e video.
    
> [!NOTE]
> AOL, Yahoo e Google Talk non sono più supportati. 
  
> [!NOTE]
> Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per consentire le comunicazioni sicure tra la distribuzione di Skype for Business Server e gli utenti esterni. Gli utenti remoti e le organizzazioni remote dell'organizzazione saranno in grado di visualizzare gli altri utenti e comunicare tramite messaggistica istantanea. 
  
> [!NOTE]
> Il protocollo XMPP (Extensible Messaging and Presence Protocol) è supportato solo per gli scenari di certificazione JITC (Unified capabilities Collaboration Platform) (UCCP). 
  
### <a name="archiving-im-content"></a>Contenuto di messaggistica istantanea di archiviazione

Skype for Business Server fornisce caratteristiche che è possibile utilizzare se l'organizzazione deve rispettare le normative di conformità. È possibile utilizzare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per alcuni utenti specificati. Per ulteriori informazioni, vedere [Plan for archiving in Skype for Business Server](archiving/archiving.md). 
  
Se si dispone anche di Microsoft Exchange Server 2013 distribuito, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Skype for Business Server e utilizzare un unico strumento per eseguire la ricerca di entrambi i tipi di dati archiviati. Per ulteriori informazioni, vedere [Configurare Skype for Business Server per l'utilizzo dell'archiviazione di Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologie e componenti

Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:
  
- I front end server dell'organizzazione (noti come pool) o un server Standard Edition. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server. Per ulteriori informazioni sulle topologie e sulla gestione del pool Front End, vedere [disponibilità elevata e gestione del pool Front End](high-availability-and-disaster-recovery/high-availability.md).
    
- Un bilanciamento del carico, se si dispone di un pool Enterprise Edition front end.
    
### <a name="supported-collocation"></a>Collocazione supportata

La collocazione è definita come avente un singolo server o gruppo di server, con più ruoli installati. Per informazioni dettagliate sulla collocazione, vedere [nozioni di base sulla topologia per Skype for Business Server](topology-basics/topology-basics.md). 
  

