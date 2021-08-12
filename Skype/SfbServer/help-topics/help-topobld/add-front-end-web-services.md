---
title: Aggiungere servizi Web di Front End Server
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
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.net.
ms.openlocfilehash: b82cc8383efc32a92b46b798503a7780df82aad8c235c3d75561f895e13cdc02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314492"
---
# <a name="add-front-end-web-services"></a>Aggiungere servizi Web di Front End Server
 
L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.net.
  
Non è possibile sostituire il nome di dominio completo (FQDN) del pool di servizi Web interno per un server Standard Edition. Se si sta configurando il bilanciamento del carico DNS (Domain Name System) per un pool Front End edizione Enterprise, è possibile specificare un URL di base interno diverso, che deve essere diverso dal nome di dominio completo (ad esempio, internal- \<your base URL\> ).
  
È possibile specificare un URL di base esterno diverso dall'URL di base interno per differenziare i nomi dei domini. Il dominio interno, ad esempio, è contoso.net, ma il nome di dominio esterno è contoso.com. È possibile definire l'URL di base esterno usando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione perimetrale. Il nome di dominio dell'URL di base esterno deve essere lo stesso del nome di dominio dell'FQDN del proxy inverso. Per la messaggistica istantanea e la presenza è necessario l'accesso HTTP al pool Front End.
  

