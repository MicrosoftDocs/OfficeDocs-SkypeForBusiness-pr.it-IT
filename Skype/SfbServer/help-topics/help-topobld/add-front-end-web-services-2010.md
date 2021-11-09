---
title: Aggiungere servizi Web di Front End Server (2010)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: cbc30f550d5f012e510cb5941e97ed65668a9f2c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845499"
---
# <a name="add-front-end-web-services-2010"></a>Aggiungere servizi Web di Front End Server (2010)
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è `https://pool01.contoso.net` , l'URL di base è `pool01.contoso.net` .
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno per un edizione Standard Server. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Front End edizione Enterprise, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Ad esempio, il dominio interno è `contoso.net` , ma il nome di dominio esterno è `contoso.com` . È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso. Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.
  

