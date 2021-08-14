---
title: Nome di dominio completo (FQDN) per unione legacy
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: L'FQDN interno del pool di accessi perimetrali viene utilizzato per diversi scenari in cui gli utenti interni comunicano con utenti esterni per la federazione, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica. Se nell'ambiente legacy è stato distribuito un Edge Server con bilanciamento del carico, immettere il nome di dominio completo (FQDN) del servizio di bilanciamento del carico interno.
ms.openlocfilehash: 0bfbff4fcd04d0e2e202febe8601079364d4a02e966449242b1e87693c5634f9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342331"
---
# <a name="legacy-merge-fqdn"></a>Nome di dominio completo (FQDN) per unione legacy
 
L'FQDN interno del pool di **accessi** perimetrali viene utilizzato per diversi scenari in cui gli utenti interni comunicano con utenti esterni per la federazione, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica. Se nell'ambiente legacy è stato distribuito un Edge Server con bilanciamento del carico, immettere il nome di dominio completo (FQDN) del servizio di bilanciamento del carico interno.
  
Il **valore della porta di** accesso SIP interna **5061** è la porta SIP TCP (Transmission Control Protocol) predefinita per la comunicazione con client, pool Front End legacy e server. Se non è stato utilizzato il valore predefinito, aggiornare il valore del campo **Porta di accesso SIP interna**.
  

