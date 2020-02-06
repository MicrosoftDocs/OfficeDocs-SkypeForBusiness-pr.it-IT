---
title: Tabella UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805054"
---
# <a name="useragent-table"></a>Tabella UserAgent
 
La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo agente utente.  <br/> |
|**UserAgent** <br/> |nvarchar (256)  <br/> |Univoci  <br/> |Stringa agente utente.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 è Mediation Server.  <br/> 2 è un/V Conferencing Server.  <br/> 4 è Skype for business.  <br/> 8 è il telefono IP.  <br/> 16 è la console Live Meeting.  <br/> 32 è lo strumento di convalida della distribuzione (TVP).  <br/> 64 è Skype for Business Server su computer Macintosh.  <br/> 128 è Skype for Business Server Attendant.  <br/> 256 è un servizio di annunci conferenza.  <br/> 512 è operatore automatico di conferenza.  <br/> 1024 è un'applicazione Response Group.  <br/> 2048 è il controllo vocale esterno.  <br/> |
   

