---
title: Tabella Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279962"
---
# <a name="subnet-table"></a>Tabella Subnet
 
La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaria, esterna  <br/> |Rappresentazione in forma di numero intero dell'IP della subnet.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Subnet mask.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Riferimento dalla [tabella UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Descrizione della subnet.  <br/> |
   

