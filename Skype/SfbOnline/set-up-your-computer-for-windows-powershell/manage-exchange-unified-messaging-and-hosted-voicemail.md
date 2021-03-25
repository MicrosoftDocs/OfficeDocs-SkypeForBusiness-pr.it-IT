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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113202"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata

[] Puoi gestire la segreteria telefonica ospitata e la messaggistica unificata di Exchange in Skype for Business online utilizzando un set di cmdlet.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata

I cmdlet seguenti possono essere usati per gestire il servizio Messaggistica unificata di Exchange e i criteri della segreteria telefonica ospitata:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Crea e gestisce gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore quando Messaggistica unificata di Exchange è un servizio ospitato.  <br/><br/> Skype for Business online collabora con la messaggistica unificata di Exchange per fornire diverse funzionalità vocali, tra cui Operatore automatico e Accesso sottoscrittore. Operatore automatico consente di rispondere automaticamente alle chiamate e indirizzarle all'utente corretto. Accesso sottoscrittore consente agli utenti di connettersi al servizio Messaggistica unificata di Exchange e recuperare posta elettronica, messaggi vocali, contatti e informazioni di calendario.<br/><br/> Quando la messaggistica unificata di Exchange viene fornita come servizio ospitato, gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore devono essere creati usando Microsoft PowerShell. Questi oggetti vengono creati e gestiti usando i cmdlet **CsExUmContact**.<br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Gestisce i criteri della segreteria telefonica ospitata in uso nell'organizzazione. I criteri della segreteria telefonica ospitata specificano il modo in cui le chiamate senza risposta vengono indirizzate al servizio Messaggistica unificata di Exchange. Questi criteri hanno effetto solo sugli utenti abilitati per la segreteria telefonica ospitata della messaggistica unificata di Exchange.    <br/><br/> Per verificare se un utente è abilitato per la segreteria telefonica ospitata, esegui un comando simile al seguente dal prompt di PowerShell.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
