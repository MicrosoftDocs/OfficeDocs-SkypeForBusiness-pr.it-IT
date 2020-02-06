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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814794"
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
   

