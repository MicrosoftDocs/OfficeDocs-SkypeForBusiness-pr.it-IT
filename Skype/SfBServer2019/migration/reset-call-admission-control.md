---
title: Reimpostare il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195854"
---
# <a name="reset-call-admission-control"></a>Reimpostare il controllo di ammissione di chiamata

Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
  
### <a name="to-reset-cac"></a>Per reimpostare CAC

1. Aprire Generatore di topologie.
    
2. Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.
    
3. In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** . 
    
4. In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Skype for Business Server 2019 che ospita CAC e quindi fare clic su **OK**.
    
5. Pubblicare la topologia.
    

