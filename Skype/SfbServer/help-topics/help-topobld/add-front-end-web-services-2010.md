---
title: Aggiungere servizi Web di Front End Server (2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è `https://pool01.contoso.net` , l'URL di base è `pool01.contoso.net` .
ms.openlocfilehash: 1e3cfa9fbf56819cb7e920ca312a2fecdd3db6b5
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013990"
---
# <a name="add-front-end-web-services-2010"></a>Aggiungere servizi Web di Front End Server (2010)
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è `https://pool01.contoso.net` , l'URL di base è `pool01.contoso.net` .
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno per un edizione Standard Server. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Front End di edizione Enterprise, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Ad esempio, il dominio interno è `contoso.net` , ma il nome di dominio esterno è `contoso.com` . È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso. Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.
  

