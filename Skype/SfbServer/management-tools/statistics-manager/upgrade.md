---
title: Aggiornare il gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiornare Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: de88257b628256c47b68036852d82fb6715c043f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992503"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aggiornare il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiornare Statistics Manager per Skype for Business Server.
  
Questo argomento descrive come aggiornare un'installazione esistente di Statistics Manager per Skype for Business Server, un potente strumento che consente di visualizzare in tempo reale i dati relativi alla salute e alle prestazioni di Skype for Business Server. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione statistiche. 
  
Per altre informazioni su Gestione statistiche e sulle nuove funzionalità della versione 2,0, vedere [pianificare la gestione delle statistiche per Skype for Business Server](plan.md) e [distribuire Gestione statistiche per Skype for Business Server](deploy.md).
  
Esistono due metodi per l'aggiornamento:
  
- **Aggiornamento automatico.** Questo metodo usa uno script automatizzato. È il metodo più semplice e dovrebbe essere applicabile a tutti gli scenari di aggiornamento.
    
- **Aggiornamento manuale.** Questo metodo viene fornito come piano di backup nel caso insolito in cui l'aggiornamento automatico non riesce.
    
## <a name="prerequisites"></a>Prerequisiti

Prima di eseguire l'aggiornamento, assicurarsi di avere le informazioni seguenti:
  
- Identificazione personale del certificato del listener attivo
    
- Password del servizio listener (immessa durante l'installazione del listener e di ogni agente)
    
- Configurazione del certificato SSL per il sito Web
    
## <a name="automated-upgrade"></a>Aggiornamento automatico

Lo script raccoglierà le informazioni sul certificato corrente e la password del listener, disinstallerà la versione precedente del prodotto e quindi installerà la nuova versione del prodotto. L'istanza Redis installata nel server non verrà toccata, quindi tutti i dati archiviati nella cache verranno mantenuti tramite il processo di aggiornamento.
  
1. Posizionare i file MSI per la nuova versione dell'agente, del listener e del sito Web insieme allo script Update-StatsMan. ps1 in una singola cartella nel computer del listener.
    
2. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente listener:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La password del servizio di gestione statistiche verrà visualizzata in testo non crittografato nella riga di comando mentre viene passata al programma di installazione. Assicurarsi di proteggere il monitor in base alle esigenze. 
  
1. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
2. Se il servizio listener è in funzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consentire all'applicazione di chiudere (il servizio listener di gestione statistiche verrà interrotto).
    
3. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato vengono precompilate. In caso contrario, aggiungere i valori salvati prima di continuare.
    
4. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente sito Web:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
6. Se il servizio agente è in funzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consenti chiusura dell'applicazione (il servizio agente di statistiche verrà interrotto).
    
7. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato vengono precompilate. In caso contrario, aggiungere i valori salvati prima di continuare.
    
8. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente Agent:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto. Rispondere Sì.
    
10. Continuare il processo di installazione. Si noti che la porta del sito Web viene prepopolata. In caso contrario, Aggiungi il valore salvato prima di continuare.
    
11. Verificare che il sito Web funzioni come previsto tramite il browser.
    
> [!NOTE]
> L'aggiornamento dell'agente può essere usato con l'opzione-noprompt. Ciò consentirà l'esecuzione del processo di disinstallazione/installazione in modo invisibile all'utente, consentendo agli strumenti come PSExec di eseguire l'aggiornamento in remoto su un numero elevato di server. 
  
### <a name="manual-upgrade"></a>Aggiornamento manuale

Se per qualche motivo l'aggiornamento automatico non riesce, è sempre possibile eseguire un aggiornamento manuale nel modo seguente:
  
1. Nel computer listener disinstallare il listener, il sito Web e l'agente (se è stato installato nel server) tramite il pannello di controllo programmi e funzionalità. 
    
    > [!NOTE]
    >  Mantenere Redis installato in modo che i dati nella cache vengano mantenuti tramite il processo di aggiornamento.
  
2. Installare le nuove versioni dei componenti, inclusi i valori salvati sopra quando richiesto. Per altre informazioni sull'installazione di componenti, vedere [distribuire Gestione statistiche](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Per altre informazioni
<a name="BKMK_Fixed"> </a>

Per altre informazioni, vedere quanto segue:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
