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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194622"
---
# <a name="dialog-table"></a>Tabella Dialog
 
La tabella di finestra di dialogo è una tabella di supporto; ogni record rappresenta una finestra di dialogo SIP (Session Initiation Protocol).
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |Ora in cui l'agente QoE (Quality of Excellence) riceve il primo report da chiamante o chiamato. Usato in combinazione con SessionSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Numero di sequenza per distinguere le sessioni quando hanno lo stesso ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||ID finestra di dialogo univoco globale.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |Indice  <br/> |Checksum dell'ID della finestra di dialogo.  <br/> |
   

