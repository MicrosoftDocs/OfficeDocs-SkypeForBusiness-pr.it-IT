---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303659"
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
   

