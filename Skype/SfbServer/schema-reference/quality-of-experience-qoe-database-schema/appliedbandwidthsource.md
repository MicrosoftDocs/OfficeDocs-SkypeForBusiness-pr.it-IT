---
title: Tabella AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta una sola origine.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194643"
---
# <a name="appliedbandwidthsource-table"></a>Tabella AppliedBandwidthSource
 
La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta una sola origine.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'origine.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Univoci  <br/> |Questa è l'origine del limite di larghezza di banda imposto. Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".  <br/> |
   

