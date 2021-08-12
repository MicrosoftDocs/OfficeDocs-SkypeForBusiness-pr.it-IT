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
description: "La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool di Skype for Business Server 2019 con tutti i file di musica di attesa personalizzati caricati nell'installazione legacy, il ripristino delle impostazioni del livello di servizio e il retargeting di tutti i orbit del parcheggio di chiamata al pool di Skype for Business Server 2019. Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool Skype for Business Server 2019. È inoltre consigliabile eseguire il backup di tutti i file di musica di attesa personalizzati di Parcheggio di chiamata da un'altra destinazione per conservare una copia di backup separata di tutti i file di musica di attesa personalizzati caricati per parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool Skype for Business Server 2019, utilizzare il comando Xcopy con i parametri seguenti:"
ms.openlocfilehash: f83e1095361ddd272a35bf9100171c0d06caf003dfae84f19c01b2aa53de7977
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312324"
---
# <a name="migrate-call-park-application-settings"></a>Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata

La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool di Skype for Business Server 2019 con tutti i file di musica di attesa personalizzati caricati nell'installazione legacy, il ripristino delle impostazioni a livello di servizio e la nuova destinazione di tutti i orbit del parcheggio di chiamata al pool di Skype for Business Server 2019. Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool Skype for Business Server 2019. Inoltre, è consigliabile eseguire il backup di tutti i file di musica di attesa personalizzati di Parcheggio di chiamata in un'altra destinazione per conservare una copia di backup separata di tutti i file di musica di attesa personalizzati che sono stati caricati per parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool Skype for Business Server 2019, utilizzare il comando **Xcopy** con i parametri seguenti: 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

Quando tutti i file audio personalizzati sono stati copiati nell'archivio file di Skype for Business Server 2019, le impostazioni dell'applicazione Parcheggio di chiamata del pool di Skype for Business Server 2019 devono essere configurate e gli intervalli di orbit del parcheggio di chiamata associati al pool legacy devono essere riassegnati al pool di Skype for Business Server 2019.

Le impostazioni dell'applicazione Parcheggio di chiamata includono la soglia di timeout di prelievo, l'abilitazione o la disabilitazione della musica in attesa, il numero massimo di tentativi di prelievo delle chiamate e la richiesta di timeout. È necessario gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Skype for Business Server Management Shell per eseguire il cmdlet **Set-CsCpsConfiguration.** Non è possibile gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Skype for Business Server pannello di controllo. 

## <a name="reconfigure-the-call-park-service-settings"></a>Riconfigurare le impostazioni del servizio Parcheggio chiamata

1. Dal Front End Server Skype for Business Server 2019 aprire Skype for Business Server Management Shell.

2. Nella riga di comando digitare quanto segue:

    > [!NOTE]
    > Se le impostazioni Skype for Business Server'applicazione parcheggio di chiamata 2019 sono identiche alle impostazioni legacy, è possibile ignorare questo passaggio. Se le impostazioni dell'applicazione Parcheggio di chiamata sono diverse Skype for Business Server 2019 e gli ambienti legacy, utilizzare il cmdlet seguente come modello per aggiornare tali modifiche. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool legacy al pool di Skype for Business Server 2019, è possibile utilizzare il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>Riassegnare tutti gli intervalli orbit del parcheggio di chiamata Skype for Business Server Pannello di controllo

1. Aprire Skype for Business Server Pannello di controllo.

2. Nel riquadro sinistro, selezionare **Funzionalità vocali**.

3. Selezionare la scheda **Parcheggio chiamata**. 

4. Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool legacy, modificare l'impostazione FQDN del **server** di destinazione e selezionare il pool di Skype for Business Server 2019 che eelaborare le richieste di parcheggio di chiamata. 

5. Selezionare **Commit** per salvare le modifiche. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>Riassegnare tutti gli intervalli orbit del parcheggio di chiamata tramite Skype for Business Server Management Shell

1. Aprire Skype for Business Server Management Shell.

2. Nella riga di comando digitare quanto segue:

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    Questo cmdlet elenca tutti gli intervalli di codici orbit di Parcheggio chiamata nella distribuzione. Tutti i orbit del parcheggio di chiamata con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool legacy devono essere riassegnati. 

    Per riassegnare gli intervalli di orbit del parcheggio di chiamata legacy al pool Skype for Business Server 2019, nella riga di comando digitare quanto segue:

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

Dopo aver riassegnare tutti gli intervalli di orbit del parcheggio di chiamata al pool di Skype for Business Server 2019, il processo di migrazione per l'applicazione Parcheggio di chiamata verrà completato e il pool di Skype for Business Server 2019 gestirà tutte le richieste di parcheggio di chiamata future.


