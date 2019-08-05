---
title: Aggiungere servizi Web front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: 3317df51fcacd17de8c1ce3f40163f2ce63dc13f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187163"
---
# <a name="add-front-end-web-services"></a>Aggiungere servizi Web front-end
 
L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
  
Non è possibile eseguire l'override del nome di dominio completo del pool di servizi Web interni per un server Standard Edition. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Enterprise Edition Front-\<end, è possibile specificare un URL di base interno diverso, che deve essere diverso dall'FQDN del pool, ad esempio l'\>URL di base interno.
  
Puoi specificare un URL di base esterno diverso dall'URL di base interno per distinguere la denominazione dei domini. Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com. Definiresti l'URL della base esterna usando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di Edge. Il nome di dominio dell'URL di base esterno deve essere uguale al nome di dominio dell'FQDN del proxy inverso. La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front-end.
  

