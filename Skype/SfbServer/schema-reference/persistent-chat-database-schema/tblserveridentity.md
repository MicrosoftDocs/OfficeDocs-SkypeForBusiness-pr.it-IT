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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server di chat attivi nel pool del server di chat persistente.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812274"
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
   

