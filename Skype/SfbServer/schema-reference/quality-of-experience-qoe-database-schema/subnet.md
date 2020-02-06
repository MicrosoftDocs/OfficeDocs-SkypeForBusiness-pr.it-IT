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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805204"
---
# <a name="subnet-table"></a>Tabella Subnet
 
La tabella subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione della rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaria, straniera  <br/> |Rappresentazione Integer per l'IP della subnet.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnet mask.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Esterna  <br/> |A cui si fa riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Descrizione della subnet.  <br/> |
   

