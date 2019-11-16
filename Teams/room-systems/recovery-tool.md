---
title: Usare lo strumento di ripristino di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.
ms.openlocfilehash: bc35dc744dac5f04d537f023e790bc89c2c649d0
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675350"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usare lo strumento di ripristino di Microsoft teams rooms
 
Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato. Si utilizzerebbe questo strumento quando la console Microsoft teams Rooms Mostra un errore "configurazione di sistema non aggiornata".
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Prerequisiti

Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.

Potrebbe essere necessario installare anche [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Verificare la versione di Windows 

1. Accedere a un account di amministratore accedendo a **impostazioni> impostazione di Windows> l'accesso di amministratore** dal dispositivo Microsoft teams rooms. Questa opzione consente di accedere alla schermata di accesso.
2. Accedere a un account di amministratore, `admin` con la password `sfb`dell'account di amministratore predefinito.
3. Fare clic sul menu Start e digitare `winver.exe` nella casella di ricerca e fare clic su **Esegui comando* nel risultato.
4. Prendere nota del numero dopo ' versione ' nella seconda riga del riquadro delle informazioni.

>[!NOTE]
>Se la versione visualizzata è 1607 o precedente, seguire i passaggi descritti in <a href="#Windows-up">aggiornare le finestre prima</a> di eseguire i passaggi di ripristino prima di procedere con i passaggi di <a href="#Perform">ripristino</a> . Se la versione visualizzata è maggiore di 1607, seguire solo la procedura descritta in <a href="#Perform">eseguire un ripristino</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Aggiornare Windows prima del ripristino (se necessario)

1. Durante l'accesso come utente di amministratore, avviare un prompt di PowerShell con privilegi elevati.
2. Eseguire il comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Eseguire Windows Update e installare l'aggiornamento per Windows 1709.
4. Dopo che l'aggiornamento a 1709 è stato completato, accedere all'account di amministratore e installare [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). L'aggiornamento può essere eseguito dal collegamento o tramite Windows Update.
5. Come passaggio facoltativo, installare gli eventuali aggiornamenti aggiuntivi disponibili in Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Eseguire un ripristino

1. Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2. Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere `RecoveryTool.ps1` al file, incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms. Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.
3. Eseguire il comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.
4. Quando richiesto dall'opzione `1:"Repair System"`di selezione dello script.
5. Al termine, riavviare il dispositivo Microsoft teams rooms. Verrà riavviato automaticamente e verrà recuperato completamente la seconda volta.



<a name="See"> </a>  
## <a name="see-also"></a>Vedere anche
 
[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)
