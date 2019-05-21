---
title: Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 4bc953307059a1679ad435b3674befe824e34056
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284701"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata

[] Puoi gestire la segreteria telefonica ospitata e la messaggistica unificata di Exchange in Skype for Business online utilizzando un set di cmdlet.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata

I cmdlet seguenti possono essere usati per gestire il servizio Messaggistica unificata di Exchange e i criteri della segreteria telefonica ospitata:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Crea e gestisce gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore quando Messaggistica unificata di Exchange è un servizio ospitato.  <br/><br/> Skype for Business online collabora con la messaggistica unificata di Exchange per fornire diverse funzionalità vocali, tra cui Operatore automatico e Accesso sottoscrittore. Operatore automatico consente di rispondere automaticamente alle chiamate e indirizzarle all'utente corretto. Accesso sottoscrittore consente agli utenti di connettersi al servizio Messaggistica unificata di Exchange e recuperare posta elettronica, messaggi vocali, contatti e informazioni di calendario.<br/><br/> Quando la messaggistica unificata di Exchange viene fornita come servizio ospitato, gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore devono essere creati usando Microsoft PowerShell. Questi oggetti vengono creati e gestiti usando i cmdlet **CsExUmContact**.<br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Gestisce i criteri della segreteria telefonica ospitata in uso nell'organizzazione. I criteri della segreteria telefonica ospitata specificano il modo in cui le chiamate senza risposta vengono indirizzate al servizio Messaggistica unificata di Exchange. Questi criteri hanno effetto solo sugli utenti abilitati per la segreteria telefonica ospitata della messaggistica unificata di Exchange.    <br/><br/> Per verificare se un utente è abilitato per la segreteria telefonica ospitata, esegui un comando simile al seguente dal prompt di PowerShell.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
