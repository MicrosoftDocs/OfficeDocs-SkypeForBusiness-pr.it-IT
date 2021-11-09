---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.
ms.openlocfilehash: 980364d2483d4418177d5eaeceeb9a7ec884871d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852860"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, not null  <br/> |ID del server che ha inviato la voce.  <br/> |
|aplPeerID  <br/> |int, not null  <br/> |ID del peer a cui è connesso il server che esegue l'invio.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Chiave primaria.  <br/> |
|aplServerID  <br/> |Chiave esterna con ricerca nella tabella tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Chiave esterna con ricerca nella tabella tblServerIdentity.serverID.  <br/> |
   

