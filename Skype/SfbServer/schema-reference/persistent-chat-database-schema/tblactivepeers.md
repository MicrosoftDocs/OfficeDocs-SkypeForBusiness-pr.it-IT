---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene le connessioni peer-to-peer correnti tra i servizi di chat.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814714"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers contiene le connessioni peer-to-peer correnti tra i servizi di chat.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, not null  <br/> |ID del server che ha pubblicato la voce.  <br/> |
|aplPeerID  <br/> |int, not null  <br/> |ID del peer a cui è connesso il server di registrazione.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Chiave primaria.  <br/> |
|aplServerID  <br/> |Chiave esterna con ricerca nella tabella tblServerIdentity. serverID.  <br/> |
|aplPeerID  <br/> |Chiave esterna con ricerca nella tabella tblServerIdentity. serverID.  <br/> |
   

