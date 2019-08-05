---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194699"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint e non null  <br/> |ID evento.  <br/> |
|entryDate  <br/> |smalldatetime, not null  <br/> |Ora di inserimento (può essere lontano in futuro per cmplType = 9 perché la voce è solo un segnaposto in questo caso).  <br/> |
|cmplType  <br/> |int, not null  <br/> | Tipo di evento di conformità: <br/>  1: chat <br/>  2: backchat <br/>  3: download di file <br/>  4: caricamento di file <br/>  9: trasferimento di file provvisorio <br/>  10: eliminazione della chat (con Sostituisci) <br/>  11: eliminazione chat <br/> |
|cmplTime  <br/> |bigint e non null  <br/> |Indicatore di data e ora per l'evento.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), not null  <br/> |URI (Uniform Resource Identifier) del canale.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |ID chat (corrispondente alla tabella tblChat. chatId).  <br/> |
|cmplUserID  <br/> |int, not null  <br/> |ID principale del poster (corrispondente alla tabella tblPrincipal. prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), not null  <br/> |URI utente.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Messaggio (la codifica dipende da cmplType).  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|cmplEventID  <br/> |Chiave primaria.  <br/> |
   

