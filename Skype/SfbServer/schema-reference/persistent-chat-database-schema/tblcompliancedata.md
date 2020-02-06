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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814664"
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
   

