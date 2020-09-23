---
title: Aggiungere servizi Web di Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217937"
---
# <a name="add-front-end-web-services"></a>Aggiungere servizi Web di Front End Server
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno per un server Standard Edition. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Enterprise Edition front end, è possibile specificare un URL di base interno diverso, che deve essere diverso dall'FQDN del pool (ad esempio, Internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno diverso dall'URL di base interno per differenziare i nomi dei domini. Il dominio interno, ad esempio, è contoso.net, ma il nome di dominio esterno è contoso.com. È possibile definire l'URL di base esterno usando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione perimetrale. Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso. Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.
  

