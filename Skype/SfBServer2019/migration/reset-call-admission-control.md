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
ms.localizationpriority: medium
description: Se un pool Front End legacy ospita il servizio Controllo di ammissione di chiamata( CAC), è necessario spostare l'hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front End legacy.
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583450"
---
# <a name="reset-call-admission-control"></a>Reimpostare il controllo di ammissione di chiamata

Se un pool Front End legacy ospita il servizio Controllo di ammissione di chiamata( CAC), è necessario spostare l'hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front End legacy.
  
### <a name="to-reset-cac"></a>Per reimpostare il servizio Controllo di ammissione di chiamata

1. Apre lo strumento di generazione topologia
    
2. Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **Modifica proprietà**.
    
3. In **Impostazione controllo di ammissione di chiamata** assicurarsi che l'opzione **Abilita il controllo di ammissione di chiamata** sia selezionata. 
    
4. In **Pool Front End per** eseguire il controllo di ammissione di chiamata selezionare il pool Skype for Business Server 2019 che deve ospitare il servizio Controllo di ammissione di chiamata e quindi fare clic su **OK.**
    
5. Pubblicare la topologia.
    

