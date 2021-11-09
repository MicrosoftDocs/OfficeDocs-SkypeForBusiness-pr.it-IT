---
title: Processo di distribuzione per parcheggio di chiamata in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Processo di distribuzione e passaggi per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b734aba8c2944cab37071773d27bbc9411a18b9c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861853"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo di distribuzione per parcheggio di chiamata in Skype for Business
 
Processo di distribuzione e passaggi per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
Parcheggio di chiamata consente a un utente VoIP aziendale di mettere in attesa una chiamata da un telefono e quindi recuperare la chiamata in un secondo momento componendo un numero interno (noto come orbit del parcheggio di chiamata) da qualsiasi telefono.
  
I componenti utilizzati da Parcheggio di chiamata vengono installati e abilitati automaticamente nel Front End Server o nel server edizione Standard quando si distribuisce VoIP aziendale. Tuttavia, è necessario eseguire la procedura seguente per configurare parcheggio di chiamata prima che sia disponibile per gli utenti. 
  
**Processo di distribuzione di Parcheggio di chiamata**

|**Fase**|**Procedura**|**Gruppi e ruoli obbligatori**|**Documentazione sulla distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare gli intervalli dei codici orbit di parcheggio di chiamata nella tabella dei codici orbit  <br/> |Utilizzare Skype for Business Server Pannello di controllo o il cmdlet **New-CSCallParkOrbit** per creare gli intervalli di orbit nella tabella orbit del parcheggio di chiamata e associarli al servizio applicazione che ospita l'applicazione Parcheggio di chiamata. <br/> **Nota:** Per una perfetta integrazione con i dial plan esistenti, gli intervalli di orbit sono in genere configurati come un blocco di estensioni virtuali. L'assegnazione di numeri Direct Inward Dialing (DID) come numeri di codici orbit nella tabella dei codici orbit di parcheggio di chiamata non è supportata. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo di orbit del parcheggio di chiamata in Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurare le impostazioni del parcheggio di chiamata  <br/> | Utilizzare il cmdlet **Set-CsCpsConfiguration** per configurare le impostazioni del parcheggio di chiamata. Come minimo, è consigliabile configurare l'opzione **OnTimeoutURI** per configurare la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata. È inoltre possibile configurare le impostazioni seguenti: <br/>  (Facoltativo) **EnableMusicOnHold** per abilitare o disabilitare la musica di attesa. <br/>  (Facoltativo) **MaxCallPickupAttempts** per determinare il numero di squilli sul telefono di destinazione di una chiamata parcheggiata prima dell'inoltro all'URI (Uniform Resource Identifier) di fallback. <br/>  (Facoltativo) **CallPickupTimeoutThreshold** per determinare quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurare le impostazioni del parcheggio di chiamata in Skype for Business](configure-call-park-settings.md) <br/> |
|Se lo si desidera, personalizzare la musica di attesa  <br/> |Utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile** per personalizzare e caricare un file audio, se non si desidera utilizzare la musica di attesa predefinita. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business](customize-call-park-music-on-hold.md) <br/> |
|Configurare i criteri vocali per abilitare parcheggio di chiamata per gli utenti  <br/> |Utilizzare Skype for Business Server pannello di controllo o il cmdlet **Set-CSVoicePolicy** con l'opzione **EnableCallPark** per abilitare Parcheggio di chiamata per gli utenti nei criteri vocali. <br/> Per impostazione predefinita, parcheggio di chiamata è disabilitato per tutti gli utenti.  <br/> Se si dispone di più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale e non solo per quello predefinito.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare parcheggio di chiamata per gli utenti in Skype for Business](enable-call-park-for-users.md) <br/> |
|Verificare le regole di normalizzazione del parcheggio di chiamata  <br/> |I codici orbit di Parcheggio di chiamata non devono essere normalizzati. Verificare che le regole di normalizzazione non includano alcun intervallo dei codici orbit. Se necessario, creare regole di normalizzazione aggiuntive per impedire che vengano normalizzati i codici orbit.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|Verificare la distribuzione del parcheggio di chiamata  <br/> |Testare il parcheggio e il recupero delle chiamate per assicurarsi che la configurazione funzioni come previsto.  <br/> |-  <br/> |[(Facoltativo) Verificare la distribuzione del parcheggio di chiamata in Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

