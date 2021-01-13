---
title: Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Skype for Business Server
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Checklist finale per la distribuzione del controllo di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830836"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Distribuzione dei controlli di ammissione di chiamata: elenco di controllo finale per Skype for Business Server
 
Checklist finale per la distribuzione del controllo di ammissione di chiamata (CAC) in Skype for Business Server VoIP aziendale. 
  
Utilizzare l'elenco di controllo seguente per verificare che siano state completate tutte le attività di configurazione necessarie per la distribuzione dei controlli di ammissione di chiamata (CAC).
  
- Se uno o più server perimetrali sono distribuiti, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco di subnet nelle impostazioni di configurazione di rete, con una maschera di bit pari a 32. È inoltre consigliabile associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.
    
    > [!NOTE]
    > I server perimetrali non sono necessari per implementare il servizio di controllo di ammissione. 
  
- Verificare che CAC sia abilitato, come specificato in [Enable Call Admission Control in Skype for Business Server](enable-call-admission-control.md).
    
- Verificare che il servizio di controllo di ammissione sia abilitato in tutti i siti centrali. È possibile eseguire questa operazione tramite il generatore di topologie. Se viene generato un avviso quando si  *pubblica, non*  ignorarlo.
    
- Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione di rete. È inoltre essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md).
    
- Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), audio/video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.
    

