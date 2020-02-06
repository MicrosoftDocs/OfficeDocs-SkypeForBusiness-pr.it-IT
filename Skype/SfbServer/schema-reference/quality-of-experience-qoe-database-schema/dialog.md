---
title: Tabella Dialog
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809534"
---
# <a name="dialog-table"></a>Tabella Dialog
 
La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |Ora in cui l'agente QoE (Quality of Excellence) riceve il primo report da chiamante o chiamato. Usato in combinazione con SessionSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Numero di sequenza per distinguere le sessioni quando hanno lo stesso ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||ID finestra di dialogo univoco globale.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Indice  <br/> |Checksum dell'ID della finestra di dialogo.  <br/> |
   

