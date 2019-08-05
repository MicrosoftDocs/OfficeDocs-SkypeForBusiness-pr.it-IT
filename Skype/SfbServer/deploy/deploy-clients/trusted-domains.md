---
title: Skype room System Trusted Domains
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype room System e Skype for business.
ms.openlocfilehash: eacc468508ba9107534ce4ac729edf0d0d6c895d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190991"
---
# <a name="skype-room-system-trusted-domains"></a>Skype room System Trusted Domains
 
Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype room System e Skype for business.
  
## <a name="trusted-domains"></a>Domini attendibili

Il client Skype for business Visualizza una finestra di dialogo che consente agli utenti di accettare il certificato da Skype for Business Server se il dominio SIP dell'account utente che esegue l'accesso è diverso dal nome presentato nel nome dell'oggetto o dell'oggetto alternativo del certificato. Se il certificato configurato per Skype for Business Server nell'organizzazione non ha un nome di dominio SIP per l'account di sistema room Skype in nome soggetto o oggetto alternativo, è necessario configurare i domini presentati nel certificato sotto i domini attendibili chiave del registro di sistema nel computer della console Skype room System. Il sistema Skype room System-fornito dalla guida dell'amministratore della sala Skype spiega come e dove aggiungere domini attendibili nel client Skype for business. 
  
Supponiamo ad esempio che i certificati configurati in Skype for Business Server abbiano un nome alternativo soggetto/oggetto "CONTOSO". LOCAL "e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso per Skype room System è" confrm1@contoso.net ". Dato che contoso.net non è presente nel certificato, nel computer della sala di Skype è necessario configurare "contoso. local" come dominio attendibile nel registro di sistema, come spiegato nel manuale dell'amministratore della sala di Skype room System fornito dal produttore. 
  

