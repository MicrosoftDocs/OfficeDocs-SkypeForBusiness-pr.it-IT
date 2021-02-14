---
title: Modificare gli URL semplici dopo la migrazione
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
description: Skype for Business Server supporta URL semplici.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753906"
---
# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

Skype for Business Server supporta tre URL semplici:
  
- L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire. 
    
- L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN. 
    
- **L'amministratore** consente l'accesso rapido al Pannello di controllo di Skype for Business Server. L'URL semplice di amministrazione è interno all'organizzazione. 
    
Dopo la migrazione a Skype for Business Server, è necessario essere consapevoli dell'impatto della modifica sui record DNS e sui certificati per gli URL semplici. Se il Director di Skype for Business Server legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici. Se il Director di Skype for Business Server viene rimosso dalla topologia dopo la migrazione, i record DNS degli URL semplici devono essere aggiornati in modo che puntino a uno dei pool di Skype for Business Server. Ogni volta che si modifica il nome di un URL semplice, è necessario però eseguire Enable-CsComputer in ogni Director e Front End Server per registrare la modifica.

## <a name="to-update-the-meet-simple-url"></a>Per aggiornare l'URL semplice riunione

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **principale Skype for Business Server** e quindi scegliere Modifica **proprietà.**
    
2. Selezionare **URL semplici nel** riquadro sinistro, quindi sotto URL **riunione:** selezionare l'URL riunione e quindi fare clic su Modifica **URL.**
    
3. Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. 
    
## <a name="to-update-the-admin-simple-url"></a>Per aggiornare l'URL semplice di amministrazione

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **principale Skype for Business Server** e quindi scegliere Modifica **proprietà.**
    
2. Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.
    
   > [!TIP]
   > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è https://admin <em>\<domain\></em> ... 
  
## <a name="see-also"></a>Vedere anche

[Requisiti DNS per URL semplici in Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
