---
title: Espansione delle impostazioni del servizio Mediation per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:'
ms.openlocfilehash: 29c5172157d993c73ca35a5217c67ee6d6df87ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696971"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del servizio Mediation per Lync Server 2010
 
Per modificare le proprietà del servizio Mediation, definire le proprietà seguenti:
  
- **Porte di attesa**: definire la porta **TLS** di attesa per il servizio Mediation. Per impostazione predefinita, il valore della porta è TCP 5067 su TLS (Transport Layer Security)
    
    Se lo si desidera, definire un valore di porta **TCP**. Per impostazione predefinita, il valore è TCP 5068.
    
    > [!NOTE]
    > Per abilitare l'impostazione del valore della porta TCP, selezionare **Abilita la porta TCP**. Per informazioni sui requisiti relativi alle impostazioni di porta necessarie per comunicare con il servizio Mediation, fare riferimento alla documentazione per il gateway PSTN (Public Switched Telephone Network) o IP-PBX (Internet Protocol Private Branch Exchange). 
  
- Selezionare **Abilita la porta TCP** per definire il valore di porta per le comunicazioni TCP dal gateway PSTN o IP-PBX.
    
- Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.
    
- Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il servizio Mediation. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.
    
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

