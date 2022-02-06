---
title: Elenco di controllo finale per la distribuzione del controllo di ammissione di chiamata Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Elenco di controllo finale per la distribuzione del servizio Controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale.
---

# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>Distribuzione del controllo di ammissione di chiamata: elenco di controllo finale per Skype for Business Server
 
Elenco di controllo finale per la distribuzione del servizio Controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale. 
  
Utilizzare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il servizio Controllo di ammissione di chiamata.
  
- Se vengono distribuiti uno o più server perimetrali, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco delle subnet nelle impostazioni di configurazione di rete, con una maschera di bit di 32. È inoltre consigliabile associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui viene distribuito il servizio A/V Edge.
    
    > [!NOTE]
    > I server perimetrali non sono necessari per implementare il controllo di ammissione di chiamata. 
  
- Verificare che il servizio Controllo di ammissione di chiamata sia abilitato, come specificato in [Abilitare il controllo di ammissione di chiamata in Skype for Business Server](enable-call-admission-control.md).
    
- Verificare che il controllo di ammissione di chiamata sia abilitato in tutti i siti centrali. Questa operazione può essere eseguita tramite Generatore di topologie. Se durante la pubblicazione viene generato un avviso,  *non ignorarlo*  .
    
- Assicurarsi che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete. È inoltre essenziale che ogni subnet sia associata a un sito di rete, come illustrato [in Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).
    
- Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), Audio/Video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.
    

