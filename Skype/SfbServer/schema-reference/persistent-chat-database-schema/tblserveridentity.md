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
description: Tabella tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831496"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
Tabella tblServerIdentity contiene i server chat attivi nel pool di server Chat persistente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|serverID  <br/> |int, not null  <br/> |ID del server. Corrisponde all'ID istanza dell'archivio di gestione centrale.  <br/> |
|serverAddress  <br/> |nvarchar (256), not null  <br/> |Indirizzo del server che usa l'indirizzo di Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Ora dell'ultimo aggiornamento di questa riga eseguito dal Channel Server per confermare che è in esecuzione.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|serverID  <br/> |Chiave primaria.  <br/> |
   

