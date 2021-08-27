---
title: Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
ms.openlocfilehash: 31c27a84965e3b75515c206f8dc984b2eaa178eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578040"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
 
Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare la messaggistica istantanea offline in Skype for Business Server

La messaggistica istantanea offline è una funzionalità sul lato client incorporata nel client Skype for Business (2016 C2R build 16.0.6701.1000 o versione successiva) che sfrutta i servizi Web Exchange (EWS) per inviare messaggi dal client Skype for Business alla cassetta postale Exchange di un utente. La messaggistica istantanea offline Exchange Web Services (EWS) per inviare messaggi offline dal client Skype for Business alla cassetta postale del destinatario. EWS deve essere disponibile per il client Skype for Business per l'invio dei messaggi offline. Per ulteriori informazioni sulla pianificazione della messaggistica istantanea e della [presenza,](../../plan-your-deployment/instant-messaging-and-presence.md)vedere Plan for instant messaging and presence in Skype for Business Server .
  
> [!NOTE]
> Se la cassetta postale dell'utente è ospitata in Exchange locale, è necessario il client Skype for Business (2016 C2R build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Per abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server

1. Aprire la Skype for Business Server Management Shell.
    
2. Eseguire il comando seguente per abilitare la messaggistica istantanea offline.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3, l'opzione EnableOfflineIM è impostata su $True per impostazione predefinita. Per disabilitare, impostare questo valore su $False. 
  
3. Eseguire il comando seguente per verificare che sia impostata la possibilità di archiviare messaggi istantanei offline.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integrazione della messaggistica istantanea offline con Exchange

La messaggistica istantanea offline non sarà disponibile per i mittenti se dispone di un criterio client che disabilita il salvataggio automatico dei messaggi offline nella cartella della cronologia conversazioni (EnableIMAutoArchiving = $false). Non esiste alcun meccanismo per verificare se il destinatario è in grado di ricevere messaggi offline.
  
Per i messaggi offline inviati all'interno della stessa organizzazione, questi verranno ricevuti come messaggio di posta elettronica  con classe messaggio IM.Note.MissedConversation e verranno inclusi nella cartella Conversazione senza risposta di Outlook, nonché nella cronologia delle conversazioni che verrà selezionata nella scheda Elenco recente/Cronologia conversazioni nei client Skype for Business.
  
Per i messaggi offline inviati dall'organizzazione federata, questi verranno ricevuti come messaggio di posta elettronica senza IM.Note.MisssedConversation e non verranno raccolti nelle cartelle della conversazione senza risposta o della cronologia delle conversazioni. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

Esiste un timer di due minuti da quando viene inviato un messaggio offline quando viene raccolto ed elaborato. Se i messaggi offline non possono essere elaborati, verranno visualizzati nella directory seguente: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Il registro Skype for Business ETL conterrà informazioni sull'elaborazione dei messaggi offline ed è la fonte migliore per l'indagine/risoluzione dei problemi. 
  
> [!NOTE]
> È stato segnalato un problema a causa del quale i messaggi offline non sono stati inviati e la cartella "Bozze" era piena di messaggi. Ciò si è verificato Exchange cassette postali locali. Il problema è stato risolto in tutti i canali C2R dal 14/06/2016.  
