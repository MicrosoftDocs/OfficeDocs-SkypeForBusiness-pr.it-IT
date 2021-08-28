---
title: tblActivePeers
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
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.
ms.openlocfilehash: 21623df3acf8ec8077fa4f2f490f28d2e8482907
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622098"
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
   

