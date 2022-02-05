---
title: Skype trusted room system
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype Room System e Skype for Business.
---

# <a name="skype-room-system-trusted-domains"></a>Skype trusted room system
 
Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype Room System e Skype for Business.
  
## <a name="trusted-domains"></a>Domini attendibili

Il client Skype for Business visualizza una finestra di dialogo che consente agli utenti di accettare il certificato del Skype for Business Server se il dominio SIP dell'account utente che accede è diverso dal nome presentato nell'oggetto o nel nome alternativo dell'oggetto nel certificato. Se il certificato configurato per Skype for Business Server nell'organizzazione non dispone del nome di dominio SIP dell'account di sistema sala Skype in Subject o Subject Alt Name, è necessario configurare i domini presentati nel certificato nella chiave del Registro di sistema Trusted Domains nel computer console del sistema room di Skype. La Skype dell'amministratore di Skype Room System fornita dal Skype Room System spiega come e dove aggiungere domini attendibili nel client Skype for Business locale. 
  
Si supponga, ad esempio, che i certificati configurati Skype for Business Server un Oggetto/Oggetto Alt Name di "CONTOSO. LOCAL" e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso Skype Room System è "confrm1@contoso.net". Poiché contoso.net non è presente nel certificato, nel computer Skype Room System sarà necessario configurare "contoso.local" come dominio attendibile nel Registro di sistema, come illustrato nel manuale dell'amministratore di Skype Room System fornito dal produttore di Skype Room System. 
  

