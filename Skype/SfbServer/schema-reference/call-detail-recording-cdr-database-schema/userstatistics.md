---
title: Tabella UserStatistics
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. In ogni record della tabella sono archiviate informazioni sull'utilizzo del sistema da parte di un singolo utente. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 01f002e1cba20200334f8696f9fb2c20c98e82c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756449"
---
# <a name="userstatistics-table"></a>Tabella UserStatistics
 
La tabella UserStatistics è una tabella di supporto. In ogni record della tabella sono archiviate informazioni sull'utilizzo del sistema da parte di un singolo utente. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'utente.  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||Data/ora dell'ultimo accesso dell'utente.  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||Data/ora dell'ultima conferenza organizzata dall'utente.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||Data/ora dell'ultimo errore di chiamata dell'utente.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||Data/ora dell'ultimo errore di chiamata dell'utente in qualità di organizzatore di una conferenza.  <br/> |
   

