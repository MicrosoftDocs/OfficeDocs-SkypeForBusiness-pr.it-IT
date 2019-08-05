---
title: Tabella Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194621"
---
# <a name="endpoint-table"></a>Tabella Endpoint
 
La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo endpoint.  <br/> |
|**Nome** <br/> |nvarchar (256)  <br/> |Univoci  <br/> |Nome dell'endpoint.  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |Sistema operativo (OS) dell'endpoint.  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||Nome della CPU dell'endpoint.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Numero di core della CPU dell'endpoint.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocità del processore della CPU dell'endpoint.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Flag di bit che indica se il sistema è in uso in un ambiente virtualizzato: <br/>  0x0000-None <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-Virtual PC <br/>  0x0008-Xen PC <br/> |
   

