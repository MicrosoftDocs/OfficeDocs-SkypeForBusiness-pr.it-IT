---
title: Tabella endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella Endpoint è una tabella di supporto in cui sono archiviate le informazioni sugli endpoint che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
ms.openlocfilehash: 7e892d0e913f8b06fc78f00fbbb348774b9548d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834002"
---
# <a name="endpoint-table"></a>Tabella endpoint
 
La tabella Endpoint è una tabella di supporto in cui sono archiviate le informazioni sugli endpoint che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo endpoint.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome endpoint.  <br/> |
|**Sistema operativo** <br/> |nvarchar(128)  <br/> | <br/> |Sistema operativo dell'endpoint.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nome CPU dell'endpoint.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Numero di core della CPU dell'endpoint.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocità del processore della CPU dell'endpoint.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Flag di bit che indica se il sistema è in esecuzione in un ambiente virtualizzato: <br/>  0x0000 - Nessuno <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - Virtual PC <br/>  0x0008 - PC Xen <br/> |
   

