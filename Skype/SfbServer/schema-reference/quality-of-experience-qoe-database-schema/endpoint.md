---
title: Tabella Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella Endpoint è una tabella di supporto in cui sono archiviate informazioni sugli endpoint che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un endpoint.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823066"
---
# <a name="endpoint-table"></a>Tabella Endpoint
 
La tabella Endpoint è una tabella di supporto in cui sono archiviate informazioni sugli endpoint che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo endpoint.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome dell'endpoint.  <br/> |
|**Sistema operativo** <br/> |nvarchar(128)  <br/> | <br/> |Sistema operativo dell'endpoint.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nome della CPU dell'endpoint.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Numero di core della CPU dell'endpoint.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocità del processore della CPU dell'endpoint.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Flag di bit che indica se il sistema è in esecuzione in un ambiente virtualizzato: <br/>  0x0000 - Nessuno <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - Virtual PC <br/>  0x0008 - PC Xen <br/> |
   

