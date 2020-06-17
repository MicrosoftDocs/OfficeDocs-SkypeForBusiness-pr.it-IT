---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool di Skype for Business Server 2019 con tutti i file musicali personalizzati che sono stati caricati nell'installazione legacy, ripristinando le impostazioni a livello di servizio e reindirizzando tutte le orbite del parcheggio di chiamata al pool di Skype for Business Server 2019. Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato file musicali in attesa da un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica di attesa personalizzato che sono stati caricati per il parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool in un archivio file di Skype for Business Server 2019, utilizzare il comando xcopy con i seguenti parametri:"
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752818"
---
# <a name="migrate-call-park-application-settings"></a>Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata

La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool Skype for Business Server 2019 con tutti i file musicali personalizzati che sono stati caricati nell'installazione legacy, il ripristino delle impostazioni a livello di servizio e la riassegnazione di tutte le orbite del parcheggio di chiamata al pool di Skype for Business Server 2019. Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. Inoltre, si consiglia di eseguire il backup di qualsiasi parcheggio di chiamata personalizzato file di musica di attesa in un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica di attesa personalizzato che sono stati caricati per il parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool in un archivio file di Skype for Business Server 2019, utilizzare il comando **xcopy** con i seguenti parametri: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando tutti i file audio personalizzati sono stati copiati nell'archivio file di Skype for Business Server 2019, è necessario configurare le impostazioni dell'applicazione Parcheggio di chiamata del pool di Skype for Business Server 2019 e gli intervalli di orbit del parcheggio di chiamata associati al pool legacy devono essere riassegnati al pool di Skype for Business Server 2019.

Le impostazioni dell'applicazione Parcheggio di chiamata includono la soglia di timeout del prelievo, abilitando o disabilitando la musica in attesa, il numero massimo di tentativi di prelievo delle chiamate e la richiesta di timeout. È necessario gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Skype for Business Server Management Shell per eseguire il cmdlet **Set-CsCpsConfiguration** . Non è possibile gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando il pannello di controllo di Skype for Business Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Riconfigurare le impostazioni del servizio Parcheggio chiamata

1. Dal server front end di Skype for Business Server 2019, aprire la shell di gestione di Skype for Business Server.

2. Nella riga di comando digitare quanto segue:

    > [!NOTE]
    > Se le impostazioni dell'applicazione Parcheggio di chiamata di Skype for Business Server 2019 sono identiche alle impostazioni legacy, è possibile ignorare questo passaggio. Se le impostazioni dell'applicazione Parcheggio di chiamata sono diverse per gli ambienti Skype for Business Server 2019 e legacy, utilizzare il cmdlet riportato di seguito come modello per aggiornare tali modifiche. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool legacy al pool di Skype for Business Server 2019, è possibile utilizzare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Nel riquadro sinistro, selezionare **Funzionalità vocali**.

3. Selezionare la scheda **Parcheggio chiamata**. 

4. Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool legacy, modificare l'impostazione **FQDN del server di destinazione** e selezionare il pool di Skype for Business Server 2019 che elaborerà le richieste del parcheggio di chiamata. 

5. Selezionare **Commit** per salvare le modifiche. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite Skype for Business Server Management Shell

1. Aprire Skype for Business Server Management Shell.

2. Nella riga di comando digitare quanto segue:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Questo cmdlet elenca tutti gli intervalli di codici orbit di Parcheggio chiamata nella distribuzione. Tutte le orbite del parcheggio di chiamata con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool legacy devono essere riassegnate. 

    Per riassegnare gli intervalli di orbit del parcheggio di chiamata legacy al pool di Skype for Business Server 2019, nella riga di comando digitare quanto segue:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Dopo aver riassegnato tutti gli intervalli di orbit del parcheggio di chiamata al pool di Skype for Business Server 2019, il processo di migrazione per l'applicazione Parcheggio di chiamata verrà completato e il pool di Skype for Business Server 2019 gestirà tutte le richieste future del parcheggio di chiamata.


