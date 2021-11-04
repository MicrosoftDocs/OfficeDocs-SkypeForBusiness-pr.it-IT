---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
ms.openlocfilehash: 65c9106584d6159421964da0329563cd263281ed
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768434"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|serverID  <br/> |int, not null  <br/> |ID del server. Corrisponde all'ID dell'istanza dall'archivio di gestione centrale.  <br/> |
|serverAddress  <br/> |nvarchar (256), not null  <br/> |Indirizzo del server che usa l'indirizzo di Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Ora dell'ultimo aggiornamento di questa riga eseguito dal Channel Server per confermare che è in esecuzione.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|serverID  <br/> |Chiave primaria.  <br/> |
   

