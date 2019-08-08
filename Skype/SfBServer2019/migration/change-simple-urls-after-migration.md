---
title: Modificare gli URL semplici dopo la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server supporta URL semplici.
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239704"
---
# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

Skype for Business Server supporta tre semplici URL:
  
- L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione. Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire. 
    
- **** L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con chiamata in ingresso. L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie. 
    
- L' **amministratore** consente l'accesso rapido al pannello di controllo di Skype for Business Server. L'URL semplice amministratore è interno dell'organizzazione. 
    
Dopo aver eseguito la migrazione a Skype for Business Server, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici. Se il Director di Skype for Business Server legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici. Se il Director di Skype for Business Server viene rimosso dalla topologia dopo la migrazione, è necessario che i record DNS URL semplici vengano aggiornati in modo che puntino a uno dei pool di Skype for Business Server. Ogni volta che si modifica un nome di URL semplice, è necessario eseguire Enable-CsComputer su ogni Director e front end server per registrare la modifica.

## <a name="to-update-the-meet-simple-url"></a>Per aggiornare l'URL semplice riunione

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo superiore **di Skype for Business Server**e quindi scegliere **modifica proprietà**.
    
2. Selezionare **URL semplici** nel riquadro sinistro, quindi sotto gli **URL delle riunioni:** Selezionare l'URL di riunione e quindi fare clic su **modifica URL**.
    
3. Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. 
    
## <a name="to-update-the-admin-simple-url"></a>Per aggiornare l'URL semplice dell'amministratore

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo superiore **di Skype for Business Server**e quindi scegliere **modifica proprietà**.
    
2. Selezionare **URL semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** immettere l'URL semplice da usare per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.
    
   > [!TIP]
   > È consigliabile usare l'URL più semplice possibile per l'URL di amministratore. L'opzione più semplice è https://admin. <em> \<domain\></em>. 
  
## <a name="see-also"></a>Vedere anche

[Requisiti DNS per gli URL semplici in Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
