---
title: Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server include i gruppi di controllo di accesso basati sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere Servizi di dominio Active Directory per Skype for Business Server. Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere le modifiche apportate dalla preparazione della foresta in Skype for Business Server nella documentazione relativa alla distribuzione.
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2019
ms.locfileid: "36196042"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a>Controllo di accesso basato sui ruoli (RBAC) per Skype for Business Server
 
Skype for Business Server include i gruppi di controllo di accesso basati sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza. Questi gruppi vengono creati durante la preparazione della foresta. Per informazioni dettagliate sulla preparazione della foresta, vedere [servizi di dominio Active Directory per Skype for Business Server](active-directory-domain-services.md). Per informazioni dettagliate sui gruppi specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.
  
Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti i ruoli amministrativi predefiniti, inclusi i 11 ruoli predefiniti che coprono molte attività amministrative comuni. Ogni ruolo è associato a un elenco specifico dei cmdlet di Skype for Business Server Management Shell che gli utenti possono eseguire in tale ruolo. Puoi usare RBAC per seguire il principio "privilegio minimo", in cui gli utenti ricevono solo le abilità amministrative necessarie per i loro processi. 
  
Per ulteriori informazioni sui ruoli RBAC, vedere [pianificazione del controllo di accesso basato sui ruoli](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).
