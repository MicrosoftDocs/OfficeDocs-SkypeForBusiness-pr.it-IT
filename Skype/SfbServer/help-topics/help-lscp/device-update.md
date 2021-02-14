---
title: Aggiornamento dispositivi
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti. Per ottenere il set più recente di regole di aggiornamento dei dispositivi, accedere alla pagina Guida e supporto tecnico del sito Web Microsoft e cercarePhone Edition.Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet Import-CsDeviceUpdate per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere Import-CsDeviceUpdate.
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811056"
---
# <a name="device-update"></a>Aggiornamento dispositivi

Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti. Per ottenere il set più recente di regole di aggiornamento dei dispositivi, aprire la pagina del supporto tecnico del sito Web Microsoft e cercare "Phone Edition". Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer dove devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet **Import-CsDeviceUpdate** per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, [vedere Import-CsDeviceUpdate.](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

Dopo aver importato le regole di aggiornamento  dei dispositivi, puoi usare la pagina Aggiornamento dispositivi per visualizzare e gestire queste regole per i dispositivi dell'organizzazione.

> [!TIP]
> È possibile verificare gli aggiornamenti del firmware e successivamente renderli disponibili per tutti i dispositivi pertinenti in uso nell'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Aggiornamento dispositivi** è possibile eseguire le attività seguenti:

- Approvare aggiornamenti dei dispositivi nell'elenco.

- Annullare o ripristinare aggiornamenti dei dispositivi in sospeso.

- Eliminare aggiornamenti dei dispositivi dall'elenco.

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Modifica** È possibile utilizzare questa opzione per eseguire le operazioni seguenti:

  - **Seleziona tutto** Questa opzione seleziona tutti gli aggiornamenti dei dispositivi nell'elenco.

  - **Elimina** Questa opzione elimina tutti gli aggiornamenti dei dispositivi selezionati.

- **Azione** È possibile selezionare uno o più aggiornamenti nell'elenco ed eseguire le operazioni seguenti:

  - **Annullare gli aggiornamenti in sospeso** Questa opzione impedisce la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Approva** Questa opzione consente di distribuire l'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Ripristino** Questa opzione consente di distribuire un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione

- **Aggiorna** Puoi aggiornare l'elenco per verificare lo stato di tutti gli aggiornamenti dei dispositivi.

Per informazioni dettagliate sul servizio Web Aggiornamento dispositivi, vedere [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) nella documentazione relativa alla pianificazione.
## <a name="see-also"></a>Vedere anche

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
