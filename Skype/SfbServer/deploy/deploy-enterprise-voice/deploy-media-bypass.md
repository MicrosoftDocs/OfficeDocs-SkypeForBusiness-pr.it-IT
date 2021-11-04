---
title: Distribuire il bypass multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
ms.openlocfilehash: f5bed4cf31158ea170b78110f3b6f5561aedb21d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769664"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Distribuire il bypass multimediale in Skype for Business Server
 
Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
  
In questo argomento si presuppone che siano già stati pubblicati e configurati almeno uno o più Mediation Server e almeno un peer gateway per fornire la connettività PSTN. Per ulteriori informazioni su tali attività, vedere [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md) e Define a gateway in [Topology Builder in Skype for Business Server](define-a-gateway.md).
  
 Se il peer a cui ci si connette è il controller SBC di un provider di trunking SIP, verificare che il provider sia un provider qualificato e che il provider supporti il bypass multimediale. Ad esempio, molti provider di trunking SIP consentiranno solo al proprio SBC di ricevere traffico dal Mediation Server. In tal caso, il bypass non deve essere abilitato per il trunk in questione. Inoltre, non è possibile abilitare il bypass multimediale a meno che l'organizzazione non riveli i propri indirizzi IP di rete interni al provider di trunking SIP.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PBC Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program - Lync Server.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
Se è già stato configurato il servizio Controllo di ammissione di chiamata( CAC), un'altra funzionalità avanzata di VoIP aziendale, tenere presente che la prenotazione della larghezza di banda eseguita dal controllo di ammissione di chiamata non si applica ad alcuna chiamata per la quale viene utilizzato il bypass multimediale. La verifica dell'utilizzo del bypass multimediale viene eseguita per prima e, se viene utilizzato il bypass multimediale, il controllo di ammissione di chiamata non viene utilizzato per la chiamata. solo se il controllo del bypass multimediale ha esito negativo viene eseguito per il controllo di ammissione di chiamata. Le due funzionalità si escludono quindi a vicenda per qualsiasi chiamata specifica instradata alla rete PSTN. Questa è la logica perché il bypass multimediale presuppone che non esistano vincoli di larghezza di banda tra gli endpoint multimediali in una chiamata. Non è possibile eseguire il bypass multimediale sui collegamenti con larghezza di banda limitata. Di conseguenza, a una chiamata PSTN verrà applicata una delle condizioni seguenti: a) il supporto ignora il Mediation Server e il controllo di ammissione di chiamata non riserva larghezza di banda per la chiamata. o b) il controllo di ammissione di chiamata applica la prenotazione della larghezza di banda alla chiamata e i supporti vengono elaborati dal Mediation Server coinvolto nella chiamata.
  
Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario abilitarlo globalmente. Le impostazioni globali di bypass multimediale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN oppure che il bypass multimediale viene utilizzato utilizzando il mapping delle subnet a siti di rete e aree di rete, in modo analogo a quanto avviene per il controllo di ammissione di chiamata, un'altra funzionalità vocale avanzata. Quando il bypass multimediale e il controllo di ammissione di chiamata sono entrambi abilitati, le informazioni relative all'area di rete, al sito di rete e alla subnet specificate per il controllo di ammissione di chiamata vengono utilizzate automaticamente per determinare se utilizzare il bypass multimediale. Ciò significa che non è possibile specificare che il bypass multimediale sia sempre tentato per le chiamate alla rete PSTN quando è abilitato il controllo di ammissione di chiamata.
  
> [!NOTE]
> Quando si utilizzano queste procedure per configurare il bypass multimediale, si presuppone che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un sistema IP-PBX o un SBC (Session Border Controller) in un provider di trunking SIP. Se sono previsti limiti di larghezza di banda sul collegamento, non è possibile applicare il bypass multimediale alla chiamata. Il bypass multimediale non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i Session Border Controller. Microsoft ha testato un set di gateway PSTN e SBC con partner certificati ed ha eseguito alcuni test con IP-PBC Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program - Lync Server.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
## <a name="deployment-process-for-media-bypass"></a>Processo di distribuzione per bypass multimediale

Nella tabella seguente viene fornita una panoramica del processo di distribuzione del bypass multimediale. 
  
|**Fase**|**Procedura**|**Ruoli**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare i trunk per il bypass multimediale  <br/> |Se non è già stato fatto, configurare uno o più trunk per il bypass multimediale.  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare un trunk con bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurare il bypass multimediale a livello globale  <br/> |Configurare il bypass multimediale per tutte le chiamate alla rete PSTN o per determinate chiamate basate su siti di rete e aree di rete.  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server](bypass-the-mediation-server.md) <br/> [Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per usare le informazioni sul sito e sull'area geografica](use-site-and-region-information.md) <br/> |
|Associare subnet a siti di rete, se necessario  <br/> |Se si configura il bypass multimediale per l'utilizzo delle informazioni su siti e aree geografiche, è necessario associare le subnet della distribuzione a siti e aree di rete (se non è già stato fatto per un'altra funzionalità vocale).  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
