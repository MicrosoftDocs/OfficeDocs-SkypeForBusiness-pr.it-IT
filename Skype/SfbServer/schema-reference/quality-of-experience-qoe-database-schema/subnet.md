---
title: Tabella Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194574"
---
# <a name="subnet-table"></a>Tabella Subnet
 
La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaria, straniera  <br/> |Rappresentazione Integer per l'IP della subnet.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnet mask.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Esterna  <br/> |A cui si fa riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Descrizione della subnet.  <br/> |
   

