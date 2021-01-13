---
title: Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: In Skype for Business Server sono inclusi i gruppi di controllo di accesso Role-Based (RBAC) che consentono di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Tali gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere Servizi di dominio Active Directory per Skype for Business Server. Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere changes made by Forest preparation in Skype for Business Server nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 9d3c453d4e7c3057c03f99cf2ff31b5fe17ae0bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832106"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controllo dell'accesso basato sui ruoli (RBAC) per Skype for Business Server
 
In Skype for Business Server sono inclusi i gruppi di controllo di accesso Role-Based (RBAC) che consentono di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Tali gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere [servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md). Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere [changes made by Forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.
  
Con RBAC, i privilegi amministrativi vengono concessi assegnando gli utenti ai ruoli amministrativi predefiniti, inclusi i 11 ruoli predefiniti che coprono molte attività amministrative comuni. Ogni ruolo è associato a un elenco specifico di cmdlet di Skype for Business Server Management Shell che gli utenti di quel ruolo sono autorizzati a eseguire. È possibile utilizzare RBAC per seguire il principio "privilegio minimo", in cui agli utenti vengono fornite solo le abilità amministrative richieste dai loro processi. 
  
Per ulteriori informazioni sui ruoli RBAC, vedere [pianificazione del controllo di accesso basato sui ruoli](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).
