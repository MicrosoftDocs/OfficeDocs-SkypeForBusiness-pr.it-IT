---
title: Gestione messaggistica unificata di Exchange e la segreteria telefonica ospitata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: 98a7847f6d8ec5bebd1889aef57298bd36696918
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="0351b-103">Gestione messaggistica unificata di Exchange e la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="0351b-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="0351b-104">[] Puoi gestire la segreteria telefonica ospitata e la messaggistica unificata di Exchange in Skype for Business online utilizzando un set di cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0351b-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="0351b-105">Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="0351b-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="0351b-106">I cmdlet seguenti possono essere usati per gestire il servizio Messaggistica unificata di Exchange e i criteri della segreteria telefonica ospitata:</span><span class="sxs-lookup"><span data-stu-id="0351b-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="0351b-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="0351b-107">**Cmdlet**</span></span>|<span data-ttu-id="0351b-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0351b-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0351b-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="0351b-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="0351b-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="0351b-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="0351b-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="0351b-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="0351b-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="0351b-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="0351b-113">Crea e gestisce gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore quando Messaggistica unificata di Exchange è un servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="0351b-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="0351b-p101">Skype for Business online collabora con la messaggistica unificata di Exchange per fornire diverse funzionalità vocali, tra cui Operatore automatico e Accesso sottoscrittore. Operatore automatico consente di rispondere automaticamente alle chiamate e indirizzarle all'utente corretto. Accesso sottoscrittore consente agli utenti di connettersi al servizio Messaggistica unificata di Exchange e recuperare posta elettronica, messaggi vocali, contatti e informazioni di calendario.</span><span class="sxs-lookup"><span data-stu-id="0351b-p101">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access. Auto Attendant provides a way for calls to automatically be answered and routed to the correct person. Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.  </span></span><br/><br/> <span data-ttu-id="0351b-p102">Quando la messaggistica unificata di Exchange viene fornita come servizio ospitato, gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore devono essere creati usando Microsoft PowerShell. Questi oggetti vengono creati e gestiti usando i cmdlet **CsExUmContact**.</span><span class="sxs-lookup"><span data-stu-id="0351b-p102">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell. These objects are created and managed by using the **CsExUmContact** cmdlets. </span></span><br/> |
|[<span data-ttu-id="0351b-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0351b-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="0351b-120">GRANT-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="0351b-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="0351b-p103">Gestisce i criteri della segreteria telefonica ospitata in uso nell'organizzazione. I criteri della segreteria telefonica ospitata specificano il modo in cui le chiamate senza risposta vengono indirizzate al servizio Messaggistica unificata di Exchange. Questi criteri hanno effetto solo sugli utenti abilitati per la segreteria telefonica ospitata della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0351b-p103">Manages hosted voicemail policies used in the organization. Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service. These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="0351b-124">Per verificare se un utente è abilitato per la segreteria telefonica ospitata, esegui un comando simile al seguente dal prompt di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0351b-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="0351b-125">"Get-CsOnlineUser-Identity"kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="0351b-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="0351b-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="0351b-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="0351b-127">See also</span><span class="sxs-lookup"><span data-stu-id="0351b-127">Related topics</span></span>
[<span data-ttu-id="0351b-128">Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0351b-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)