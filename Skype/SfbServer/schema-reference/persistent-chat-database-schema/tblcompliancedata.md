---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.
ms.openlocfilehash: e4f10a9a239c752bf5171f4ba7bcadcf111cef35
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596390"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, not null  <br/> |ID evento.  <br/> |
|entryDate  <br/> |smalldatetime, not null  <br/> |Data/ora di inserimento (può essere molto lontana nel futuro per cmplType=9, poiché in tal caso la voce è solo un segnaposto).  <br/> |
|cmplType  <br/> |int, not null  <br/> | Tipo di evento di conformità: <br/>  1: chat <br/>  2: dialogo della chat <br/>  3: download di file <br/>  4: caricamento di file <br/>  9: trasferimento file provvisorio <br/>  10: eliminazione della chat (con sostituzione) <br/>  11: eliminazione della chat <br/> |
|cmplTime  <br/> |bigint, not null  <br/> |Data e ora dell'evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), not null  <br/> |URI (Uniform Resource Identifier) del canale.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID chat (corrispondente alla tabella tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, not null  <br/> |ID entità di chi effettua l'invio (corrispondente alla tabella tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), not null  <br/> |URI dell'utente.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Messaggio (la codifica dipende da cmplType).  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|cmplEventID  <br/> |Chiave primaria.  <br/> |
   

