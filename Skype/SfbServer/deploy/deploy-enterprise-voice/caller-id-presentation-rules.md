---
title: Creare o modificare una regola di traduzione per la presentazione dell'ID chiamante in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: "Riepilogo: informazioni su come configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server."
ms.openlocfilehash: d6b2e594d0f16e9b3278145087af854650a957da
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768159"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di traduzione per la presentazione dell'ID chiamante in Skype for Business Server

**Riepilogo:** Informazioni su come configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server.

Con Skype for Business Server, il numero di telefono della festa chiamata (ovvero il numero di telefono chiamato) può essere tradotto dal formato E. 164 al formato di chiamata locale richiesto dal _peer trunk_ , ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP. A tale scopo, è necessario definire una o più regole di traduzione per tradurre l'URI della richiesta prima di instradarlo al peer trunk.

Skype for Business Server offre anche l'opzione di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante chiama) dal formato E. 164 al formato di chiamata locale richiesto dal peer trunk. Ad esempio, è possibile scrivere una regola di traduzione per rimuovere + 44 dall'inizio di una stringa di chiamata e sostituirla con 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Per configurare l'ID chiamante tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.

3. Nella pagina **trunk Configuration** fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .

4. Per configurare la presentazione dell'ID chiamante:

   - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **regole di traduzione dei numeri di chiamata**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.

   - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.

   - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.

   - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

     > [!CAUTION]
     > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.


