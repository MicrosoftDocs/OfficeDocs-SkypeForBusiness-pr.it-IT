---
title: Espansione delle impostazioni della route di federazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che nell'Edge Server o nel pool Edge Server sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819466"
---
# <a name="federation-route-settings-expander"></a>Espansione delle impostazioni della route di federazione
 
Per impostare un'assegnazione di route di federazione per il sito, è necessario innanzitutto che nell'Edge Server o nel pool Edge Server sia abilitata la federazione. In caso contrario, le impostazioni di assegnazione della route di federazione per il sito non saranno disponibili per la modifica.

Se l'impostazione di federazione nel server perimetrale o nel pool è stata configurata, sarà possibile configurare le opzioni seguenti: 
  
- **Consenti assegnazioni route di federazione a tutti i siti** Questa impostazione avrà effetto su tutti i siti. Accertarsi quindi che l'impostazione da configurare per questo sito sia appropriata per tutti i siti.
    
- **Abilitare la federazione SIP** Selezionare questa opzione per abilitare una route di federazione SIP e quindi selezionare un director o un pool di server perimetrali come route di federazione.
    
- **Abilitare la federazione XMPP** Selezionare questa opzione per abilitare una route di federazione XMPP e quindi selezionare un director o un pool di server perimetrali come route di federazione.
- 
  > [!NOTE]
  > I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)
    

