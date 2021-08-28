---
title: Client per dispositivi mobili Creare o modificare la configurazione delle notifiche Push
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: La notifica Push e il Clearing House (PNCH) per le notifiche Push sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o il periodo di timeout scade.
ms.openlocfilehash: eecd164c26e1787f6efb81f5b435dbadea94b550
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631750"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile: creare o modificare la configurazione di notifiche push
 
La notifica Push e il Clearing House (PNCH) per le notifiche Push sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o il periodo di timeout scade. 
  
> [!NOTE]
> Il periodo di tempo viene impostato presso il centro di cancellazione delle notifiche Push e non è configurabile dall'utente o dall'amministratore della distribuzione. 
  
Per abilitare la notifica Push, eseguire le operazioni seguenti:
  
1. **Ambito:** Prendere nota dell'ambito per questo criterio. Può essere **Global**, che si applica a tutti gli utenti della distribuzione, o **Site**, ovvero solo gli utenti assegnati ai server principali nel sito specificato.
    
    > [!IMPORTANT]
    > Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: i criteri utente (più influenza) hanno la precedenza su un criterio sito e quindi un criterio sito sostituisce un criterio globale (meno influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. 
  
2. Selezionare i servizi di notifica push che si desidera abilitare facendo clic sulla casella di controllo per:
    
   - **Abilita notifica push Microsoft** abiliterà la notifica push al PNCH basato su cloud per Windows Phone con l'app Skype for Business cloud
    
   - **Abilita notifica push Apple** abilita la notifica push al PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e usando l'app Skype for Business
    
3. Dopo aver completato le modifiche del criterio, fare clic su **Commit** per salvare le modifiche. Se è necessario eliminare le modifiche apportate, selezionare **Annulla.** Nessuna modifica verrà salvata nel criterio.
    

