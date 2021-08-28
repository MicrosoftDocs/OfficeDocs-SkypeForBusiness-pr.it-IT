---
title: Crittografia per Skype for Business Server
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da server a server richiede MTLS, indipendentemente dal fatto che il traffico sia limitato alla rete interna o attraversi il perimetro della rete interna. Quando si Skype for Business Server a sistemi IPPBX di terze parti o a trunk SIP TLS è facoltativo ma fortemente consigliato tra Mediation Server e gateway multimediale. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Di conseguenza, il gateway deve essere configurato con un certificato di un'autorità di certificazione considerato attendibile dal Mediation Server.
ms.openlocfilehash: ec87f7d2a32e02e8dcd4a4c489b77d2add3ac43a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586858"
---
# <a name="encryption-for-skype-for-business-server"></a>Crittografia per Skype for Business Server
 
Skype for Business Server utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da server a server richiede MTLS, indipendentemente dal fatto che il traffico sia limitato alla rete interna o attraversi il perimetro della rete interna. Quando si Skype for Business Server a sistemi IPPBX di terze parti o a trunk SIP TLS è facoltativo ma fortemente consigliato tra Mediation Server e gateway multimediale. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Di conseguenza, il gateway deve essere configurato con un certificato di un'autorità di certificazione considerato attendibile dal Mediation Server.
  
> [!NOTE]
> Un avviso di sicurezza relativo a SSL 3.0 è stato pubblicato nel 2014. La disabilitazione di SSL 3.0 in Skype for Business Server 2015 è un'opzione supportata. Per ulteriori informazioni sull'advisory sulla sicurezza, vedere [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013).<br/>
**Nota sulla sicurezza:** Per garantire l'utilizzo del protocollo di crittografia più forte, Skype for Business Server 2015 offrirà i protocolli di crittografia TLS nel seguente ordine ai client: **TLS 1.2, TLS 1.1, TLS 1.0.** TLS è un aspetto critico di Skype for Business Server 2015 e pertanto è necessario per mantenere un ambiente supportato.<br/>
**Nota sulla sicurezza:** Per garantire l'utilizzo del protocollo di crittografia più forte, Skype for Business Server 2019 offrirà i protocolli di crittografia TLS nell'ordine seguente ai client: **TLS 1.3, TLS 1.2**. TLS è un aspetto critico di Skype for Business Server 2019 e pertanto è necessario per mantenere un ambiente supportato. 
  
Nella tabella seguente vengono riepilogati i requisiti relativi ai protocolli per ogni tipo di traffico. 
  
**Protezione del traffico**

|**Tipo di traffico**|**Protetto da**|
|:-----|:-----|
|Da server a server  <br/> |MTLS  <br/> |
|Da client a server  <br/> |TLS  <br/> |
|Messaggistica istantanea e informazioni sulla presenza  <br/> |TLS  <br/> |
|Audio e video e condivisione desktop di elementi multimediali  <br/> |SRTP  <br/> |
|Condivisione desktop (segnalazione)  <br/> |TLS  <br/> |
|Web Conferencing  <br/> |TLS  <br/> |
|Download del contenuto delle riunioni, download della Rubrica, espansione dei gruppi di distribuzione  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Crittografia multimediale

Il traffico multimediale viene crittografato tramite SRTP (Secure RTP), un profilo del protocollo RTP (Real-Time Transport Protocol) che garantisce riservatezza, autenticazione e protezione da attacchi di tipo replay per il traffico RTP. Inoltre, il flusso multimediale in entrambe le direzioni tra Mediation Server e il successivo hop interno è anche crittografato tramite SRTP. Il flusso multimediale in entrambe le direzioni tra Mediation Server e un gateway multimediale è facoltativamente crittografato e consigliato. Il Mediation Server è in grado di supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e l'archiviazione di un certificato.
  
> [!NOTE]
> Per ulteriori informazioni sulla configurazione ibrida, vedere [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype for Business Server e Microsoft Exchange Server 2016 operano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'utilizzo degli algoritmi FIPS 140-2 per la crittografia del sistema. Per implementare il supporto FIPS, è necessario configurare ogni server che esegue Skype for Business Server supportarlo.
