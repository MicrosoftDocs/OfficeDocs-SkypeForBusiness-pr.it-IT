---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "La migrazione dell'applicazione Call Park include il provisioning del pool di Skype for Business Server 2019 con qualsiasi musica personalizzata su file in attesa caricati nell'installazione legacy, il ripristino delle impostazioni del livello di servizio e la destinazione di tutte le orbite di Call Park Pool di Skype for Business Server 2019. Se i file personalizzati per la musica in attesa sono stati configurati nel pool, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato per la musica in attesa di file da a un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica in attesa personalizzato caricato per Call Park. I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool. Per copiare i file audio da un file di pool in un archivio di file di Skype for Business Server 2019, usare il comando xcopy con i parametri seguenti:"
ms.openlocfilehash: 0435144fc647a08d8252f35d8449d1e7daa62d68
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991161"
---
# <a name="migrate-call-park-application-settings"></a>Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata

La migrazione dell'applicazione Call Park include il provisioning del pool di Skype for Business Server 2019 con tutti i file musicali personalizzati che sono stati caricati nell'installazione legacy, il ripristino delle impostazioni a livello di servizio e la destinazione di tutte le orbite di Call Park al pool di Skype for Business Server 2019. Se i file personalizzati per la musica in attesa sono stati configurati nel pool, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato per la musica in attesa di file in un'altra destinazione per mantenere una copia di backup separata di tutti i file di musica in attesa personalizzati caricati per Call Park. I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool. Per copiare i file audio da un file di pool in un archivio di file di Skype for Business Server 2019, usare il comando **xcopy** con i parametri seguenti: 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando tutti i file audio personalizzati sono stati copiati nel file Store di Skype for Business Server 2019, è necessario configurare le impostazioni dell'applicazione di Call Park del pool di Skype for Business Server 2019 e gli intervalli di orbita del parcheggio di chiamata associati al pool legacy devono essere riassegnati al pool di Skype for Business Server 2019.

Le impostazioni delle applicazioni di Call Park includono la soglia di timeout del prelievo, l'abilitazione o la disabilitazione della musica in attesa, i tentativi di ritiro massimo delle chiamate e la richiesta di timeout. Per eseguire il cmdlet **Set-CsCpsConfiguration** , è necessario gestire le impostazioni delle applicazioni di Call Park usando Skype for Business Server Management Shell. Non è possibile gestire le impostazioni delle applicazioni di Call Park usando il pannello di controllo di Skype for Business Server. 

## <a name="reconfigure-the-call-park-service-settings"></a>Riconfigurare le impostazioni del servizio di parcheggio delle chiamate

1. Dal server front-end di Skype for Business Server 2019 Aprire Skype for Business Server Management Shell.

2. Nella riga di comando digitare quanto segue:

    > [!NOTE]
    > Se le impostazioni delle applicazioni di Call Park di Skype for Business Server 2019 sono identiche alle impostazioni legacy, è possibile ignorare questo passaggio. Se le impostazioni delle applicazioni di Call Park sono diverse per Skype for Business Server 2019 e per gli ambienti Legacy, usare il cmdlet seguente come modello per aggiornare tali modifiche. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool legacy al pool di Skype for Business Server 2019, è possibile usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Riassegnare tutti gli intervalli orbit di Call Park tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Nel riquadro sinistro selezionare **funzionalità vocali**.

3. Selezionare la scheda **parcheggio chiamate** . 

4. Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool legacy, modificare l'impostazione **FQDN di server di destinazione** e selezionare il pool di Skype for Business Server 2019 in cui verranno elaborate le richieste di parcheggio delle chiamate. 

5. Selezionare **conferma** per salvare le modifiche. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Riassegnare tutti gli intervalli orbit di Call Park con Skype for Business Server Management Shell

1. Aprire Skype for Business Server Management Shell.

2. Nella riga di comando digitare quanto segue:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Questo cmdlet elenca tutti gli intervalli di orbit del parcheggio delle chiamate nella distribuzione. Tutte le orbite del parcheggio delle chiamate con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool legacy devono essere riassegnate. 

    Per riassegnare gli intervalli di orbit del parcheggio di chiamata legacy al pool di Skype for Business Server 2019, nella riga di comando digitare quanto segue:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Dopo aver riassegnato tutti gli intervalli orbit di Call Park al pool di Skype for Business Server 2019, il processo di migrazione per l'applicazione di Call Park verrà completato e il pool di Skype for Business Server 2019 gestirà tutte le richieste future di Call Park.


