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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiornare Gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: caa2a5f7576a046c990315b638e618a379dd039e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611985"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>Aggiornare il gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come aggiornare Gestione statistiche per Skype for Business Server.
  
In questo argomento viene descritto come aggiornare un'installazione esistente di Gestione statistiche per Skype for Business Server, uno strumento potente che consente di visualizzare Skype for Business Server dati sull'integrità e sulle prestazioni in tempo reale. È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web Gestione statistiche. 
  
Per ulteriori informazioni su Gestione statistiche e sulle nuove funzionalità della versione 2.0, vedere [Plan for Statistics Manager for Skype for Business Server](plan.md) e Deploy Statistics Manager for [Skype for Business Server](deploy.md).
  
Esistono due metodi per l'aggiornamento:
  
- **Aggiornamento automatico.** Questo metodo usa uno script automatico. È il metodo più semplice e deve essere applicabile a tutti gli scenari di aggiornamento.
    
- **Aggiornamento manuale.** Questo metodo viene fornito come piano di backup nel caso in cui l'aggiornamento automatico non riesca.
    
## <a name="prerequisites"></a>Prerequisiti

Prima di eseguire l'aggiornamento, assicurarsi di disporre delle informazioni seguenti:
  
- Identificazione personale certificato listener attivo
    
- Password del servizio listener (immessa durante l'installazione del listener e di ogni agente)
    
- Configurazione del certificato SSL per il sito Web
    
## <a name="automated-upgrade"></a>Aggiornamento automatico

Lo script raccoglierà le informazioni sul certificato corrente e la password del listener, disinstalla la versione precedente del prodotto e quindi installerà la nuova versione del prodotto. L'istanza di Redis installata nel server non verrà toccata, quindi tutti i dati archiviati nella cache verranno conservati tramite il processo di aggiornamento.
  
1. Inserire i file MSI per la nuova versione dell'agente, del listener e del sito Web insieme allo script di Update-StatsMan.ps1 in una singola cartella nel computer listener.
    
2. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente Listener:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> La password del servizio Gestione statistiche verrà visualizzata in testo non crittografato nella riga di comando quando viene passata al programma di installazione. Assicurati di proteggere il monitor in base alle esigenze. 
  
1. Durante l'esecuzione dello script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto. Risposta Sì.
    
2. Se il servizio Listener è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consentire la chiusura dell'applicazione (il servizio Listener di Gestione statistiche verrà arrestato).
    
3. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato sono precompilato. In caso contrario, aggiungere i valori salvati prima di continuare.
    
4. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente Sito Web:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. Durante l'esecuzione dello script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto. Risposta Sì.
    
6. Se il servizio Agente è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare. Consentire la chiusura dell'applicazione (il servizio Agente StatsMan verrà arrestato).
    
7. Continuare il processo di installazione. Si noti che la password del servizio e l'identificazione personale del certificato sono precompilato. In caso contrario, aggiungere i valori salvati prima di continuare.
    
8. Aprire una finestra di PowerShell amministrativa. Aggiornare il componente Agente:
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. Durante l'esecuzione dello script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto. Risposta Sì.
    
10. Continuare il processo di installazione. Si noti che la porta del sito Web è precompilato. In caso contrario, aggiungere il valore salvato prima di continuare.
    
11. Verificare che il sito Web funzioni come previsto utilizzando il browser.
    
> [!NOTE]
> L'aggiornamento dell'agente può essere utilizzato con l'opzione -NoPrompt. In questo modo il processo di disinstallazione/installazione verrà eseguito in modo invisibile all'utente, consentendo a strumenti come PSExec di eseguire l'aggiornamento in remoto su un numero elevato di server. 
  
### <a name="manual-upgrade"></a>Aggiornamento manuale

Se per qualche motivo, l'aggiornamento automatico ha esito negativo, è sempre possibile eseguire un aggiornamento manuale nel modo seguente:
  
1. Nel computer listener disinstallare listener, sito Web e agente (se installato nel server) tramite il Pannello di controllo Programmi e funzionalità. 
    
    > [!NOTE]
    >  Mantenere Redis installato in modo che i dati nella cache siano mantenuti attraverso il processo di aggiornamento.
  
2. Installare le nuove versioni dei componenti, inclusi i valori salvati in precedenza quando richiesto. Per ulteriori informazioni sull'installazione dei componenti, vedere [Deploy Statistics Manager](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Fixed"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server](troubleshoot.md)
