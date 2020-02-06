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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta una sola origine.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811444"
---
# <a name="appliedbandwidthsource-table"></a>Tabella AppliedBandwidthSource
 
La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta una sola origine.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'origine.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Univoci  <br/> |Questa è l'origine del limite di larghezza di banda imposto. Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".  <br/> |
   

