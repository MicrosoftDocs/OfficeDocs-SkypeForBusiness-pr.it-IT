---
title: Processo di distribuzione per il parcheggio di chiamata in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processo di distribuzione e procedura per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812356"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo di distribuzione per il parcheggio di chiamata in Skype for business
 
Processo di distribuzione e procedura per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
Parcheggio di chiamata consente a un utente di VoIP aziendale di inserire una chiamata in attesa da un telefono e quindi di recuperare la chiamata in un secondo momento componendo un numero interno (noto come orbita del parcheggio di chiamata) da qualsiasi telefono.
  
I componenti utilizzati dal parcheggio di chiamata vengono installati e abilitati automaticamente nel front end server o nel server Standard Edition quando si distribuisce VoIP aziendale. Tuttavia, è necessario utilizzare la procedura seguente per configurare il parcheggio di chiamata prima che sia disponibile per gli utenti. 
  
**Processo di distribuzione di Parcheggio di chiamata**

|**Fase**|**Procedura**|**Gruppi e ruoli obbligatori**|**Documentazione sulla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare gli intervalli dei codici orbit di parcheggio di chiamata nella tabella dei codici orbit  <br/> |Utilizzare il pannello di controllo di Skype for Business Server o il cmdlet **New-CsCallParkOrbit** per creare gli intervalli di Orbit nella tabella orbit del parcheggio di chiamata e associarli al servizio dell'applicazione che ospita l'applicazione Parcheggio di chiamata. <br/> **Nota:** Per una perfetta integrazione con i dial plan esistenti, gli intervalli di Orbit sono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri Direct Inward Dialing (DID) come numeri di codici orbit nella tabella dei codici orbit di parcheggio di chiamata non è supportata. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo di codici orbit del parcheggio di chiamata in Skype for business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurare le impostazioni del parcheggio di chiamata  <br/> | Utilizzare il cmdlet **Set-CsCpsConfiguration** per configurare le impostazioni del parcheggio di chiamata. È consigliabile configurare almeno l'opzione **OnTimeoutURI** per configurare la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata. È inoltre possibile configurare le impostazioni seguenti: <br/>  (Facoltativo) **EnableMusicOnHold** per abilitare o disabilitare la musica di attesa. <br/>  (Facoltativo) **MaxCallPickupAttempts** per determinare il numero di squilli sul telefono di destinazione di una chiamata parcheggiata prima dell'inoltro all'URI (Uniform Resource Identifier) di fallback. <br/>  (Facoltativo) **CallPickupTimeoutThreshold** per determinare quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurare le impostazioni del parcheggio di chiamata in Skype for business](configure-call-park-settings.md) <br/> |
|Se lo si desidera, personalizzare la musica di attesa  <br/> |Utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile** per personalizzare e caricare un file audio, se non si desidera utilizzare la musica di attesa predefinita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizzare la musica del parcheggio di chiamata in attesa inskype for business](customize-call-park-music-on-hold.md) <br/> |
|Configurare il criterio vocale per abilitare il parcheggio di chiamata per gli utenti  <br/> |Utilizzare il pannello di controllo di Skype for Business Server o il cmdlet **Set-CsVoicePolicy** con l'opzione **EnableCallPark** per abilitare il parcheggio di chiamata per gli utenti nel criterio vocale. <br/> Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.  <br/> Se si dispone di più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale e non solo per quello predefinito.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare il parcheggio di chiamata per gli utenti in Skype for business](enable-call-park-for-users.md) <br/> |
|Verificare le regole di normalizzazione del parcheggio di chiamata  <br/> |I codici orbit di Parcheggio di chiamata non devono essere normalizzati. Verificare che le regole di normalizzazione non includano alcun intervallo dei codici orbit. Se necessario, creare regole di normalizzazione aggiuntive per impedire che vengano normalizzati i codici orbit.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for business](verify-normalization-rules-for-call-park.md) <br/> |
|Verificare la distribuzione del parcheggio di chiamata  <br/> |Verifica del parcheggio e del recupero delle chiamate per verificare che la configurazione funzioni come previsto.  <br/> |-  <br/> |[Optional Verificare la distribuzione del parcheggio di chiamata in Skype for business](optional-verify-call-park-deployment.md) <br/> |
   

