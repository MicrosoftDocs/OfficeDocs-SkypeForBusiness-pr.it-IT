---
title: Aggiungere il servizio Web del Director
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.net.
ms.openlocfilehash: b89aef8be436171de76f5d5e172823ae3b0e72161cfbf6c26ea9933a8fb14ac5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344945"
---
# <a name="add-director-web-service"></a>Aggiungere il servizio Web del Director
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.net.
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno se si sta distribuendo solo un singolo Director. Se si sta configurando un bilanciamento del carico DNS (Domain Name System) per il pool di Director, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno che sia diverso dall'URL di base interno per differenziare la denominazione dei domini. Il dominio interno ad esempio è contoso.net, mentre il nome di dominio esterno è contoso.com. È possibile definire l'URL di base esterno utilizzando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di server perimetrali. Il nome di dominio dell'URL di base esterno deve corrispondere al nome di dominio dell'FQDN del proxy inverso. 
  

