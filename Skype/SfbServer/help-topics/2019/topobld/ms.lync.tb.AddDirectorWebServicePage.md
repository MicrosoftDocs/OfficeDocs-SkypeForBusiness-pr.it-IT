---
title: Aggiungere il servizio Web del Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è `https://pool01.contoso.net` , l'URL di base è `pool01.contoso.net` .
ms.openlocfilehash: a47149d9d4f0dfb3fed08d9727aae3803c585834
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012920"
---
# <a name="add-director-web-service"></a>Aggiungere il servizio Web del Director
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è `https://pool01.contoso.net` , l'URL di base è `pool01.contoso.net` .
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno se si sta distribuendo solo un singolo Director. Se si sta configurando un bilanciamento del carico DNS (Domain Name System) per il pool di Director, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Ad esempio, il dominio interno è `contoso.net` , ma il nome di dominio esterno è `contoso.com` . È necessario definire l'URL di base esterno utilizzando il metodo `contoso.com domain name` . Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve corrispondere al nome di dominio dell'FQDN del proxy inverso. 
  

