---
title: Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'In questa finestra di dialogo è possibile modificare le proprietà delle impostazioni di Gateway PSTN Mediation Server. È possibile definire le impostazioni seguenti:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217727"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010
 
In questa finestra di dialogo è possibile modificare le proprietà delle impostazioni di **Gateway PSTN Mediation Server**. È possibile definire le impostazioni seguenti:
  
- Selezionare il **Mediation Server collocato abilitato** se si desidera collocare il Mediation Server con il front end server o i pool Front end.
    
- **Porte di attesa**: consente di definire le porte che il Mediation server ascolterà. È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol). Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**. 
    
    > [!IMPORTANT]
    > Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, utilizzando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS. 
  
- Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.
    
- Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il Mediation Server. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.
    
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

