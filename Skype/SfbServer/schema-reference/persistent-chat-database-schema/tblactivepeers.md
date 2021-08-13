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
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: In tblActivePeers sono incluse le connessioni peer-to-peer correnti tra i servizi chat.
ms.openlocfilehash: 7ba8bb5730dc1c08a3d0f8aa13d1173192b7cc65134d90c75061ede0db5aa98d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336396"
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
   

