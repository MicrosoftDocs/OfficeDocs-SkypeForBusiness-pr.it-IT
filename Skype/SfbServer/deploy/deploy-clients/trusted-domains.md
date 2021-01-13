---
title: Domini attendibili per Skype room System
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
description: Leggere questo argomento per informazioni su come configurare domini attendibili per Skype room System e Skype for business.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834116"
---
# <a name="skype-room-system-trusted-domains"></a>Domini attendibili per Skype room System
 
Leggere questo argomento per informazioni su come configurare domini attendibili per Skype room System e Skype for business.
  
## <a name="trusted-domains"></a>Domini attendibili

Il client Skype for business Visualizza una finestra di dialogo che consente agli utenti di accettare il certificato dal server Skype for business se il dominio SIP dell'account utente che effettua l'accesso è diverso dal nome presentato nel nome dell'oggetto o dell'oggetto alt del certificato. Se il certificato configurato per Skype for Business Server nell'organizzazione non dispone del nome di dominio SIP dell'account di sistema della sala Skype in subject or subject Alt Name, è necessario configurare i domini presentati nel certificato nella chiave del registro di sistema Trusted Domains sul computer della console di Skype room System. Il manuale dell'amministratore del sistema di Skype room System ha spiegato come e dove aggiungere domini attendibili nel client Skype for business. 
  
Ad esempio, si supponga che i certificati configurati su Skype for Business Server dispongano del nome alternativo Subject/Subject di "CONTOSO. LOCAL "e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso di Skype room System è" confrm1@contoso.net ". Poiché contoso.net non è presente nel certificato, nel computer del sistema di chat room Skype è necessario configurare "contoso. local" come dominio attendibile nel registro di sistema, come spiegato nella Guida dell'amministratore del sistema di Skype room System fornito dal produttore. 
  

