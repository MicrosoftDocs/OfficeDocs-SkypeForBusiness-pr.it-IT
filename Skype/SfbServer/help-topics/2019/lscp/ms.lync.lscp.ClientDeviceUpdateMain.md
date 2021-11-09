---
title: Aggiornamento dispositivi
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Telefono Edition, che puoi importare nei server e distribuire agli utenti. Per ottenere il set più recente di regole di aggiornamento dei dispositivi, accedere alla pagina Guida e supporto tecnico del sito Web Microsoft e cercarePhone Edition.Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella del computer in cui devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet Import-CsDeviceUpdate per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere Import-CsDeviceUpdate.
ms.openlocfilehash: 19815f81a3a6fe9a3c35b1528b5eefb066003481
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858603"
---
# <a name="device-update"></a>Aggiornamento dispositivi

Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Telefono Edition, che puoi importare nei server e distribuire agli utenti. Per ottenere il set più recente di regole di aggiornamento dei dispositivi, aprire la pagina del supporto tecnico del sito Web Microsoft e cercare "Phone Edition". Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer dove devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet **Import-CsDeviceUpdate** per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, [vedere Import-CsDeviceUpdate.](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

Dopo aver importato le regole di aggiornamento dei dispositivi, puoi usare la pagina **Aggiornamento** dispositivi per visualizzare e gestire queste regole per i dispositivi dell'organizzazione.

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

- **Azione** È possibile selezionare uno o più aggiornamenti nell'elenco ed eseguire le azioni seguenti:

  - **Annullare gli aggiornamenti in sospeso** Questa opzione impedisce la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Approva** Questa opzione consente di distribuire l'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Ripristino** Questa opzione consente di distribuire un aggiornamento approvato in precedenza nei dispositivi dell'organizzazione

- **Aggiorna** Puoi aggiornare l'elenco per verificare lo stato di tutti gli aggiornamenti dei dispositivi.

Per informazioni dettagliate sul servizio Web Aggiornamento dispositivi, vedere [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) nella documentazione relativa alla pianificazione.
## <a name="see-also"></a>Vedere anche

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)