---
title: Aggiornare il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiornare la gestione delle statistiche per Skype for Business Server.'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821766"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aggiornare il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiornare la gestione delle statistiche per Skype for Business Server.
  
In questo argomento viene descritto come eseguire l'aggiornamento di un'installazione esistente di statistiche Manager per Skype for Business Server, un potente strumento che consente di visualizzare i dati di integrità e prestazioni di Skype for Business Server in tempo reale. È possibile eseguire il polling dei dati delle prestazioni tra centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione delle statistiche. 
  
Per ulteriori informazioni su Gestione statistiche e sulle nuove funzionalità della versione 2,0, vedere [Plan for Statistics Manager for Skype for Business Server](plan.md) e [deploy Statistics Manager for Skype for Business Server](deploy.md).
  
Per l'aggiornamento sono disponibili due metodi:
  
- **Aggiornamento automatico.** Questo metodo utilizza uno script automatizzato. È il metodo più semplice e dovrebbe essere applicabile a tutti gli scenari di aggiornamento.
    
- **Aggiornamento manuale.** Questo metodo viene fornito come piano di backup nel caso insolito che l'aggiornamento automatico ha esito negativo.
    
## <a name="prerequisites"></a>Prerequisiti

Prima di eseguire l'aggiornamento, verificare di disporre delle informazioni seguenti:
  
- Identificazione personale del certificato del listener attivo
    
- Password del servizio listener (immessa all'installazione del listener e di ogni agente)
    
- Configurazione del certificato SSL per il sito Web
    
## <a name="automated-upgrade"></a>Aggiornamento automatico

Lo script raccoglierà le informazioni aggiornate sul certificato e la password del listener, disinstallerà la versione precedente del prodotto e quindi installerà la nuova versione del prodotto. L'istanza di ReDim installata nel server non verrà toccata, in modo che tutti i dati memorizzati nella cache vengano mantenuti tramite il processo di aggiornamento.
  
1. Inserire i file MSI per la nuova versione dell'agente, del listener e del sito Web insieme allo script Update-StatsMan.ps1 in una singola cartella nel computer listener.
    
2. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente listener:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La password del servizio di gestione delle statistiche verrà visualizzata in testo non crittografato sulla riga di comando quando viene passata al programma di installazione. Assicurarsi di schermare il monitor in base alle esigenze. 
  
1. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
2. Se il servizio listener è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consentire la chiusura dell'applicazione (il servizio listener di gestione delle statistiche verrà interrotto).
    
3. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato sono già popolate. In caso contrario, aggiungere i valori salvati prima di continuare.
    
4. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente del sito Web:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
6. Se il servizio agente è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consenti chiusura dell'applicazione (il servizio agente di statistica verrà interrotto).
    
7. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato sono già popolate. In caso contrario, aggiungere i valori salvati prima di continuare.
    
8. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente agente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
10. Continuare il processo di installazione. Si noti che la porta del sito Web è prepopolata. In caso contrario, aggiungere il valore salvato prima di continuare.
    
11. Verificare che il sito Web funzioni come previsto utilizzando il browser.
    
> [!NOTE]
> L'aggiornamento dell'agente può essere utilizzato con l'opzione-noprompt. In questo modo il processo di disinstallazione/installazione verrà eseguito in modalità invisibile all'utente, consentendo agli strumenti come PSExec di eseguire l'aggiornamento in remoto su un numero elevato di server. 
  
### <a name="manual-upgrade"></a>Aggiornamento manuale

Se, per qualche motivo, l'aggiornamento automatico ha esito negativo, è sempre possibile eseguire un aggiornamento manuale come indicato di seguito:
  
1. Nel computer listener disinstallare il listener, il sito Web e l'agente (se è stato installato nel server) tramite il pannello di controllo programmi e funzionalità. 
    
    > [!NOTE]
    >  Mantenere le redini installate in modo che i dati nella cache vengano quindi mantenuti tramite il processo di aggiornamento.
  
2. Installare le nuove versioni dei componenti, inclusi i valori salvati sopra quando richiesto. Per ulteriori informazioni sull'installazione dei componenti, vedere [deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Fixed"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
