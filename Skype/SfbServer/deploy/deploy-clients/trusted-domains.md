---
title: Domini attendibili di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype Room System e Skype for Business.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834116"
---
# <a name="skype-room-system-trusted-domains"></a>Domini attendibili di Skype Room System
 
Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype Room System e Skype for Business.
  
## <a name="trusted-domains"></a>Domini attendibili

Il client Skype for Business visualizza una finestra di dialogo che consente agli utenti di accettare il certificato da Skype for Business Server se il dominio SIP dell'account utente che accede è diverso dal nome presentato nell'oggetto o nel nome alternativo del soggetto nel certificato. Se il certificato configurato per Skype for Business Server nell'organizzazione non dispone del nome di dominio SIP dell'account skype room system in Subject o Subject Alt Name, è necessario configurare i domini presentati nel certificato nella chiave del Registro di sistema Trusted Domains nel computer console di Skype Room System. Il manuale dell'amministratore del sistema Skype Room System fornito dal produttore spiega come e dove aggiungere domini attendibili nel client Skype for Business. 
  
Ad esempio, si supponga che i certificati configurati in Skype for Business Server siano soggetti/subject alt name di "CONTOSO. LOCAL" e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso di Skype Room System è "confrm1@contoso.net". Poiché contoso.net non è presente nel certificato, nel computer Skype Room System dovrai configurare "contoso.local" come dominio attendibile nel Registro di sistema, come spiegato nella Guida dell'amministratore di Skype Room System fornita dal produttore di Skype Room System. 
  

