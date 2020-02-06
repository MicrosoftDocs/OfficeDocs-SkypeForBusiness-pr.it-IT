---
title: Tabella UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805004"
---
# <a name="usersite-table"></a>Tabella UserSite
 
La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito in impostazioni di configurazione della rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il sito utente.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Univoci  <br/> |Nome del sito utente.  <br/> |
|**RegionKey** <br/> |int  <br/> |Esterna  <br/> |A cui si fa riferimento dalla [tabella Region](region.md).  <br/> |
   

