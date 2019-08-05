---
title: Processo di distribuzione per Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Procedura di distribuzione e passaggi per Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 972a8cec2794afeebc0f5ab65d89291e78b7211e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191339"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Processo di distribuzione per Call Park in Skype for business
 
Procedura di distribuzione e passaggi per Call Park in Skype for Business Server VoIP aziendale.
  
Call Park consente a un utente di VoIP aziendale di mettere una chiamata in attesa da un telefono e quindi recuperare la chiamata in un secondo momento componendo un numero interno (noto come orbita di Call Park) da qualsiasi telefono.
  
I componenti usati da Park chiamata vengono installati e abilitati automaticamente nel server front-end o Standard Edition quando si distribuisce VoIP aziendale. È tuttavia necessario usare la procedura seguente per configurare il parcheggio delle chiamate prima che sia disponibile per gli utenti. 
  
**Processo di distribuzione di Call Park**

|**Fase**|**Passaggi**|**Gruppi e ruoli obbligatori**|**Documentazione di distribuzione**|
|:-----|:-----|:-----|:-----|
|Configurare gli intervalli di orbit del parcheggio delle chiamate nella tabella Orbit  <br/> |Usa il pannello di controllo di Skype for Business Server o il cmdlet **New-CsCallParkOrbit** per creare gli intervalli di Orbit nella tabella Orbit di Call Park e associarli al servizio applicazione che ospita l'applicazione Parcheggio di chiamata. <br/> **Nota:** Per una perfetta integrazione con i dial plan esistenti, gli intervalli orbit sono in genere configurati come blocco di estensioni virtuali. L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Creare o modificare un intervallo orbit di Call Park in Skype for business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|Configurare le impostazioni di Call Park  <br/> | Usa il cmdlet **Set-CsCpsConfiguration** per configurare le impostazioni di Call Park. Come minimo, ti consigliamo di configurare l'opzione **OnTimeoutURI** per configurare la destinazione di fallback da usare in caso di timeout di una chiamata parcheggiata. È anche possibile configurare le impostazioni seguenti: <br/>  Opzionale **EnableMusicOnHold** per abilitare o disabilitare la musica in attesa. <br/>  Opzionale **MaxCallPickupAttempts** per determinare il numero di squilli di una chiamata parcheggiata di nuovo al telefono che risponde prima di inoltrare la chiamata all'URI (Uniform Resource Identifier) di fallback. <br/>  Opzionale **CallPickupTimeoutThreshold** per determinare la quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Configurare le impostazioni di Call Park in Skype for business](configure-call-park-settings.md) <br/> |
|Facoltativamente, personalizzare la musica in attesa  <br/> |Usare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile** per personalizzare e caricare un file audio, se non si vuole usare la musica predefinita in attesa. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Personalizzare la musica di Call Park in attesa di Skype for business](customize-call-park-music-on-hold.md) <br/> |
|Configurare i criteri vocali per abilitare il parcheggio delle chiamate per gli utenti  <br/> |Usa il pannello di controllo di Skype for Business Server o il cmdlet **Set-CsVoicePolicy** con l'opzione **EnableCallPark** per abilitare il parcheggio delle chiamate per gli utenti nel criterio vocale. <br/> Per impostazione predefinita, il parcheggio delle chiamate è disabilitato per tutti gli utenti.  <br/> Se si hanno più criteri vocali, verificare che la proprietà EnableCallPark sia impostata per ogni criterio vocale, non solo per i criteri predefiniti.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Abilitare il parcheggio delle chiamate per gli utenti in Skype for business](enable-call-park-for-users.md) <br/> |
|Verificare le regole di normalizzazione per il parcheggio di chiamata  <br/> |Le orbite del parcheggio delle chiamate non devono essere normalizzate. Verificare che le regole di normalizzazione non includano alcuno degli intervalli di orbita. Se necessario, creare regole di normalizzazione aggiuntive per impedire la normalizzazione delle orbite.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Verificare le regole di normalizzazione per Call Park in Skype for business](verify-normalization-rules-for-call-park.md) <br/> |
|Verificare la distribuzione di Call Park  <br/> |Verificare il parcheggio e il recupero delle chiamate per verificare che la configurazione funzioni come previsto.  <br/> |-  <br/> |[Opzionale Verificare la distribuzione di Call Park in Skype for business](optional-verify-call-park-deployment.md) <br/> |
   

