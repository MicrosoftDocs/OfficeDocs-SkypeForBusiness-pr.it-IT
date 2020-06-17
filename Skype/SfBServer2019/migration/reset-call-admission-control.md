---
title: Reimpostare il controllo di ammissione di chiamata
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
description: Se un pool Front end legacy ospita il controllo di ammissione di chiamata (CAC), è necessario spostare il servizio di hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front end legacy.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753298"
---
# <a name="reset-call-admission-control"></a>Reimpostare il controllo di ammissione di chiamata

Se un pool Front end legacy ospita il controllo di ammissione di chiamata (CAC), è necessario spostare il servizio di hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front end legacy.
  
### <a name="to-reset-cac"></a>Per reimpostare il servizio Controllo di ammissione di chiamata

1. Apre lo strumento di generazione topologia
    
2. Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **Modifica proprietà**.
    
3. In **Impostazione controllo di ammissione di chiamata** assicurarsi che l'opzione **Abilita il controllo di ammissione di chiamata** sia selezionata. 
    
4. In **pool Front end per eseguire il controllo di ammissione di chiamata (CAC)**, selezionare il pool di Skype for Business Server 2019 che ospita il servizio CAC e quindi fare clic su **OK**.
    
5. Pubblicare la topologia.
    

