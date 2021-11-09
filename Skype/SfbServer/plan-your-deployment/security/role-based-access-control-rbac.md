---
title: Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server include Role-Based RBAC (Access Control) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere Active Directory Domain Services for Skype for Business Server. Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere Changes made by forest preparation in Skype for Business Server nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 8b4f96764487ba20e2699ea8f22e1b065e109e8b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858953"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server
 
Skype for Business Server include Role-Based RBAC (Access Control) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md). Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.
  
Con RBAC, il privilegio amministrativo viene concesso assegnando gli utenti a ruoli amministrativi predefiniti, inclusi gli 11 ruoli predefiniti che coprono molte attività amministrative comuni. Ogni ruolo è associato a un elenco specifico di cmdlet Skype for Business Server Management Shell che gli utenti in tale ruolo possono eseguire. È possibile utilizzare RBAC per seguire il principio del "privilegio minimo", in cui agli utenti vengono fornite solo le capacità amministrative richieste dai loro processi. 
  
Per ulteriori informazioni sui ruoli RBAC, vedere [Planning for role-based access control](/lyncserver/lync-server-2013-planning-for-role-based-access-control).