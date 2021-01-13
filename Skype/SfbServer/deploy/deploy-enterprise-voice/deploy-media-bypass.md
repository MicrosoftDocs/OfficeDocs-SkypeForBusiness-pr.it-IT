---
title: Distribuire il bypass multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
ms.openlocfilehash: c6820438d969ce3c802060eba9bcababc0b1315d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812446"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Distribuire il bypass multimediale in Skype for Business Server
 
Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo del processo di distribuzione.
  
In questo argomento si presuppone che sia stato già pubblicato e configurato almeno uno o più Mediation Server e almeno un peer gateway per fornire la connettività PSTN. Per ulteriori informazioni su queste attività, vedere [deploy a Mediation Server in Generatore di topologie in Skype for Business Server](deploy-a-mediation-server.md) e [definire un gateway in Generatore di topologie in Skype for Business Server](define-a-gateway.md).
  
 Se il peer a cui ci si connette è l'SBC di un provider di trunking SIP, assicurarsi che il provider sia un provider qualificato e che il provider supporti il bypass multimediale. Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere traffico dal Mediation Server. In caso affermativo, non è necessario abilitare il bypass per il trunk in questione. Inoltre, non è possibile abilitare il bypass multimediale, a meno che l'organizzazione non riveli gli indirizzi IP della rete interna al provider di trunking SIP.
  
> [!NOTE]
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel [programma Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Se è già stato configurato facoltativamente il controllo di ammissione di chiamata (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita dal controllo di ammissione di chiamata non è applicabile alle chiamate per le quali viene utilizzato il bypass multimediale. La verifica dell'utilizzo del bypass multimediale viene eseguita per prima e, se il bypass multimediale è occupato, il controllo di ammissione di chiamata non viene utilizzato per la chiamata. solo se il controllo bypass multimediale ha esito negativo è la verifica eseguita per il controllo di ammissione di chiamata. Le due caratteristiche sono quindi esclusive per una chiamata specifica instradata alla rete PSTN. Questa è la logica perché il bypass multimediale presuppone che non esistano vincoli di larghezza di banda tra gli endpoint multimediali di una chiamata. il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata. Di conseguenza, una delle seguenti operazioni si applicherà a una chiamata PSTN: a) il contenuto multimediale ignora il Mediation Server e il controllo di ammissione di chiamata non riserva la larghezza di banda per la chiamata. o b) il controllo di ammissione di chiamata applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.
  
Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario abilitarlo globalmente. Le impostazioni globali di bypass multimediale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN oppure che il bypass multimediale viene utilizzato utilizzando il mapping delle subnet ai siti di rete e alle aree di rete, analogamente a quanto avviene tramite il controllo di ammissione di chiamata, un'altra funzionalità avanzata vocale. Quando il bypass multimediale e il controllo di ammissione di chiamata sono entrambi abilitati, vengono utilizzate automaticamente le informazioni relative all'area di rete, al sito di rete e alla subnet specificate per il controllo di ammissione di chiamata quando si determina se utilizzare il bypass multimediale. Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate alla rete PSTN quando è abilitato il controllo di ammissione di chiamata.
  
> [!NOTE]
> Quando si utilizzano queste procedure per configurare il bypass multimediale, si presuppone che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un sistema IP-PBX o un SBC (Session Border Controller) in un provider di trunking SIP. Se sono previsti limiti di larghezza di banda sul collegamento, non è possibile applicare il bypass multimediale alla chiamata. Il bypass multimediale non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i Session Border Controller. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati nel [programma Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Processo di distribuzione per il bypass multimediale

Nella tabella seguente viene fornita una panoramica del processo di distribuzione di bypass multimediale. 
  
|**Fase**|**Procedura**|**Ruoli**|**Documentazione relativa alla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare trunk per il bypass multimediale  <br/> |Se non è stato ancora fatto, configurare uno o più trunk per il bypass multimediale.  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare un trunk con bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurare il bypass multimediale a livello globale  <br/> |Configurare il bypass multimediale per tutte le chiamate alla rete PSTN o per alcune chiamate in base a siti e aree di rete.  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server](bypass-the-mediation-server.md) <br/> [Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'utilizzo delle informazioni sui siti e sulle aree geografiche](use-site-and-region-information.md) <br/> |
|Associare subnet a siti di rete, se necessario  <br/> |Se si configura il bypass multimediale per l'utilizzo delle informazioni relative a siti e aree geografiche, è necessario associare le subnet della distribuzione ai siti e alle aree di rete (se non è stato già fatto per un'altra funzionalità vocale).  <br/> | Membro del gruppo RTCUniversalServerAdmins o membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

