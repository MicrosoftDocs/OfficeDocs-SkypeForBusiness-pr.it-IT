---
title: Abilitare la qualità dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: "Riepilogo: informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server."
ms.openlocfilehash: 0a05266ed88b9d476ca787f1d32b91727e90475c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992936"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Abilitare la qualità dell'esperienza in Skype for Business Server

**Riepilogo:** informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server.

La qualità dell'esperienza (QoE) registra i dati numerici che indicano la qualità del supporto e le informazioni sui partecipanti, i nomi di dispositivo, i driver, gli indirizzi IP e i tipi di endpoint coinvolti in chiamate e sessioni. Per informazioni dettagliate, vedere [pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) nella documentazione relativa alla pianificazione.

Usare la procedura seguente per abilitare QoE per l'intera organizzazione o per ogni sito dell'organizzazione.

> [!NOTE]
> Per abilitare QoE, è prima necessario configurare il monitoraggio e un database back-end di monitoraggio. Per informazioni dettagliate, vedere [distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Per abilitare QoE usando il pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4. Nella pagina **qualità di dati esperienza** fare clic sulla raccolta appropriata dalla tabella, fare clic su **azione**e quindi su **Abilita QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Abilitazione di QoE usando i cmdlet di Windows PowerShell

Puoi abilitare QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Per abilitare QoE per una singola posizione

 Per abilitare QoE, imposta il parametro EnableQoE su true ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Per disabilitare QoE per una singola posizione

 Per disabilitare QoE, imposta il parametro EnableQoE su false ($False). Questo non disinstalla il monitoraggio. Sospende la raccolta e lo spazio di archiviazione dei dati QoE.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Per usare un singolo comando per abilitare QoE in più posizioni

 Questo comando abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Vedere anche

[Pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

