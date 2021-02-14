---
title: Tabella Dialog
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella Dialog è una tabella di supporto. Ogni record rappresenta un dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815846"
---
# <a name="dialog-table"></a>Tabella Dialog
 
La tabella Dialog è una tabella di supporto. Ogni record rappresenta un dialogo SIP (Session Initiation Protocol).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Data/ora in cui l'agente QoE (Quality of Experience) riceve il primo rapporto dal chiamante o dal destinatario della chiamata. Valore utilizzato in combinazione con SessionSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Numero sequenziale per distinguere le sessioni con valore ConferenceDateTime identico.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||ID del dialogo globalmente univoco.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Checksum dell'ID del dialogo.  <br/> |
   

