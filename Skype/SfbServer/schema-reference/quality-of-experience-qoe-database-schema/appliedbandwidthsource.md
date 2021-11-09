---
title: Tabella AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.
ms.openlocfilehash: 10dbe69533fe26ba156c270f003fb11ab56e5179
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856433"
---
# <a name="appliedbandwidthsource-table"></a>Tabella AppliedBandwidthSource
 
La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'origine.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Univoco  <br/> |Origine del limite della larghezza di banda imposto. Descrive da dove proviene il limite di larghezza di banda (ad esempio, "Policy Server", "TURN Server" o "Modality").  <br/> |
   

