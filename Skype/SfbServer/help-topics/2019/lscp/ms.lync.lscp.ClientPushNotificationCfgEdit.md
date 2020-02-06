---
title: Creazione o modifica della configurazione delle notifiche push tramite client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: La notifica Push e il fornitore di servizi di accesso a terze parti per notifiche Push sono due elementi chiave della funzionalità per dispositivi mobili. La notifica Push è il processo di invio di un messaggio a un fornitore di servizi di accesso a terze parti per notifiche Push, che trattiene i messaggi fino a quando sarà possibile recapitarli al client mobile o fino allo scadere del periodo di timeout.
ms.openlocfilehash: 803bc61d12263e98efe5e74764f9f60f392af95f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796485"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile: creare o modificare la configurazione di notifiche Push
 
La notifica Push e il fornitore di servizi di accesso a terze parti per notifiche Push sono due elementi chiave della funzionalità per dispositivi mobili. La notifica Push è il processo di invio di un messaggio a un fornitore di servizi di accesso a terze parti per notifiche Push, che trattiene i messaggi fino a quando sarà possibile recapitarli al client mobile o fino allo scadere del periodo di timeout. 
  
> [!NOTE]
> Il periodo di timeout è impostato dal fornitore di servizi di accesso a terze parti per notifiche Push e non può essere configurato dall'utente o dall'amministratore della distribuzione. 
  
Per abilitare la notifica Push, si eseguono le operazioni seguenti:
  
1. **Ambito:** notare l'ambito di questo criterio. Può essere **Globale**, ovvero applicabile a tutti gli utenti in questa distribuzione, oppure **Sito**, ovvero relativo solo agli utenti assegnati ai server principali del sito specificato.
    
    > [!IMPORTANT]
    > Le impostazioni dei criteri applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto. 
  
2. Selezionare i servizi di notifica Push da abilitare, facendo clic sulla relativa casella di controllo:
    
   - **Abilitare la notifica push Microsoft** consentirà la notifica push al centro PNCH basato su cloud per Windows Phone con l'app Skype for business
    
   - **Abilitare la notifica push Apple** consentirà la notifica push all'Apple centro PNCH per i dispositivi che usano iOS di Apple, ad esempio iPhone, iPad, e l'uso dell'app Skype for business
    
3. Al termine delle modifiche del criterio, fare clic su **Commit** per salvare le modifiche. Per eliminare le modifiche eseguite, selezionare **Annulla**. Non verranno salvate modifiche al criterio.
    

