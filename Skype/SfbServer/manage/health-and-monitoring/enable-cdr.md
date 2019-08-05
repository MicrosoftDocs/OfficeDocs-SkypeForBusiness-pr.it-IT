---
title: Abilitare la registrazione dei dettagli delle chiamate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Riepilogo: informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 64a6e7d8d0e633fb3ef4e440932226f1f6f9c11a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195689"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Abilitare la registrazione dei dettagli delle chiamate in Skype for Business Server

**Riepilogo:** Informazioni su come abilitare i record di registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.

Registrazione dettagli chiamata (CDR) registra l'uso e le informazioni di diagnostica sulle attività peer-to-peer, tra cui messaggistica istanza, chiamate VoIP (Voice over Internet Protocol), condivisione di applicazioni, trasferimento di file e riunioni. I dati sull'utilizzo possono essere usati per calcolare il ritorno sugli investimenti (ROI) e i dati di diagnostica possono essere usati per risolvere le attività e le riunioni peer-to-peer.

Usare la procedura seguente per abilitare CDR per l'intera organizzazione o per ogni sito dell'organizzazione.

> [!NOTE]
> Per abilitare CDR è necessario configurare il monitoraggio e un database di monitoraggio. Per informazioni dettagliate, vedere [distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Per abilitare CDR con il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.

4. Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **azione**e quindi su **Abilita CDR**.

    > [!NOTE]
    > CDR è abilitato per impostazione predefinita.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Attivazione di CDR tramite i cmdlet di Windows PowerShell

È possibile abilitare CDR usando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Per abilitare CDR per una singola posizione

 Per disabilitare CDR, imposta il parametro EnableCDR su true ($True).

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Per disabilitare CDR per una singola posizione

 Per disabilitare CDR, imposta il parametro EnableCDR su false ($False). La disattivazione di CDR non disinstalla il monitoraggio. Sospende la raccolta e lo spazio di archiviazione dei dati CDR.

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Per usare un singolo comando per abilitare CDR in più posizioni

 Questo comando consente a CDR di usare tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Vedere anche

[Pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
