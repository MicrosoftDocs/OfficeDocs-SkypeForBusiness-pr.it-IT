---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contiene tutti i messaggi di chat.
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194698"
---
# <a name="tblchat"></a>tblChat
 
tblChat contiene tutti i messaggi di chat.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|channelId  <br/> |int, not null  <br/> |ID nodo.  <br/> |
|chatId  <br/> |bigint e non null  <br/> |Numero sequenziale univoco (per ID nodo) che definisce l'ordine della chat room generato dalla tabella tblLastChatId.  <br/> |
|chatDate  <br/> |bigint e non null  <br/> |Indicatore di data e ora per il messaggio di chat.  <br/> |
|userId  <br/> |int, not null  <br/> |ID principale del poster.  <br/> |
|Messaggio di avviso  <br/> |bit, not null  <br/> |True se il messaggio è un messaggio di avviso. False se non lo è.  <br/> |
|contenuto  <br/> |nvarchar (max), not null  <br/> | Contenuto della chat (la versione in formato testo normale). Il contenuto è in genere in testo normale con le eccezioni seguenti: <br/>  I file sono rappresentati come ma-filelink: collegamenti. <br/>  I collegamenti sono rappresentati come elemento HTML (anche se il tipo di contenuto non può essere considerato HTML). <br/>  Le storie sono codificate come formato "[storia]...."-like. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Contenuto della chat (la versione RTF). Può essere null se il client non lo consente.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<channelID, chat\>  <br/> |Chiave primaria.  <br/> |
   

