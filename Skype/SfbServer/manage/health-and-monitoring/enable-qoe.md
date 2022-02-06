---
title: Abilitare la qualità dell'esperienza in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Riepilogo: informazioni su come abilitare la qualità dell''esperienza (QoE) in Skype for Business Server.'
---

# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Abilitare la qualità dell'esperienza in Skype for Business Server

**Riepilogo:** informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server.

La qualità percepita dagli utenti (QoE, Quality of Experience) registra dati numerici che indicano la qualità multimediale e le informazioni sui partecipanti, i nomi di dispositivi, i driver, gli indirizzi IP e i tipi di endpoint coinvolti nelle chiamate e nelle sessioni. Per informazioni dettagliate, vedere [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) nella documentazione relativa alla pianificazione.

Utilizzare la procedura che segue per abilitare QoE per l'intera organizzazione o per ogni suo sito.

> [!NOTE]
> Per abilitare QoE, è innanzitutto necessario configurare il monitoraggio e un database back-end Monitoring Server. Per informazioni dettagliate, vedere [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Per abilitare QoE tramite il Pannello Skype for Business Server di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.

2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.

4. Nella pagina **Dati QoE** fare clic sulla raccolta appropriata nella tabella, su **Azione** e quindi su **Abilita QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Abilitazione di QoE tramite Windows PowerShell cmdlet

È possibile abilitare QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota [di PowerShell per Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Il processo è lo stesso in Skype for Business Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Per abilitare QoE per una singola posizione

 Per abilitare QoE, impostare il parametro EnableQoE su True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Per disabilitare QoE per una singola posizione

 Per disabilitare QoE, impostare il parametro EnableQoE su False ($False). Questa operazione non comporta la disinstallazione del monitoraggio. Determina solo la sospensione della raccolta e dell'archiviazione di dati QoE.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Per utilizzare un singolo comando per abilitare QoE in più posizioni

 Il comando seguente abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Per informazioni dettagliate, [vedere Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Vedere anche

[Pianificazione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Distribuzione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)