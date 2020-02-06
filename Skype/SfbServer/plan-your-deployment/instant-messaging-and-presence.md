---
title: Pianificare la messaggistica istantanea e la presenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Riepilogo: informazioni su come pianificare la messaggistica istantanea e la presenza in Skype for Business Server.'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815904"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Pianificare la messaggistica istantanea e la presenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come pianificare la messaggistica istantanea e la presenza in Skype for Business Server.
  
Pianificare la messaggistica istantanea e la presenza in Skype for Business Server. Per informazioni sulle opzioni di distribuzione specifiche, ad esempio l'abilitazione o la disabilitazione della messaggistica istantanea offline, vedere [distribuire la messaggistica istantanea e la presenza in Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Pianificare la messaggistica istantanea e la presenza in Skype for Business Server

I server front-end supportano le funzionalità di Skype for Business Server principali, come la messaggistica istantanea e la presenza e sono inclusi in ogni distribuzione di Skype for Business Server. Sono disponibili due edizioni: Skype for Business Server Enterprise Edition, progettato principalmente per le organizzazioni di grandi dimensioni, e Skype for Business Server Standard Edition, progettato principalmente per le organizzazioni più piccole che vogliono un numero più piccolo investimenti hardware e non richiedono opzioni di disponibilità elevate complete. Entrambe le edizioni supportano tutti i carichi di lavoro di Skype for Business Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.
  
La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo. Sono supportate entrambe le sessioni di messaggistica istantanea a due parti e a più parti. Un partecipante a una conversazione di messaggistica istantanea a due parti può aggiungere un terzo partecipante alla conversazione in qualsiasi momento. In questo caso, la finestra di conversazione viene modificata per supportare le funzionalità di conferenza.
  
La presenza fornisce informazioni agli utenti sullo stato degli altri nella rete. Lo stato presenza di un utente fornisce informazioni utili per consentire agli altri utenti di decidere se provare a contattare l'utente e se usare la messaggistica istantanea, il telefono o l'indirizzo di posta elettronica. La presenza incoraggia le comunicazioni istantanee quando possibile, ma fornisce anche informazioni sul fatto che un utente si trovi in una riunione o fuori sede, indicando che la comunicazione immediata non è possibile. Questo stato presenza viene visualizzato come icona presenza in Skype for business e in altre applicazioni che supportano la presenza, tra cui il client di messaggistica e collaborazione di Microsoft Outlook, le tecnologie Microsoft SharePoint e Microsoft Office. L'icona presenza rappresenta la disponibilità corrente dell'utente e la disponibilità a comunicare. 
  
### <a name="technical-requirements"></a>Requisiti tecnici

La messaggistica istantanea (IM) e la presenza vengono sempre eseguite nei pool Front end Enterprise Edition e nei server Standard Edition. Per informazioni su hardware, sistemi operativi e software di database supportati, vedere [gateway certificati](../../SfbPartnerCertification/certification/infra-gateways.md), [requisiti per l'ambiente skype for business 2015](requirements-for-your-environment/requirements-for-your-environment.md)e requisiti di [infrastruttura per Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Abilitazione delle comunicazioni con utenti esterni

È possibile aumentare notevolmente i vantaggi offerti dall'investimento in Skype for Business Server consentendo agli utenti di comunicare con utenti esterni. Gli utenti esterni possono includere:
  
- Utenti remoti: gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e usano i loro portatili o altri dispositivi Skype for Business Server.
    
- Utenti federati: utenti di aziende con cui si lavora e che eseguono anche Skype for Business Server. Per consentire agli utenti di contattare facilmente questi utenti, è possibile creare relazioni federate con queste società. 
    
- Utenti Skype: gli utenti di Skype for business possono raggiungere le centinaia di milioni di utenti in Skype con messaggistica istantanea, audio e video.
    
> [!NOTE]
> AOL, Yahoo e Google Talk non sono più supportate. 
  
> [!NOTE]
> Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per facilitare le comunicazioni sicure tra la distribuzione di Skype for Business Server e gli utenti esterni. Gli utenti e gli utenti remoti dell'organizzazione presso le organizzazioni federate potranno vedere la presenza e comunicare tramite messaggistica istantanea. 
  
> [!NOTE]
> Il protocollo XMPP (Extensible Messaging and Presence Protocol) è supportato solo per gli scenari di certificazione JITC (Unified capabilities Collaboration Platform) (UCCP). 
  
### <a name="archiving-im-content"></a>Archiviazione del contenuto di messaggistica istantanea

Skype for Business Server offre le caratteristiche che puoi usare se l'organizzazione deve seguire le regole di conformità. È possibile usare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per determinati utenti specificati. Per informazioni dettagliate, vedere [pianificare l'archiviazione in Skype for Business Server](archiving/archiving.md). 
  
Se è stato distribuito anche Microsoft Exchange Server 2013, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Skype for Business Server e usare un singolo strumento per eseguire ricerche in entrambi i tipi di dati archiviati. Per altre informazioni, vedere [Configurare Skype for Business Server in uso per l'archiviazione di Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologie e componenti

Gli unici componenti necessari per la messaggistica istantanea e la presenza sono i seguenti:
  
- I server front-end dell'organizzazione (noti come pool) o un server Standard Edition. Le funzionalità di messaggistica istantanea e presenza sono sempre abilitate in questi server. Per altre informazioni sulle topologie e la gestione del pool di front-end, vedere [disponibilità e gestione elevata del pool Front-End](high-availability-and-disaster-recovery/high-availability.md).
    
- Un gruppo di bilanciamento del carico, se si ha un pool Enterprise Edition front-end.
    
### <a name="supported-collocation"></a>Collocazione supportata

La collocazione è definita come avente un singolo server o gruppo di server, con più ruoli installati. Per informazioni dettagliate sulla collocazione, vedere [nozioni di base sulla topologia per Skype for Business Server](topology-basics/topology-basics.md). 
  

