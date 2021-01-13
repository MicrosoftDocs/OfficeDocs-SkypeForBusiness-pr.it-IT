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
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824026"
---
# <a name="add-front-end-web-services-2010"></a>Aggiungere servizi Web di Front End Server (2010)
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
  
Non è possibile eseguire l'override del nome di dominio completo (FQDN) del pool di servizi Web interni per un server Standard Edition. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Enterprise Edition front end, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e che potrebbe essere, ad esempio, Internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Il dominio interno ad esempio è contoso.net, mentre il nome di dominio esterno è contoso.com. È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso. Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.
  

