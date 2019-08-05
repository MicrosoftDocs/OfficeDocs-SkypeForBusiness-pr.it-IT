---
title: Modificare le impostazioni di qualità delle esperienze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Riepilogo: informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188783"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificare le impostazioni di qualità delle esperienze in Skype for Business Server

**Riepilogo:** Informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.

Per impostazione predefinita, i dati di qualità dell'esperienza (QoE) vengono eliminati dopo 60 giorni. Per mantenere i dati per un periodo di tempo più lungo o più breve, è possibile usare le impostazioni nella pagina di **dati qualità della prova** . Se si disattiva QoE, anche i dati acquisiti prima dell'abilitazione di QoE saranno soggetti all'eliminazione.

> [!NOTE]
> Devi configurare la registrazione dei dettagli delle chiamate (CDR) e QoE per mantenere i dati per lo stesso numero di giorni. Ogni chiamata nei report dettagli chiamata (CDRs), disponibile nella Home page dei report di monitoraggio, include informazioni CDR e QoE. Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate possono includere solo dati CDR, mentre altre possono includere solo dati QoE.

La procedura seguente descrive come configurare le impostazioni di eliminazione dei dati QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Per specificare la conservazione dei dati QoE usando il pannello di controllo di Skype for Business Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4. Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.

5. Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di QoE**.

6. In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i dati QoE.

7. Fare clic su **Commit**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Specifica della conservazione QoE usando i cmdlet di Windows PowerShell

È possibile creare impostazioni di conservazione QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Per specificare la conservazione QoE per una posizione specifica

- Questo comando consente l'eliminazione dei dati QoE per il sito Redmond e configura il sito per la gestione dei dati QoE per 20 giorni.

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Per specificare la conservazione QoE per più posizioni

- Questo comando configura la conservazione QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .

## <a name="see-also"></a>Vedere anche

[Distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
