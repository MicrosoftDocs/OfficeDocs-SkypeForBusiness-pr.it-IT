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
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801946"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
 
Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare la messaggistica istantanea offline in Skype for Business Server

La messaggistica istantanea offline è una funzionalità sul lato client incorporata nel client Skype for Business (2016 C2R build 16.0.6701.1000 o successiva) che sfrutta Servizi Web Exchange (EWS) per inviare messaggi dal client Skype for Business alla cassetta postale di Exchange di un utente. La messaggistica istantanea offline utilizza Servizi Web Exchange (EWS) per inviare messaggi offline dal client Skype for Business alla cassetta postale del destinatario. EWS deve essere disponibile per il client Skype for Business per l'invio dei messaggi offline. Per ulteriori informazioni sulla pianificazione della messaggistica istantanea e della presenza, vedere Pianificare la messaggistica istantanea e [la presenza in Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
  
> [!NOTE]
> Se la cassetta postale dell'utente è ospitata in Exchange locale, è necessario il client Skype for Business (2016 C2R build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Per abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server

1. Aprire Skype for Business Server Management Shell.
    
2. Eseguire il seguente comando per abilitare la messaggistica istantanea offline.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3, l'opzione EnableOfflineIM è impostata su $True per impostazione predefinita. Per disabilitare, impostare questo valore su $False. 
  
3. Eseguire il seguente comando per verificare che sia impostata la possibilità di archiviare messaggi istantanei offline.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integrazione della messaggistica istantanea offline con Exchange

La messaggistica istantanea offline non sarà disponibile per i mittenti se dispone di un criterio client che disabilita il salvataggio automatico dei messaggi offline nella cartella della cronologia conversazioni (EnableIMAutoArchiving = $false). Non esiste alcun meccanismo per verificare se il destinatario è in grado di ricevere messaggi offline.
  
Per i messaggi offline inviati all'interno della stessa organizzazione, verranno ricevuti come messaggi di posta elettronica con la classe messaggio IM.Note.MissedConversation e verranno inclusi nella cartella Conversazione senza risposta di **Outlook,** nonché nella cronologia delle conversazioni che verrà selezionata nella scheda della cronologia delle conversazioni e dell'elenco recente nei client Skype for Business.
  
Per i messaggi offline inviati dall'organizzazione federata, questi verranno ricevuti come messaggio di posta elettronica senza IM.Note.MisssedConversation e non verranno selezionati nelle cartelle della conversazione o della cronologia conversazioni senza risposta. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

Esiste un timer di due minuti da quando un messaggio offline viene inviato a quando viene raccolto ed elaborato. Se i messaggi offline non possono essere elaborati, verranno visualizzati nella directory seguente: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Il log ETL principale di Skype for Business conterrà informazioni sull'elaborazione dei messaggi offline ed è la migliore fonte per l'indagine/risoluzione dei problemi. 
  
> [!NOTE]
> È stato segnalato un problema a causa del quale i messaggi offline non sono stati inviati e la cartella "Bozze" era piena di messaggi. Questo problema si è verificato con le cassette postali locali di Exchange. The issue has been fixed in all C2R channels as of 6/14/2016.  
