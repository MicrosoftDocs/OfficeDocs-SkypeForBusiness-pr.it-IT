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
ms.localizationpriority: medium
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Riepilogo: informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: cc9b3d4f19a4598638093d92733a0917fca7c2c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622368"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Abilitare la registrazione dettagli chiamata in Skype for Business Server

**Riepilogo:** Informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.

La funzionalità di registrazione dettagli chiamata (CDR) registra le informazioni di utilizzo e di diagnostica per le attività peer-to-peer, tra cui la messaggistica istantanea, le chiamate VoIP (Voice over Internet Protocol), la condivisione applicazioni, il trasferimento file e le riunioni. I dati di utilizzo possono essere utilizzati per calcolare il rendimento dell'investimento, mentre i dati di diagnostica possono aiutare a risolvere problemi relativi alle attività peer-to-peer e alle riunioni.

Utilizzare la procedura seguente per abilitare la registrazione dettagli chiamata per l'intera organizzazione o per ogni sito dell'organizzazione.

> [!NOTE]
> Per abilitare la registrazione dettagli chiamata, è necessario configurare il monitoraggio e un database di monitoraggio. Per informazioni dettagliate, vedere [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Per abilitare la registrazione cdR con Skype for Business Server pannello di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.

4. Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, su **Azione** e quindi su **Abilita registrazione dettagli chiamata**.

    > [!NOTE]
    > La funzionalità di registrazione dettagli chiamata è abilitata per impostazione predefinita.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Abilitazione della registrazione cdR tramite Windows PowerShell cmdlet

È possibile abilitare la registrazione cdR utilizzando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Per abilitare la funzionalità CR per una sola postazione

 Per abilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Per disabilitare la funzionalità CDR per una sola postazione

 Per disabilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su False ($False). La disabilitazione della registrazione cdR non consente di disinstallare il monitoraggio. Sospende la raccolta e l'archiviazione dei dati cdR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Per abilitare la funzionalità CDR in più postazioni con un solo comando

 Questo comando abilita la funzionalità CDR per tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Vedere anche

[Pianificazione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Distribuzione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)