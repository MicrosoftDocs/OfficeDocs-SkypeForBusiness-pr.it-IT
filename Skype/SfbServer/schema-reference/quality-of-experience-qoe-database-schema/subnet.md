---
title: Tabella Subnet
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.
---

# <a name="subnet-table"></a>Tabella Subnet
 
La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaria, esterna  <br/> |Rappresentazione in forma di numero intero dell'IP della subnet.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnet mask.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descrizione della subnet.  <br/> |
   

