---
title: Client per dispositivi mobili Creare o modificare la configurazione delle notifiche Push
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
description: La notifica Push e il Clearing House (PNCH) per le notifiche push sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o il periodo di timeout scade.
ms.openlocfilehash: 7e214b9fa92db420b0451d2a32e8158df2d5212c4394fb7307a7198ff733c425
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316292"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile: creare o modificare la configurazione di notifiche push
 
La notifica Push e il Clearing House (PNCH) per le notifiche push sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o il periodo di timeout scade. 
  
> [!NOTE]
> Il periodo di tempo viene impostato presso il centro di cancellazione delle notifiche Push e non è configurabile dall'utente o dall'amministratore della distribuzione. 
  
Per abilitare la notifica Push, eseguire le operazioni seguenti:
  
1. **Ambito:** Prendere nota dell'ambito per questo criterio. Può essere **Global**, che si applica a tutti gli utenti della distribuzione, o **Site**, ovvero solo gli utenti assegnati ai server principali nel sito specificato.
    
    > [!IMPORTANT]
    > Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: i criteri utente (più influenza) hanno la precedenza su un criterio sito e quindi un criterio sito sostituisce un criterio globale (meno influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. 
  
2. Selezionare i servizi di notifica push che si desidera abilitare facendo clic sulla casella di controllo per:
    
   - **Abilita notifica push Microsoft** abiliterà la notifica push al PNCH basato su cloud per Windows Phone con l'app Skype for Business app
    
   - **Abilita notifica push Apple** abilita la notifica push al PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e usando l'app Skype for Business
    
3. Dopo aver completato le modifiche del criterio, fare clic su **Commit** per salvare le modifiche. Se è necessario eliminare le modifiche apportate, selezionare **Annulla.** Nessuna modifica verrà salvata nel criterio.
    

