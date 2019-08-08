---
title: Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Elenco di controllo finale per la distribuzione di controlli di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 275afdfcb3c5e2b7cc635e073bcb5b9ba5edc853
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240569"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Distribuzione del controllo di ammissione alle chiamate: elenco di verifica finale per Skype for Business Server
 
Elenco di controllo finale per la distribuzione di controlli di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale. 
  
Usare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il controllo di ammissione di chiamata (CAC).
  
- Se vengono distribuiti uno o più Edge Server, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco subnet nelle impostazioni di configurazione della rete, con una maschera di bit di 32. Devi anche associare questa subnet (indirizzo IP) con l'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.
    
    > [!NOTE]
    > I server perimetrali non sono obbligatori per implementare CAC. 
  
- Verificare che CAC sia abilitato, come specificato in [Abilita controllo ammissione chiamata in Skype for Business Server](enable-call-admission-control.md).
    
- Verificare che CAC sia abilitato in tutti i siti centrali. Questa operazione può essere eseguita tramite il generatore di topologie. Se viene generato un avviso durante la pubblicazione, *non* ignorarlo.
    
- Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete. È anche essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md).
    
- Verificare che la subnet o gli indirizzi IP di tutti i server front-end, Survivable Branch Appliances (SBAs), audio/video Conferencing Servers (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione della rete.
    

