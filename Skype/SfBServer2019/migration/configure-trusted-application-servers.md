---
title: Configurare i server applicazioni attendibili
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool hop successivo come pool di Skype for Business Server 2019. In un ambiente misto, nell'elenco a discesa vengono visualizzati sia il pool legacy che il pool di Skype for Business Server 2019. La selezione del pool legacy non è supportata.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753946"
---
# <a name="configure-trusted-application-servers"></a>Configurare i server applicazioni attendibili

In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool hop successivo come pool di Skype for Business Server 2019. In un ambiente misto, nell'elenco a discesa vengono visualizzati sia il pool legacy che il pool di Skype for Business Server 2019. La selezione del pool legacy non è supportata.
  
> [!IMPORTANT]
> Se si esegue la migrazione di un server applicazioni attendibili, è necessario aggiornare anche la versione di UCMA in uso. Se si crea un nuovo pool di applicazioni attendibili per Skype for Business Server 2019, è necessario aggiornare UCMA alla versione inclusa in Skype for Business Server 2019 o alla versione più recente disponibile. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selezionare Skype for Business Server 2019 come hop successivo quando si crea un server applicazioni attendibili

1. Apre lo strumento di generazione topologia
    
2. Nel riquadro sinistro fare clic con il pulsante destro del mouse **su Server applicazioni attendibili** e scegliere Nuovo pool di applicazioni **attendibili.**
    
3. Immettere **l'FQDN del** pool di applicazioni attendibili e specificare se sarà a server singolo o a più server. 
    
4. Fare clic su **Avanti**.
    
5. Nella pagina **Seleziona l'hop** successivo, nell'elenco, selezionare il pool Front End di Skype for Business Server 2019. 
    
6. Fare clic su **Fine**.
    
7. Selezionare il nodo principale **Skype for Business Server** e scegliere Pubblica dal menu **Azione.** 
    
    Verificare che **il pool di applicazioni** attendibili sia stato creato correttamente e che sia associato al pool Front End corretto. 
    

