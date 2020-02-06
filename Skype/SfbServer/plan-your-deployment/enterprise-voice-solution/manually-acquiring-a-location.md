---
title: Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Pianificazione per gli utenti mobili in una distribuzione E9-1-1 con i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802716"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
 
Pianificazione per gli utenti mobili in una distribuzione E9-1-1 con i provider di trunking SIP, in Skype for Business Server VoIP aziendale.
  
Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. Durante una chiamata di emergenza, però, la chiamata verrà prima instradata a un dispatcher di Emergency Call Centre (ECRC) National/Regional E9-1-1, prima di essere indirizzato a un punto di risposta di sicurezza pubblica (PSAP). ECRC eseguirà una query verbale sul chiamante per una posizione e quindi inoltra la chiamata al PSAP appropriato, in base alle informazioni fornite. 
  
**Gli utenti devono essere invitati a immettere una posizione quando non vengono forniti automaticamente dal servizio informazioni sulla posizione?**
  
Ad esempio, se un client si trova in una subnet non definita, a casa, in un hotel o in qualsiasi altro punto all'esterno della rete, l'utente deve essere tenuto a immettere una posizione?
    
Per definire il comportamento del client, è possibile configurare l'impostazione della **posizione necessaria** nel criterio della posizione. L'impostazione di questo valore non significa che l'utente non verrà richiesto per una posizione. L'impostazione di questo valore su Sì significa che l'utente verrà richiesto per una posizione, ma può chiudere la richiesta. L'impostazione di questo valore su Disclaimer indica che all'utente verrà richiesto di trovare una posizione e verrà visualizzata una dichiarazione di non responsabilità se tenta di chiudere il messaggio. In tutti i casi, l'utente può continuare a usare il client come di consueto.
    
Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e viene archiviata in una tabella per utente che si trova nel client. Quando l'utente torna in qualsiasi posizione precedentemente archiviata, il client Skype for business si imposta automaticamente in tale posizione. 
  
> [!NOTE]
> È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale. 
  

