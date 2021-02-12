---
title: Creare o modificare una regola di conversione per la presentazione dell'ID chiamante in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Riepilogo: informazioni su come configurare l'ID chiamante utilizzando il Pannello di controllo di Skype for Business Server."
ms.openlocfilehash: ca1451a051a1c9053b88861222d2c4d42c5d555b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804186"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di conversione per la presentazione dell'ID chiamante in Skype for Business Server

**Riepilogo:** Informazioni su come configurare l'ID chiamante utilizzando il Pannello di controllo di Skype for Business Server.

Con Skype for Business Server, il numero di telefono della parte chiamata (ovvero il numero di telefono chiamato) può essere convertito dal formato E.164 al formato di composizione locale richiesto dal  _trunk peer_ (ovvero il gateway associato, pbx o trunk SIP). A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.

Skype for Business Server offre anche la possibilità di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante sta chiamando) dal formato E.164 al formato di composizione locale richiesto dal trunk peer. È ad esempio possibile scrivere una regola di conversione per rimuovere +44 da una stringa di composizione e sostituirlo con 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Per configurare l'ID chiamante utilizzando il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.

3. Nella pagina **Configurazione trunk** fare doppio clic su un trunk esistente, ad esempio il trunk **Globale** per visualizzare la finestra di dialogo **Modifica configurazione trunk**.

4. Per configurare la presentazione dell'ID chiamante:

   - Per selezionare una o più regole in un elenco di tutte le regole di conversione disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. In **Regola di conversione per il numero del chiamante** fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.

   - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.

   - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.

   - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

     > [!CAUTION]
     > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel trunk peer associato, perché le due regole potrebbero essere in conflitto.


