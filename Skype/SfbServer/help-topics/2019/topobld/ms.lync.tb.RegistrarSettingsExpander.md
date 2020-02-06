---
title: Espansione delle impostazioni del servizio di registrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La resilienza garantisce l'elevata disponibilità e il ripristino di emergenza per il pool di registrar. Fornendo un registrar di backup in caso di errore del registrar principale, il registrar di backup può subentrare per il registrar non riuscito, consentendo agli utenti di accedere e comunicare. Gli utenti possono potenzialmente provare funzionalità ridotte, a seconda dei sistemi non riusciti con il registrar principale.
ms.openlocfilehash: b6dd5fac05b4692e8f30f1063ab71b1bad02d810
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797237"
---
# <a name="registrar-settings-expander"></a>Espansione delle impostazioni del servizio di registrazione
 
La resilienza garantisce l'elevata disponibilità e il ripristino di emergenza per il pool di registrar. Fornendo un registrar di backup in caso di errore del registrar principale, il registrar di backup può subentrare per il registrar non riuscito, consentendo agli utenti di accedere e comunicare. Gli utenti possono potenzialmente provare funzionalità ridotte, a seconda dei sistemi non riusciti con il registrar principale.
  
Nella sezione **resilienza** della finestra di dialogo **modifica proprietà** relativa a Survivable Branch Appliance o Survivable Branch Server è possibile modificare le impostazioni seguenti:
  
- **Servizio utente associato e pool Registrar di backup** Nell'elenco a discesa selezionare il pool di front end Enterprise Edition o il server front end Standard Edition che funge da registrar per il Survivable Branch Appliance o Survivable Branch Server.
    
- **Abilitare il failover e il failback** Selezionare questa impostazione per consentire il rilevamento automatico di un registrar non riuscito e la determinazione automatica che il registrar principale è il backup e pronto per riprendere il processo di registrazione.
    
- **Intervallo di rilevamento errori (sec)** Digitare il numero di secondi che deve trascorrere prima che venga determinato che il registrar principale non è riuscito. Il valore predefinito è 120 secondi. Questo campo è obbligatorio se si seleziona **Abilita failover e failback**.
    
- **Intervallo di rilevamento del fallback (sec)** Digitare il numero di secondi che deve trascorrere prima che venga determinato il backup del registrar principale. Il valore predefinito è 240 secondi. Questo campo è obbligatorio se si seleziona **Abilita failover e fallback**.
    
> [!IMPORTANT]
> Quando si definisce l'intervallo di rilevamento degli errori e l'intervallo di rilevamento del fallback, prestare attenzione a non immettere un intervallo che provocherà il failover e il fallback se il registrar non risponde per un breve periodo di tempo. È possibile che il registrar principale non possa rispondere per brevi periodi di tempo in base al caricamento del pool o dei server. 
  

