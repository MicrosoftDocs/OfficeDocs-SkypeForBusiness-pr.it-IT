---
title: Expander per le impostazioni del servizio di mediazione front end per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'È possibile modificare le proprietà delle impostazioni del gateway PSTN di Mediation Server in questa finestra di dialogo. Si definiscono le impostazioni seguenti:'
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189911"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expander per le impostazioni del servizio di mediazione front end per Lync Server 2010
 
È possibile modificare le proprietà delle impostazioni del **gateway PSTN di Mediation Server** in questa finestra di dialogo. Si definiscono le impostazioni seguenti:
  
- Selezionare il **Mediation Server collocato abilitato** se si vuole collocare il Mediation Server con questo server front-end o i pool Front-end.
    
- **Porte in ascolto**: definire le porte che il server di mediazione ascolterà. Puoi definire una porta per **TLS** o Transport Layer Security o **TCP**o Transport Control Protocol. Per rendere disponibile la voce di porta per TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**. 
    
    > [!IMPORTANT]
    > Fare riferimento alla documentazione e alle impostazioni di configurazione per il gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, usando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS. 
  
- Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.
    
- Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il servizio Mediation. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.
    
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

