---
title: Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191534"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server
 
Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare la messaggistica istantanea offline in Skype for Business Server

La messaggistica istantanea offline è una caratteristica lato client integrata nel client Skype for business (2016 C2R Build 16.0.6701.1000 o versione successiva) che sfrutta i servizi Web Exchange (EWS) per inviare messaggi dal client Skype for business alla cassetta postale di Exchange di un utente. La messaggistica istantanea offline usa i servizi Web Exchange (EWS) per inviare messaggi offline dal client Skype for business alla cassetta postale del destinatario. EWS deve essere disponibile per il client Skype for business per inviare messaggi offline. Per altre informazioni sulla pianificazione per la messaggistica istantanea e la presenza, vedere [pianificare la messaggistica istantanea e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Se la cassetta postale dell'utente è ospitata in Exchange locale, è necessario il client Skype for business (2016 C2R Build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Per abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server

1. Aprire Skype for Business Server Management Shell.
    
2. Eseguire il comando seguente per abilitare la messaggistica istantanea offline.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3 l'opzione EnableOfflineIM è impostata su $True per impostazione predefinita. Per disabilitare, imposta questo valore su $False. 
  
3. Eseguire il comando seguente per verificare che sia impostata la possibilità di archiviare i messaggi istantanei offline.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integrazione di messaggistica istantanea offline con Exchange

La messaggistica istantanea offline non sarà disponibile per i mittenti se ha un criterio client che disabilita il salvataggio automatico dei messaggi offline nella cartella Cronologia conversazioni (EnableIMAutoArchiving = $false). Non esiste un meccanismo per verificare se il destinatario è in grado di ricevere messaggi offline.
  
Per i messaggi offline inviati all'interno della stessa organizzazione verranno ricevuti come messaggio di posta elettronica con la classe messaggio di messaggistica istantanea. Nota. MissedConversation e verrà incluso nella cartella delle **conversazioni perse** in Outlook, oltre alla cronologia delle conversazioni che verrà ripresa nella scheda cronologia delle conversazioni/elenchi recenti nei client Skype for business.
  
Per i messaggi offline inviati dall'organizzazione federata verranno ricevuti come messaggio di posta elettronica senza messaggistica istantanea. Nota. MisssedConversation e non verranno rilevati nelle cartelle della conversazione o della cronologia delle conversazioni perse. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

C'è un timer da due minuti quando viene inviato un messaggio offline quando viene raccolto ed elaborato. Se non è possibile elaborare i messaggi offline, verranno visualizzati nella directory seguente: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Il log ETL principale di Skype for business conterrà informazioni sull'elaborazione dei messaggi offline ed è l'origine migliore per l'analisi/risoluzione dei problemi. 
  
> [!NOTE]
> È stato segnalato un problema in cui i messaggi offline non sono stati inviati e la cartella "bozze" è stata riempita con i messaggi. Questo problema si verifica con le cassette postali di Exchange locale. Il problema è stato risolto in tutti i canali di C2R a partire da 6/14/2016.  
