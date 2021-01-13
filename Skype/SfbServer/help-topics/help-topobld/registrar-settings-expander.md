---
title: Espansione delle impostazioni del servizio di registrazione
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
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La resilienza offre disponibilità elevata e ripristino di emergenza per il pool di registrazione. Dato che è disponibile un servizio di registrazione di backup in caso di errore del servizio di registrazione principale, quello di backup può subentrare al posto di quello in errore, permettendo agli utenti di accedere e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda dei sistemi che hanno avuto problemi con il servizio di registrazione principale.
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818296"
---
# <a name="registrar-settings-expander"></a>Espansione delle impostazioni del servizio di registrazione
 
La resilienza offre disponibilità elevata e ripristino di emergenza per il pool di registrazione. Dato che è disponibile un servizio di registrazione di backup in caso di errore del servizio di registrazione principale, quello di backup può subentrare al posto di quello in errore, permettendo agli utenti di accedere e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda dei sistemi che hanno avuto problemi con il servizio di registrazione principale.
  
Nella sezione **Resilienza** della finestra di dialogo **Modifica proprietà** per il Survivable Branch Appliance o il Survivable Branch Server è possibile modificare queste impostazioni:
  
- **Pool di registrazione di backup e servizi utente associati** Nell'elenco a discesa selezionare il pool Enterprise Edition front end o Standard Edition Front End Server che deve fungere da registrar di backup per Survivable Branch Appliance o Survivable Branch Server.
    
- **Abilitare il failover e il failback** Selezionare questa impostazione per consentire il rilevamento automatico di un registrar non riuscito e la determinazione automatica che il servizio di registrazione principale sia di nuovo attivo e pronto per riprendere il processo di registrazione.
    
- **Intervallo di rilevamento errori (sec)** Digitare il numero di secondi che devono trascorrere prima che venga stabilito che il servizio di registrazione primario ha avuto esito negativo. Il valore predefinito è 120 secondi. È necessario specificare un valore in questo campo se si seleziona **Abilita failover e failback**.
    
- **Intervallo di rilevamento del fallback (sec)** Digitare il numero di secondi che devono trascorrere prima che venga stabilito che è stato eseguito il backup del servizio di registrazione principale. Il valore predefinito è 240 secondi. È necessario specificare un valore in questo campo se si seleziona **Abilita failover e failback**.
    
> [!IMPORTANT]
> Quando si definiscono l'intervallo di rilevamento degli errori e l'intervallo di failback, fare attenzione a non immettere un intervallo che possa provocare il failover e il failback se il servizio di registrazione non risponde per un breve periodo di tempo. È infatti possibile che il servizio di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server. 
  

