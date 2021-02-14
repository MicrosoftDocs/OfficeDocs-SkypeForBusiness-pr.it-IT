---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: In tblChat sono inclusi tutti i messaggi di chat.
ms.openlocfilehash: b375c8c5dcd626a02f59aa9a916d3ca883e4767d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809896"
---
# <a name="tblchat"></a>tblChat
 
In tblChat sono inclusi tutti i messaggi di chat.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|channelId  <br/> |int, not null  <br/> |ID del nodo.  <br/> |
|chatId  <br/> |bigint, not null  <br/> |Numero sequenziale univoco (per ID di nodo) che definisce l'ordine delle chat room, generato dalla tabella tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, not null  <br/> |Timestamp per il messaggio chat.  <br/> |
|userId  <br/> |int, not null  <br/> |ID di entità dell'autore del post.  <br/> |
|isAlert  <br/> |bit, not null  <br/> |True se il messaggio è un messaggio di avviso. False in caso contrario.  <br/> |
|content  <br/> |nvarchar (max), not null  <br/> | Contenuto della chat (versione in testo normale). Il contenuto è solitamente in testo normale con le eccezioni seguenti: <br/>  I file sono rappresentati come collegamenti ma-filelink:. <br/>  I collegamenti sono rappresentati come elemento HTML (sebbene il tipo di contenuto non possa essere considerato HTML). <br/>  Le storie sono codificate come formato "[STORY]....". <br/> |
|rtf  <br/> |varchar(max)  <br/> |Contenuto della chat (versione RTF). Può essere Null se il client non lo fornisce.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Chiave primaria.  <br/> |
   

