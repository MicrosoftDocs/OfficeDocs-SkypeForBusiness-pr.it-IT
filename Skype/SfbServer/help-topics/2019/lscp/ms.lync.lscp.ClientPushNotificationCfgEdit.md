---
title: Client per dispositivi mobili creare o modificare la configurazione delle notifiche push
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: La notifica push e la casa di compensazione delle notifiche push (centro PNCH) sono due parti principali della funzionalità per dispositivi mobili. La notifica push è il processo in cui viene inviato un messaggio al centro PNCH. Il messaggio viene mantenuto qui finché non può essere recapitato al client per dispositivi mobili o scade il periodo di timeout.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808746"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile: creare o modificare la configurazione di notifiche push
 
La notifica push e la casa di compensazione delle notifiche push (centro PNCH) sono due parti principali della funzionalità per dispositivi mobili. La notifica push è il processo in cui viene inviato un messaggio al centro PNCH. Il messaggio viene mantenuto qui finché non può essere recapitato al client per dispositivi mobili o scade il periodo di timeout. 
  
> [!NOTE]
> Il periodo di tempo è impostato nella barra di compensazione notifiche push e non può essere configurato dall'utente o dall'amministratore della distribuzione. 
  
Per abilitare la notifica push, eseguire le operazioni seguenti:
  
1. **Ambito:** Tenere presente l'ambito per questo criterio. Può essere **globale**, che si applica a tutti gli utenti in questa distribuzione o **sito**, che è solo gli utenti assegnati ai server Home nel sito specificato.
    
    > [!IMPORTANT]
    > Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: criteri utente (la maggior parte influenza) sostituisce un criterio di sito e quindi un criterio sito sostituisce un criterio globale (meno influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. 
  
2. Selezionare i servizi di notifica push che si desidera abilitare facendo clic sulla casella di controllo per:
    
   - **Abilita notifica push Microsoft** consentirà la notifica push al centro PNCH basato sul cloud per Windows Phone con l'app Skype for business
    
   - **Consenti notifiche push di Apple** consentirà la notifica push alla centro PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e l'utilizzo dell'app Skype for business
    
3. Dopo aver completato le modifiche del criterio, fare clic su **commit** per salvarle. Se è necessario eliminare le modifiche apportate, selezionare **Annulla**. Nessuna modifica verrà salvata nel criterio.
    

