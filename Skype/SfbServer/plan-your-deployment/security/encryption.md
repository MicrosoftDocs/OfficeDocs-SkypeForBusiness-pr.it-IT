---
title: Crittografia per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server usa TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da un server all'altro richiede MTLS, indipendentemente dal fatto che il traffico sia confinato alla rete interna o attraversi il perimetro della rete interna. Quando si connette Skype for Business Server a sistemi IPPBX di terze parti o trunk SIP, è facoltativo ma fortemente consigliato tra Mediation Server e media gateway. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Di conseguenza, il gateway deve essere configurato con un certificato di una CA considerata attendibile dal server Mediation.
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194891"
---
# <a name="encryption-for-skype-for-business-server"></a>Crittografia per Skype for Business Server
 
Skype for Business Server usa TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da un server all'altro richiede MTLS, indipendentemente dal fatto che il traffico sia confinato alla rete interna o attraversi il perimetro della rete interna. Quando si connette Skype for Business Server a sistemi IPPBX di terze parti o trunk SIP, è facoltativo ma fortemente consigliato tra Mediation Server e media gateway. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Di conseguenza, il gateway deve essere configurato con un certificato di una CA considerata attendibile dal server Mediation.
  
> [!NOTE]
> Un Advisory sulla sicurezza per SSL 3,0 è stato pubblicato in 2014. La disabilitazione di SSL 3,0 in Skype for Business Server 2015 è un'opzione supportata. Per ulteriori informazioni sull'advisory sulla sicurezza, vedere Disabilitazione di [SSL 3,0 in Lync server 2013 e Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Nota sulla sicurezza:** Per assicurarsi che venga usato il protocollo crittografico più forte, Skype for Business Server 2015 offrirà ai client protocolli di crittografia TLS con l'ordine seguente: **tls 1,2, tls 1,1, tls 1,0**. TLS è un aspetto critico di Skype for Business Server 2015 e quindi è necessario per mantenere un ambiente supportato.<br/>
**Nota sulla sicurezza:** Per assicurarsi che venga usato il protocollo crittografico più forte, Skype for Business Server 2019 offrirà ai client protocolli di crittografia TLS con l'ordine seguente: **tls 1,3, tls 1,2**. TLS è un aspetto critico di Skype for Business Server 2019 e quindi è necessario per mantenere un ambiente supportato. 
  
La tabella seguente riepiloga i requisiti di protocollo per ogni tipo di traffico. 
  
**Protezione del traffico**

|**Tipologia di traffico**|**Protetto da**|
|:-----|:-----|
|Da server a server  <br/> |MTLS  <br/> |
|Da client a server  <br/> |TLS  <br/> |
|Messaggistica istantanea e presenza  <br/> |TLS  <br/> |
|Audio e video e condivisione desktop di file multimediali  <br/> |SRTP  <br/> |
|Condivisione desktop (segnalazione)  <br/> |TLS  <br/> |
|Conferenza Web  <br/> |TLS  <br/> |
|Download contenuto della riunione, download rubrica, espansione gruppo di distribuzione  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Crittografia file multimediali

Il traffico di file multimediali viene crittografato tramite Secure RTP (SRTP), un profilo di Real-Time Transport Protocol (RTP) che offre riservatezza, autenticazione e protezione dagli attacchi di riproduzione al traffico RTP. Inoltre, i file multimediali che scorrono in entrambe le direzioni tra il Mediation Server e il suo hop successivo interno sono crittografati anche tramite SRTP. Il flusso multimediale in entrambe le direzioni tra il Mediation Server e un gateway multimediale è facoltativamente crittografato e consigliato. Il Mediation Server può supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e lo spazio di archiviazione di un certificato.
  
> [!NOTE]
> Per altre informazioni sulla configurazione di Hybrid, vedere [pianificare la connettività ibrida](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype for Business Server e Microsoft Exchange Server 2016 funzionano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'uso degli algoritmi FIPS 140-2 per la crittografia del sistema . Per implementare il supporto FIPS, è necessario configurare ogni server in cui è in esecuzione Skype for Business Server per supportarlo.
  

