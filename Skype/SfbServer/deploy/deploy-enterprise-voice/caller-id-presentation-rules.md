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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: "Riepilogo: informazioni su come configurare l'ID chiamante utilizzando il Skype for Business Server di controllo."
ms.openlocfilehash: 7accfe11c22a8b453ac767c80a0c9269fe638c45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605595"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Creare o modificare una regola di conversione per la presentazione dell'ID chiamante in Skype for Business Server

**Riepilogo:** Informazioni su come configurare l'ID chiamante utilizzando il Skype for Business Server di controllo.

Con Skype for Business Server, il numero di telefono della parte chiamata ,ovvero il numero di telefono chiamato, può essere convertito dal formato E.164 al formato di composizione locale richiesto dal _trunk peer,_ ovvero dal gateway associato, dal PBX (Private Branch Exchange) o dal trunk SIP. A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.

Skype for Business Server offre anche la possibilità di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante sta chiamando) dal formato E.164 al formato di composizione locale richiesto dal trunk peer. È ad esempio possibile scrivere una regola di conversione per rimuovere +44 da una stringa di composizione e sostituirlo con 0144.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>Per configurare l'ID chiamante tramite Skype for Business Server pannello di controllo

1. Aprire Skype for Business Server Pannello di controllo.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.

3. Nella pagina **Configurazione trunk** fare doppio clic su un trunk esistente, ad esempio il trunk **Globale** per visualizzare la finestra di dialogo **Modifica configurazione trunk**.

4. Per configurare la presentazione dell'ID chiamante:

   - Per selezionare una o più regole in un elenco di tutte le regole di conversione disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**. In **Regola di conversione per il numero del chiamante** fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.

   - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere  [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) nella documentazione relativa alla distribuzione.

   - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) nella documentazione relativa alla distribuzione.

   - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).

   - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

     > [!CAUTION]
     > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel trunk peer associato, perché le due regole potrebbero essere in conflitto.