---
title: Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Pianificazione degli utenti mobili in una distribuzione E9-1-1 tramite provider di trunking SIP, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: cf0f023b352f27d38ceea8f9ee07b295b91ed7b3373e22f0258fea3874a9a7d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286455"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
 
Pianificazione degli utenti mobili in una distribuzione E9-1-1 tramite provider di trunking SIP, in Skype for Business Server VoIP aziendale.
  
Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. La chiamata di emergenza però verrà innanzitutto instradata a un dispatcher ECRC (Emergency Call Response Center) del servizio E9-1-1 nazionale/regionale prima di essere instradata a un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point). Il dispatcher ECRC richiederà verbalmente al chiamante la posizione e inoltrerà quindi la chiamata al centro PSAP appropriato in base alle informazioni fornite. 
  
**Agli utenti deve essere richiesto di immettere una posizione quando non ne viene fornita automaticamente una dal servizio informazioni sulla posizione?**
  
Se, ad esempio, un client si trova in una subnet non definita, a casa, in un albergo o in qualsiasi altro luogo esterno alla rete, è necessario richiedere all'utente la specifica di una posizione?
    
È possibile configurare l'impostazione **Posizione obbligatoria** nei criteri percorso per definire il comportamento del client. L'impostazione di questo valore su No indica che all'utente non verrà richiesta una posizione. Se invece si imposta il valore su Sì, all'utente verrà richiesta la specifica della posizione ma potrà ignorare il messaggio. Il valore Dichiarazione di non responsabilità indica invece che all'utente verrà richiesta una posizione e visualizzata una dichiarazione di non responsabilità se tenta di ignorare il messaggio. In tutti i casi, l'utente potrà continuare a utilizzare il client come sempre.
    
Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e archiviata in una tabella per utente presente nel client. Quando l'utente torna a una posizione memorizzata in precedenza, il client Skype for Business automaticamente imposta se stesso su tale posizione. 
  
> [!NOTE]
> È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale. 
  

