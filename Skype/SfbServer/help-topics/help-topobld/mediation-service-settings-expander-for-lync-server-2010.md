---
title: Espansione delle impostazioni del servizio Mediation per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:'
ms.openlocfilehash: ddc6ab56f848179800b6398b7a638cdb7a061a9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806686"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del servizio Mediation per Lync Server 2010
 
Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:
  
- **Porte di attesa**: definire la porta **TLS** di attesa per il servizio Mediation. Per impostazione predefinita, il valore della porta è TCP 5067 su TLS (Transport Layer Security)
    
    Se lo si desidera, definire un valore di porta **TCP**. Per impostazione predefinita, il valore è TCP 5068.
    
    > [!NOTE]
    > Per abilitare l'impostazione del valore della porta TCP, selezionare **Abilita la porta TCP**. Per informazioni sui requisiti relativi alle impostazioni di porta necessarie per comunicare con il servizio Mediation, fare riferimento alla documentazione per il gateway PSTN (Public Switched Telephone Network) o IP-PBX (Internet Protocol Private Branch Exchange). 
  
- Selezionare **Abilita la porta TCP** per definire il valore di porta per le comunicazioni TCP dal gateway PSTN o IP-PBX.
    
- Un elenco di **Trunk** (ovvero trunk SIP, Session Initiation Protocol), **Gateway** (gateway PSTN o IP-PBX) e **Sito** (sito configurato per il trunk e il gateway) attualmente associati ed esistenti.
    
- Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il Mediation Server. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.
    
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

