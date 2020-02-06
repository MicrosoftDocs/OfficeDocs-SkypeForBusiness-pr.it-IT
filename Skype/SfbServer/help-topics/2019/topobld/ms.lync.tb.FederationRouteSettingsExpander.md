---
title: Espansione delle impostazioni della route di federazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Per impostare un'assegnazione della route Federation del sito, è necessario prima di tutto abilitare la Federazione nel pool di Edge Server o Edge Server. Se Federation non è abilitato nell'Edge Server o nel pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.
ms.openlocfilehash: fafc576e3fd3a3c33d17728437c8472eaf1a57e9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793694"
---
# <a name="federation-route-settings-expander"></a>Espansione delle impostazioni della route di federazione
 
Per impostare un'assegnazione della route Federation del sito, è necessario prima di tutto abilitare la Federazione nel pool di Edge Server o Edge Server. Se Federation non è abilitato nell'Edge Server o nel pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.

Se è stata configurata l'impostazione federativo in Edge Server o pool, è possibile configurare le opzioni seguenti: 
  
- **Consentire le assegnazioni di routing federativo a tutti i siti** Questa impostazione avrà effetto su tutti i siti. Verificare che l'impostazione che si sta configurando in questo sito sia appropriata per tutti i siti.
    
- **Abilitare la federazione SIP** Selezionare questa opzione per abilitare una route federativo SIP e quindi selezionare un Director o un pool di Edge come route federativo.
    
- **Abilitare la Federazione XMPP** Selezionare questa opzione per abilitare una route federativa XMPP e quindi selezionare un Director o un pool di Edge come route federativo.
- 
  > [!NOTE]
  > I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    

