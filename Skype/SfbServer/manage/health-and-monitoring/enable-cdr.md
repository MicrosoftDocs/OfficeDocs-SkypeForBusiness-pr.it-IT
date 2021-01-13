---
title: Abilitare la registrazione dettagli chiamata in Skype for Business Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Riepilogo: informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816886"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Abilitare la registrazione dettagli chiamata in Skype for Business Server

**Riepilogo:** Informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.

La funzionalità di registrazione dettagli chiamata (CDR) registra le informazioni di utilizzo e di diagnostica per le attività peer-to-peer, tra cui la messaggistica istantanea, le chiamate VoIP (Voice over Internet Protocol), la condivisione applicazioni, il trasferimento file e le riunioni. I dati di utilizzo possono essere utilizzati per calcolare il rendimento dell'investimento, mentre i dati di diagnostica possono aiutare a risolvere problemi relativi alle attività peer-to-peer e alle riunioni.

Utilizzare la procedura seguente per abilitare la registrazione dettagli chiamata per l'intera organizzazione o per ogni sito dell'organizzazione.

> [!NOTE]
> Per abilitare la registrazione dettagli chiamata, è necessario configurare il monitoraggio e un database di monitoraggio. Per informazioni dettagliate, vedere [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Per abilitare CDR con il pannello di controllo di Skype for Business Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.

2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.

3. Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.

4. Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, su **Azione** e quindi su **Abilita registrazione dettagli chiamata**.

    > [!NOTE]
    > La funzionalità di registrazione dettagli chiamata è abilitata per impostazione predefinita.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Abilitazione di CDR tramite i cmdlet di Windows PowerShell

È possibile abilitare la funzionalità registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** . È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Per abilitare la funzionalità CR per una sola postazione

 Per abilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Per disabilitare la funzionalità CDR per una sola postazione

 Per disabilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su False ($False). La disattivazione di CDR non disinstalla il monitoraggio. Interrompe la raccolta e l'archiviazione dei dati di registrazione dettagli chiamata.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Per abilitare la funzionalità CDR in più postazioni con un solo comando

 Questo comando abilita la funzionalità CDR per tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Vedere anche

[Pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
