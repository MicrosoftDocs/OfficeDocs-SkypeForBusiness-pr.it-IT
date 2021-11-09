---
title: Tabella UserSite
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.
ms.openlocfilehash: 80286b04e408a8f80e63364e3c7a822ce8e63505
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851770"
---
# <a name="usersite-table"></a>Tabella UserSite
 
La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il sito utente.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Univoco  <br/> |Nome del sito utente.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

