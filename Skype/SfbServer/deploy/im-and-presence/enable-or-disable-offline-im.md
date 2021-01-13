---
title: Abilitare o disabilitare la messaggistica istantanea offline (IM) in Skype for Business Server
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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare o disabilitare la messaggistica istantanea offline (IM) in Skype for Business Server
 
Informazioni su come abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Abilitare la messaggistica istantanea offline (IM) in Skype for Business Server

La messaggistica istantanea offline è una funzionalità client integrata nel client Skype for business (2016 C2R Build 16.0.6701.1000 o versione successiva) che utilizza servizi Web Exchange (EWS) per inviare messaggi dal client Skype for business alla cassetta postale di Exchange di un utente. La messaggistica istantanea offline utilizza servizi Web Exchange (EWS) per inviare messaggi offline dal client Skype for business alla cassetta postale del destinatario. EWS deve essere disponibile per il client Skype for business per i messaggi offline da inviare. Per ulteriori informazioni sulla pianificazione della messaggistica istantanea e della presenza, vedere [pianificare la messaggistica istantanea e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Se la cassetta postale dell'utente è ospitata in Exchange locale, è necessario il client Skype for business (2016 C2R Build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Per abilitare o disabilitare la messaggistica istantanea offline in Skype for Business Server

1. Aprire la shell di gestione di Skype for Business Server.
    
2. Eseguire il seguente comando per abilitare la messaggistica istantanea offline.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > In Skype for Business Server 2015 CU3, l'opzione EnableOfflineIM è impostata su $True per impostazione predefinita. Per disabilitare, impostare questo valore su $False. 
  
3. Eseguire il seguente comando per verificare che la possibilità di archiviare i messaggi di messaggistica istantanea offline sia impostata.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integrazione di messaggistica istantanea offline con Exchange

La messaggistica istantanea offline non sarà disponibile per i mittenti se dispone di un criterio client che disabilita il salvataggio automatico dei messaggi offline nella cartella Cronologia conversazioni (EnableIMAutoArchiving = $false). Non esiste un meccanismo per controllare se il destinatario è in grado di ricevere messaggi non in linea.
  
Per i messaggi offline inviati all'interno della stessa organizzazione, verranno ricevuti come messaggio di posta elettronica con la classe messaggio di messaggistica istantanea. note. MissedConversation e verranno inclusi nella cartella di **conversazione senza risposta** di Outlook, nonché nella cronologia delle conversazioni che verranno raccolte nella scheda cronologia recente elenco/conversazione nei client Skype for business.
  
Per i messaggi non in linea inviati dall'organizzazione federata verranno ricevuti come messaggio di posta elettronica senza IM. note. MisssedConversation e non verranno ritirati nelle cartelle di conversazione o di cronologia delle conversazioni perse. 
  
## <a name="troubleshooting"></a>Risoluzione dei problemi

È presente un timer di due minuti da quando viene inviato un messaggio offline al momento della raccolta e dell'elaborazione. Se non è possibile elaborare i messaggi non in linea, verranno visualizzati nella directory seguente: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

Il registro ETL principale di Skype for business conterrà informazioni sull'elaborazione dei messaggi offline ed è la migliore risorsa per l'analisi o la risoluzione degli errori. 
  
> [!NOTE]
> È stato segnalato un problema a causa del quale i messaggi offline non sono stati inviati e la cartella ' bozze ' è stata riempita con i messaggi. Ciò si è verificato con le cassette postali locali di Exchange. Il problema è stato risolto in tutti i canali di C2R a 6/14/2016.  
