---
title: "Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata in Skype for Business Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/18/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c

description: "Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online."
---

# Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata in Skype for Business Online

Puoi gestire la segreteria telefonica ospitata e la messaggistica unificata di Exchange in Skype for Business online utilizzando un set di cmdlet.
  
## Gestire la messaggistica unificata di Exchange e la segreteria telefonica ospitata

I cmdlet seguenti possono essere usati per gestire il servizio Messaggistica unificata di Exchange e i criteri della segreteria telefonica ospitata:
  
|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> [Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |Crea e gestisce gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore quando Messaggistica unificata di Exchange è un servizio ospitato.  <br/> Skype for Business online collabora con la messaggistica unificata di Exchange per fornire diverse funzionalità vocali, tra cui Operatore automatico e Accesso sottoscrittore. Operatore automatico consente di rispondere automaticamente alle chiamate e indirizzarle all'utente corretto. Accesso sottoscrittore consente agli utenti di connettersi al servizio Messaggistica unificata di Exchange e recuperare posta elettronica, messaggi vocali, contatti e informazioni di calendario.  <br/> Quando la messaggistica unificata di Exchange viene fornita come servizio ospitato, gli oggetti contatto usati per i servizi Operatore automatico e Accesso sottoscrittore devono essere creati usando Microsoft PowerShell. Questi oggetti vengono creati e gestiti usando i cmdlet **CsExUmContact**. <br/> |
|[Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> [Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |Gestisce i criteri della segreteria telefonica ospitata in uso nell'organizzazione. I criteri della segreteria telefonica ospitata specificano il modo in cui le chiamate senza risposta vengono indirizzate al servizio Messaggistica unificata di Exchange. Questi criteri hanno effetto solo sugli utenti abilitati per la segreteria telefonica ospitata della messaggistica unificata di Exchange.  <br/> Per verificare se un utente è abilitato per la segreteria telefonica ospitata, esegui un comando simile al seguente dal prompt di PowerShell.  <br/> ```Get-CsOnlineUser -Identity "kenmyer@litwareinc.com" | Select-Object HostedVoiceMail```|
   

