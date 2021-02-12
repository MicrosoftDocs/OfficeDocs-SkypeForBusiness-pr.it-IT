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
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825426"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server
 
Pianificazione degli utenti mobili in una distribuzione E9-1-1 tramite provider di trunking SIP, in Skype for Business Server VoIP aziendale.
  
Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. La chiamata di emergenza però verrà innanzitutto instradata a un dispatcher ECRC (Emergency Call Response Center) del servizio E9-1-1 nazionale/regionale prima di essere instradata a un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point). Il dispatcher ECRC richiederà verbalmente al chiamante la posizione e inoltrerà quindi la chiamata al centro PSAP appropriato in base alle informazioni fornite. 
  
**Agli utenti deve essere richiesto di immettere una posizione quando non viene fornita automaticamente dal servizio Informazioni percorso?**
  
Se, ad esempio, un client si trova in una subnet non definita, a casa, in un albergo o in qualsiasi altro luogo esterno alla rete, è necessario richiedere all'utente la specifica di una posizione?
    
È possibile configurare l'impostazione **Posizione obbligatoria** nei criteri percorso per definire il comportamento del client. L'impostazione di questo valore su No indica che all'utente non verrà richiesta una posizione. Se invece si imposta il valore su Sì, all'utente verrà richiesta la specifica della posizione ma potrà ignorare il messaggio. Il valore Dichiarazione di non responsabilità indica invece che all'utente verrà richiesta una posizione e visualizzata una dichiarazione di non responsabilità se tenta di ignorare il messaggio. In tutti i casi, l'utente potrà continuare a utilizzare il client come sempre.
    
Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e archiviata in una tabella per utente presente nel client. Quando l'utente torna a una posizione memorizzata in precedenza, il client Skype for Business si imposta automaticamente su tale posizione. 
  
> [!NOTE]
> È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale. 
  

