---
title: Reimpostare il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812804"
---
# <a name="reset-call-admission-control"></a>Reimpostare il controllo di ammissione di chiamata

Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
  
### <a name="to-reset-cac"></a>Per reimpostare CAC

1. Aprire Generatore di topologie.
    
2. Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.
    
3. In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** . 
    
4. In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Skype for Business Server 2019 che ospita CAC e quindi fare clic su **OK**.
    
5. Pubblicare la topologia.
    

