---
title: Tabella UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799936"
---
# <a name="useragent-table"></a>Tabella UserAgent
 
La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'agente utente.  <br/> |
|**UserAgent** <br/> |nvarchar (256)  <br/> |Univoco  <br/> |Stringa dell'agente utente.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 è Mediation Server.  <br/> 2 è A/V Conferencing Server.  <br/> 4 è Skype for business.  <br/> 8 è il telefono IP.  <br/> 16 è la console di Live Meeting.  <br/> 32 è lo strumento di convalida della distribuzione (TVP).  <br/> 64 è Skype for Business Server nei computer Macintosh.  <br/> 128 è l'operatore di Skype for Business Server.  <br/> 256 è il servizio Annuncio conferenza.  <br/> 512 è operatore automatico di conferenza.  <br/> 1024 è un'applicazione Response Group.  <br/> 2048 è un controllo vocale esterno.  <br/> |
   

