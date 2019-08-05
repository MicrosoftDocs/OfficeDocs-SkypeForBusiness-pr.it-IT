---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194655"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|serverID  <br/> |int, not null  <br/> |ID server. Corrisponde all'ID istanza di Central Management store.  <br/> |
|serverAddress  <br/> |nvarchar (256), not null  <br/> |Indirizzo del server tramite l'indirizzo di Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |DateTime  <br/> |L'ultima volta che il Channel Server ha aggiornato questa riga per dare prova che è in esecuzione.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|serverID  <br/> |Chiave primaria.  <br/> |
   

