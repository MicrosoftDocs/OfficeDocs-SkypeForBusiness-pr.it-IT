---
title: Tabella UserAgent
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un agente utente
---

# <a name="useragent-table"></a>Tabella UserAgent
 
La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un agente utente
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'agente utente.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Stringa agente utente.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 è Mediation Server.  <br/> 2 è A/V Conferencing Server.  <br/> 4 è Skype for Business.  <br/> 8 è ip Telefono.  <br/> 16 è Live Meeting Console.  <br/> 32 è lo strumento di convalida della distribuzione (DVT).  <br/> 64 è Skype for Business Server computer Macintosh.  <br/> 128 è Skype for Business Server Attendant.  <br/> 256 è Annuncio conferenza servizio.  <br/> 512 è Conferencing Operatore automatico.  <br/> 1024 è l'applicazione Response Group.  <br/> 2048 è Outside Voice Control.  <br/> |
   

