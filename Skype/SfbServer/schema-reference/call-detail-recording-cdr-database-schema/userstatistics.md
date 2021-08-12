---
title: Tabella UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. In ogni record della tabella sono archiviate informazioni sull'utilizzo del sistema da parte di un singolo utente. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d0d3fde20f7c8c94629f75ff00f310111cac16d386fc0b0373ee07b5c2a35fb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302210"
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
   

