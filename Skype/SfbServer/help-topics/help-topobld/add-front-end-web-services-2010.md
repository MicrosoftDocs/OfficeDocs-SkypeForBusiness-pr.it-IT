---
title: Aggiungere servizi Web 2010 di Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 48d2cc4c8ce9bc1074ae42e385265b34f24c662e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685129"
---
# <a name="add-front-end-web-services-2010"></a>Aggiungere servizi Web 2010 di Front End
 
L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
  
Non è possibile eseguire l'override del nome di dominio completo del pool di servizi Web interni per un server Standard Edition. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool di front-\<end Enterprise Edition, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio\>, l'URL di base dell'interno).
  
Puoi specificare un URL di base esterno diverso dall'URL di base interno per distinguere la denominazione dei domini. Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com. Definiresti l'URL della base esterna usando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di Edge. Il nome di dominio dell'URL di base esterno deve essere uguale al nome di dominio dell'FQDN del proxy inverso. La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front-end.
  

