---
title: Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server include i gruppi di controllo di accesso basati sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere Servizi di dominio Active Directory per Skype for Business Server. Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere le modifiche apportate dalla preparazione della foresta in Skype for Business Server nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 41efad45b442d9c7fca82d090afa0d1aa23e7d63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815624"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server
 
Skype for Business Server include i gruppi di controllo di accesso basati sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere [servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md). Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.
  
Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti i ruoli amministrativi predefiniti, inclusi i 11 ruoli predefiniti che coprono molte attività amministrative comuni. Ogni ruolo è associato a un elenco specifico dei cmdlet di Skype for Business Server Management Shell che gli utenti possono eseguire in tale ruolo. Puoi usare RBAC per seguire il principio "privilegio minimo", in cui gli utenti ricevono solo le abilità amministrative necessarie per i loro processi. 
  
Per ulteriori informazioni sui ruoli RBAC, vedere [pianificazione del controllo di accesso basato sui ruoli](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).
