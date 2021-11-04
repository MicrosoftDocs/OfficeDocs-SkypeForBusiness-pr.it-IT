---
title: Nome di dominio completo (FQDN) per unione legacy
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: L'FQDN interno del pool di accessi perimetrali viene utilizzato per diversi scenari in cui gli utenti interni comunicano con utenti esterni per la federazione, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica. Se nell'ambiente legacy è stato distribuito un Edge Server con bilanciamento del carico, immettere il nome di dominio completo (FQDN) del servizio di bilanciamento del carico interno.
ms.openlocfilehash: a3a2017f62ffabe8f427f7e5bd048f8c6e5c3d67
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752385"
---
# <a name="legacy-merge-fqdn"></a>Nome di dominio completo (FQDN) per unione legacy
 
L'FQDN interno del pool di **accessi** perimetrali viene utilizzato per diversi scenari in cui gli utenti interni comunicano con utenti esterni per la federazione, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica. Se nell'ambiente legacy è stato distribuito un Edge Server con bilanciamento del carico, immettere il nome di dominio completo (FQDN) del servizio di bilanciamento del carico interno.
  
Il **valore della porta di** accesso SIP interna **5061** è la porta SIP TCP (Transmission Control Protocol) predefinita per la comunicazione con client, pool Front End legacy e server. Se non è stato utilizzato il valore predefinito, aggiornare il valore del campo **Porta di accesso SIP interna**.
  

