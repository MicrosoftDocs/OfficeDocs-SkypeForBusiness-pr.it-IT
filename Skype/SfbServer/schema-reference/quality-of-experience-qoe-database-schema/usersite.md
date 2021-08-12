---
title: Tabella UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314332"
---
# <a name="usersite-table"></a>Tabella UserSite
 
La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il sito utente.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Univoco  <br/> |Nome del sito utente.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Riferimento dalla [tabella Region](region.md).  <br/> |
   

