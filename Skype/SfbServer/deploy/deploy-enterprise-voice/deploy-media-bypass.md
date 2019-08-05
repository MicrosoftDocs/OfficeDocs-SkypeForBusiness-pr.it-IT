---
title: Distribuire il bypass multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo processo di distribuzione.
ms.openlocfilehash: 37812ab6784167fd59f578e5f12560fbd7e9a08a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191945"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Distribuire il bypass multimediale in Skype for Business Server
 
Distribuire il bypass multimediale in Skype for Business Server VoIP aziendale. Include i prerequisiti e l'elenco di controllo processo di distribuzione.
  
Questo argomento presuppone che sia già stato pubblicato e configurato almeno uno o più server di mediazione e almeno un peer del gateway per ottenere la connettività PSTN. Per altre informazioni su queste attività, vedere [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](deploy-a-mediation-server.md) e [definire un gateway in Generatore di topologie in Skype for Business Server](define-a-gateway.md).
  
 Se il peer a cui si connette è il SBC di un provider di trunking SIP, verificare che il provider sia un provider qualificato e che il provider supporti il bypass multimediale. Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere il traffico dal Mediation Server. In caso affermativo, l'esclusione non deve essere abilitata per il trunk in questione. Non è inoltre possibile abilitare il bypass multimediale a meno che l'organizzazione non riveli gli indirizzi IP di rete interni al provider di trunking SIP.
  
> [!NOTE]
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Se è già stato configurato facoltativamente il controllo di ammissione alle chiamate (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita tramite il controllo di ammissione delle chiamate non si applica alle chiamate per cui è impiegato il bypass multimediale. La verifica dell'uso del bypass multimediale viene eseguita per prima e, se il bypass multimediale viene impiegato, il controllo di ammissione delle chiamate non viene usato per la chiamata; solo se il controllo del bypass multimediale non riesce, viene eseguito il controllo per l'ammissione alla chiamata. Le due caratteristiche si escludono quindi a vicenda per qualsiasi chiamata specifica indirizzata alla rete PSTN. Questa è la logica perché il bypass multimediale presuppone che i vincoli di larghezza di banda non esistano tra gli endpoint multimediali di una chiamata; il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata. Di conseguenza, una delle operazioni seguenti verrà applicata a una chiamata PSTN: a) l'elemento multimediale ignora il Mediation Server e il controllo di ammissione delle chiamate non riserva la larghezza di banda per la chiamata; o b) il controllo dell'ammissione alle chiamate applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.
  
Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, devi anche abilitare il bypass multimediale a livello globale. Le impostazioni di bypass multimediale globale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN o che il bypass multimediale viene usato usando il mapping delle subnet ai siti di rete e alle aree di rete, in modo simile a quanto avviene tramite il controllo di ammissione delle chiamate, un altro funzionalità vocale avanzata. Quando il bypass multimediale e il controllo dell'ammissione alle chiamate sono entrambi abilitati, viene usata automaticamente l'area di rete, il sito di rete e le informazioni di subnet specificate per il controllo di ammissione di chiamata per determinare se usare il bypass multimediale. Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate al PSTN quando il controllo di ammissione delle chiamate è abilitato.
  
> [!NOTE]
> Quando si usano questi passaggi per configurare il bypass multimediale, si presume che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un IP-PBX o un SBC presso un provider di trunking SIP. Se sono presenti limitazioni della larghezza di banda per il collegamento, non è possibile applicare l'esclusione multimediale alla chiamata. Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in [Unified Communications Open Interoperability Program-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Processo di distribuzione per il bypass multimediale

La tabella seguente offre una panoramica del processo di distribuzione del bypass multimediale. 
  
|**Fase**|**Passaggi**|**Ruoli**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare Trunks per il bypass multimediale  <br/> |Se non è ancora stato fatto, configurare uno o più trunk per il bypass multimediale.  <br/> | Un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Configurare il bypass multimediale a livello globale  <br/> |Configurare il bypass multimediale per tutte le chiamate alla rete PSTN o per determinate chiamate in base a siti e aree di rete.  <br/> | Un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Configurare il bypass multimediale in Skype for Business Server per aggirare sempre il Mediation Server](bypass-the-mediation-server.md) <br/> [Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'uso delle informazioni sul sito e sulle aree geografiche](use-site-and-region-information.md) <br/> |
|Associare subnet a siti di rete, se necessario  <br/> |Se si configura il bypass multimediale per l'uso di informazioni sul sito e sull'area geografica, è necessario associare le subnet della distribuzione a siti e aree geografiche di rete (se non lo si è già fatto per un'altra funzionalità vocale).  <br/> | Un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator <br/> |[Associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

