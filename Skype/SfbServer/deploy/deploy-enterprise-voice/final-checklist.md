---
title: Elenco di controllo finale per la distribuzione del controllo di ammissione di chiamata per Skype for Business Server
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
description: Elenco di controllo finale per la distribuzione del servizio Controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830836"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Distribuzione del controllo di ammissione di chiamata: elenco di controllo finale per Skype for Business Server
 
Elenco di controllo finale per la distribuzione del servizio Controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale. 
  
Utilizzare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il servizio Controllo di ammissione di chiamata.
  
- Se vengono distribuiti uno o più server perimetrali, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco delle subnet nelle impostazioni di configurazione di rete, con una maschera di bit di 32. È inoltre necessario associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.
    
    > [!NOTE]
    > I server perimetrali non sono necessari per implementare il controllo di ammissione di chiamata. 
  
- Verificare che il servizio Controllo di ammissione di chiamata sia abilitato, come specificato in Abilitare il controllo di ammissione [di chiamata in Skype for Business Server.](enable-call-admission-control.md)
    
- Verificare che il servizio Controllo di ammissione di chiamata sia abilitato in tutti i siti centrali. Questa operazione può essere eseguita tramite generatore di topologie. Se durante la pubblicazione viene generato un avviso, *non ignorarlo.*
    
- Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete. È inoltre essenziale associare ogni subnet a un sito di rete, come illustrato in Distribuire aree [di rete, siti e subnet in Skype for Business.](deploy-network.md)
    
- Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), Audio/Video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.
    

