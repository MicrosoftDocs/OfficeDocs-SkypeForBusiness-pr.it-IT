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
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contiene le connessioni peer-to-peer correnti tra i servizi di chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194706"
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
   

