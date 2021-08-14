---
title: Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: a4220a9134917ded867b639bb019594be5e21b9191e636503ae8883a5be39d77
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344815"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010
 
In questa finestra di dialogo è possibile modificare le proprietà delle impostazioni di **Gateway PSTN Mediation Server**. È possibile definire le impostazioni seguenti:
  
- Selezionare mediation **server collocato abilitato** se si desidera collocare il Mediation Server con questo Front End Server o pool Front End.
    
- **Porte di attesa:** definire le porte su cui il Mediation Server sarà in ascolto. È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol). Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**. 
    
    > [!IMPORTANT]
    > Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi. TLS è un protocollo più sicuro, che utilizza certificati per crittografare il traffico tra Mediation Server e il gateway PSTN. Non tutti i gateway PSTN supportano TLS. 
  
- Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.
    
- Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il Mediation Server. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.
    
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  

