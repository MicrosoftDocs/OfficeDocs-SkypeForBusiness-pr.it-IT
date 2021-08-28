---
title: Modificare le impostazioni di qualità dell'esperienza in Skype for Business Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Riepilogo: informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.'
ms.openlocfilehash: 54cb02e17106d2eee61bca8c171f6b16985d0dbc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614086"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificare le impostazioni di qualità dell'esperienza in Skype for Business Server

**Riepilogo:** Informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.

Per impostazione predefinita, i dati relativi alla QoE (Quality of Experience) vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Dati QoE** per conservare i dati per un periodo superiore o inferiore. Se si disabilita la funzionalità QoE, verranno eliminati anche i dati acquisiti prima dell'abilitazione di questa funzionalità.

> [!NOTE]
> È consigliabile configurare la registrazione dettagli chiamata (CDR, Call Detail Recording) e QoE in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla home page dei rapporti di monitoraggio, include informazioni di registrazione dettagli chiamata e QoE. Se il periodo che precede l'eliminazione è diverso, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.

Nella procedura seguente viene descritto come configurare le impostazioni per l'eliminazione dei dati QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Per specificare la conservazione dei dati QoE tramite il Skype for Business Server di controllo

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.

4. Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5. Per abilitare l'eliminazione, selezionare **Abilita eliminazione dei dati QoE**.

6. In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere i dati QoE.

7. Fare clic su **Commit**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Specifica della conservazione QoE tramite Windows PowerShell cmdlet

È possibile creare le impostazioni di conservazione QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Per specificare il mantenimento dei dati QoE per una posizione specifica

- Questo comando consente di abilitare l'eliminazione dei dati QoE per il sito Redmond e di configurare il sito per mantenere i dati QoE per 20 giorni.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Per specificare il mantenimento dei dati QoE per più posizioni

- Questo comando consente di configurare il mantenimento dei dati QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Vedere anche

[Distribuzione del monitoraggio](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)