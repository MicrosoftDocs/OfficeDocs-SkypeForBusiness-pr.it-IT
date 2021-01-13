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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da server a server richiede MTLS, indipendentemente dal fatto che il traffico venga confinato alla rete interna o attraversi il perimetro della rete interna. Quando si connette Skype for Business Server a sistemi di IPPBX di terze parti o trunk SIP TLS è facoltativo ma è fortemente consigliato tra il Mediation Server e il gateway multimediale. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Pertanto, il gateway deve essere configurato con un certificato proveniente da un'autorità di certificazione considerata attendibile dal Mediation Server.
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832206"
---
# <a name="encryption-for-skype-for-business-server"></a>Crittografia per Skype for Business Server
 
Skype for Business Server utilizza TLS e MTLS per crittografare i messaggi istantanei. Tutto il traffico da server a server richiede MTLS, indipendentemente dal fatto che il traffico venga confinato alla rete interna o attraversi il perimetro della rete interna. Quando si connette Skype for Business Server a sistemi IPPBX di terze parti o trunk SIP, TLS è facoltativo ma è fortemente consigliato tra il Mediation Server e il gateway multimediale. Se TLS è configurato su questo collegamento, MTLS è obbligatorio. Pertanto, il gateway deve essere configurato con un certificato proveniente da un'autorità di certificazione considerata attendibile dal Mediation Server.
  
> [!NOTE]
> Una consulenza sulla sicurezza relativa a SSL 3,0 è stata pubblicata nel 2014. La disattivazione di SSL 3,0 in Skype for Business Server 2015 è un'opzione supportata. Per ulteriori informazioni sull'advisory sulla sicurezza, vedere [disattivazione di SSL 3,0 in Lync server 2013 e Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Nota sulla sicurezza:** Per assicurarsi che il protocollo crittografico più efficace venga utilizzato, Skype for Business Server 2015 offrirà i protocolli di crittografia TLS nell'ordine seguente ai client: **tls 1,2, tls 1,1, tls 1,0**. TLS è un aspetto critico di Skype for Business Server 2015 e pertanto è necessario per mantenere un ambiente supportato.<br/>
**Nota sulla sicurezza:** Per assicurarsi che il protocollo crittografico più efficace venga utilizzato, Skype for Business Server 2019 offrirà i protocolli di crittografia TLS nell'ordine seguente ai client: **tls 1,3, tls 1,2**. TLS è un aspetto critico di Skype for Business Server 2019 e pertanto è necessario per mantenere un ambiente supportato. 
  
Nella tabella seguente vengono riepilogati i requisiti relativi ai protocolli per ogni tipo di traffico. 
  
**Protezione del traffico**

|**Tipo di traffico**|**Protetto da**|
|:-----|:-----|
|Da server a server  <br/> |MTLS  <br/> |
|Client-to-server  <br/> |TLS  <br/> |
|Messaggistica istantanea e informazioni sulla presenza  <br/> |TLS  <br/> |
|Audio e video e condivisione desktop di elementi multimediali  <br/> |SRTP  <br/> |
|Condivisione desktop (segnalazione)  <br/> |TLS  <br/> |
|Web Conferencing  <br/> |TLS  <br/> |
|Download del contenuto delle riunioni, download della Rubrica, espansione dei gruppi di distribuzione  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Crittografia multimediale

Il traffico multimediale viene crittografato tramite SRTP (Secure RTP), un profilo del protocollo RTP (Real-Time Transport Protocol) che garantisce riservatezza, autenticazione e protezione da attacchi di tipo replay per il traffico RTP. Inoltre, il flusso multimediale in entrambe le direzioni tra Mediation Server e il successivo hop interno è anche crittografato tramite SRTP. Il flusso multimediale in entrambe le direzioni tra il Mediation Server e un gateway multimediale è facoltativamente crittografato e consigliato. Il Mediation Server è in grado di supportare la crittografia per il gateway multimediale, ma il gateway deve supportare MTLS e l'archiviazione di un certificato.
  
> [!NOTE]
> Per ulteriori informazioni sulla configurazione di un ambiente ibrido, vedere [pianificare la connettività ibrida](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype for Business Server e Microsoft Exchange Server 2016 operano con il supporto per gli algoritmi FIPS (Federal Information Processing Standard) 140-2 se i sistemi operativi Windows Server sono configurati per l'utilizzo degli algoritmi FIPS 140-2 per la crittografia del sistema. Per implementare il supporto FIPS, è necessario configurare ogni server che esegue Skype for Business Server per supportarlo.
  

