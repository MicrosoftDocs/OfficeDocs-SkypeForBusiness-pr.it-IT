---
title: Expander delle impostazioni della route federativo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Per impostare un'assegnazione della route Federation del sito, è necessario prima di tutto abilitare la Federazione nel pool di Edge Server o Edge Server. Se Federation non è abilitato nell'Edge Server o nel pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194326"
---
# <a name="federation-route-settings-expander"></a>Expander delle impostazioni della route federativo
 
Per impostare un'assegnazione della route Federation del sito, è necessario prima di tutto abilitare la Federazione nel pool di Edge Server o Edge Server. Se Federation non è abilitato nell'Edge Server o nel pool, le impostazioni di assegnazione della route federativo per il sito non saranno disponibili per la modifica.

Se è stata configurata l'impostazione federativo in Edge Server o pool, è possibile configurare le opzioni seguenti: 
  
- **Consentire le assegnazioni di routing federativo a tutti i siti** Questa impostazione avrà effetto su tutti i siti. Verificare che l'impostazione che si sta configurando in questo sito sia appropriata per tutti i siti.
    
- **Abilitare la federazione SIP** Selezionare questa opzione per abilitare una route federativo SIP e quindi selezionare un Director o un pool di Edge come route federativo.
    
- **Abilitare la Federazione XMPP** Selezionare questa opzione per abilitare una route federativa XMPP e quindi selezionare un Director o un pool di Edge come route federativo.
- 
  > [!NOTE]
  > I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    

