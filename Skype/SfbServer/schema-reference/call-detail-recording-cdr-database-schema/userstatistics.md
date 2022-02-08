---
title: Tabella UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 29c710f86560ff204d1e6f97794cf6760a924242
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393678"
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
   

