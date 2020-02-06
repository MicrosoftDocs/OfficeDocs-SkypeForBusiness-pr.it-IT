---
title: Aggiungere il servizio Web Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796555"
---
# <a name="add-director-web-service"></a>Aggiungere il servizio Web Director
 
L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.
  
Non è possibile eseguire l'override del nome di dominio completo (FQDN) del pool di servizi Web interni se si sta distribuendo solo un singolo amministratore. Se si configura un bilanciamento del carico DNS (Domain Name System) per pool di amministratori, è possibile specificare un URL di base interno diverso (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, l'URL\<\>di base interno).
  
Puoi specificare un URL di base esterno diverso dall'URL di base interno per distinguere la denominazione dei domini. Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com. Definiresti l'URL della base esterna usando il nome di dominio contoso.com. Questo è importante per i server proxy inversi per una distribuzione di Edge. Il nome di dominio dell'URL di base esterno deve essere uguale al nome di dominio dell'FQDN del proxy inverso. 
  

