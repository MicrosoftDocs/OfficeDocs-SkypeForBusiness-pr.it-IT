---
title: Tabella UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194720"
---
# <a name="userstatistics-table"></a>Tabella UserStatistics
 
La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo utente.  <br/> |
|**LastLogInTime** <br/> |DateTime  <br/> ||Ultima volta che l'utente ha effettuato l'accesso.  <br/> |
|**LastConfOrganizedTime** <br/> |DateTime  <br/> ||L'ultima volta che l'utente ha organizzato una conferenza.  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |DateTime  <br/> ||L'ultima volta che l'utente ha riscontrato un errore di chiamata.  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |DateTime  <br/> ||L'ultima volta che l'utente ha sperimentato un errore di chiamata come organizzatore di conferenze.  <br/> |
   

