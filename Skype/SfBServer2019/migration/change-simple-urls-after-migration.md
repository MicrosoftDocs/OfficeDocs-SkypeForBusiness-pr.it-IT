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
description: Skype for Business Server supporta gli URL semplici.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753906"
---
# <a name="change-simple-urls-after-migration"></a>Modificare gli URL semplici dopo la migrazione

Skype for Business Server supporta tre URL semplici:
  
- **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute. 
    
- **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information. 
    
- L' **amministratore** consente di accedere rapidamente al pannello di controllo di Skype for Business Server. L'URL semplice di amministrazione è interno all'organizzazione. 
    
Dopo aver eseguito la migrazione a Skype for Business Server, è necessario essere a conoscenza del modo in cui la modifica incide sui record DNS e sui certificati per gli URL semplici. Se il Director di Skype for Business Server legacy rimane in uso nella topologia, non sono necessarie modifiche agli URL semplici. Se il Director di Skype for Business Server è stato rimosso dalla topologia dopo la migrazione, è necessario aggiornare i record DNS degli URL semplificati in modo che puntino a uno dei pool di Skype for Business Server. Ogni volta che si modifica il nome di un URL semplice, è necessario però eseguire Enable-CsComputer in ogni Director e Front End Server per registrare la modifica.

## <a name="to-update-the-meet-simple-url"></a>Per aggiornare l'URL semplice riunione

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server**e quindi scegliere **modifica proprietà**.
    
2. Nel riquadro sinistro selezionare URL **semplici** , quindi fare clic su URL di **riunione** e quindi su **modifica URL**.
    
3. Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. 
    
## <a name="to-update-the-admin-simple-url"></a>Per aggiornare l'URL semplice di amministrazione

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server**e quindi scegliere **modifica proprietà**.
    
2. Selezionare gli URL **semplici** nel riquadro sinistro, quindi sotto la casella **URL di accesso amministrativo** , immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.
    
   > [!TIP]
   > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>Vedere anche

[Requisiti DNS per gli URL semplici in Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
