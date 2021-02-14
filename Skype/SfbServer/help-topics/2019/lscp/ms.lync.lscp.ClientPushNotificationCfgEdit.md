---
title: Creazione o modifica della configurazione delle notifiche Push da parte del client mobile
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
description: La notifica Push e il PNCH (Push Notification Clearing House) sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o fino alla scadenza del periodo di timeout.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808746"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile: creare o modificare la configurazione di notifiche push
 
La notifica Push e il PNCH (Push Notification Clearing House) sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o fino alla scadenza del periodo di timeout. 
  
> [!NOTE]
> Il periodo di tempo viene impostato presso il centro di raccolta delle notifiche Push e non è configurabile dall'utente o dall'amministratore della distribuzione. 
  
Per abilitare la notifica Push, eseguire le operazioni seguenti:
  
1. **Ambito:** Prendere nota dell'ambito di questo criterio. Può essere **Global**, applicabile a tutti gli utenti della distribuzione, oppure **Site**, ovvero solo gli utenti assegnati ai server principali del sito specificato.
    
    > [!IMPORTANT]
    > Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: i criteri utente (maggiore influenza) sostituiscono i criteri sito, quindi i criteri sito sostituiscono i criteri globali (meno influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. 
  
2. Selezionare i servizi di notifica Push che si desidera abilitare facendo clic sulla casella di controllo per:
    
   - **Abilitare la notifica push Microsoft** abiliterà la notifica push al PNCH basato sul cloud per Windows Phone con l'app Skype for Business
    
   - **Abilita la** notifica push Apple abiliterà la notifica push al PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e l'uso dell'app Skype for Business
    
3. Dopo aver completato le modifiche del criterio, fare clic su **Salva** per salvare le modifiche. Se è necessario eliminare le modifiche apportate, selezionare **Annulla.** Nessuna modifica verrà salvata nel criterio.
    

