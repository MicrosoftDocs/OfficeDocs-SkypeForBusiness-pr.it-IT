---
title: Aggiornamento dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti. Per ottenere l'ultimo set di regole di aggiornamento dei dispositivi, passare alla pagina della guida e del supporto nel sito Web Microsoft e cercare forPhone Edition. scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet Import-CsDeviceUpdate per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere Import-CsDeviceUpdate.
ms.openlocfilehash: d82010d45ae550c49529720496fc202abb2f6e4c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705141"
---
# <a name="device-update"></a>Aggiornamento del dispositivo

Microsoft rilascia periodicamente un nuovo set di aggiornamenti del firmware del dispositivo per Skype for Business Phone Edition, che è possibile importare nei server e distribuire agli utenti. Per ottenere il set più recente di regole di aggiornamento dei dispositivi, aprire la pagina del supporto tecnico del sito Web Microsoft e cercare "Phone Edition". Scaricare il pacchetto di aggiornamento più recente ed estrarre i file in una cartella nel computer dove devono essere caricati gli aggiornamenti. Dopo aver estratto i file, è possibile usare il cmdlet **Import-CsDeviceUpdate** per importare le regole di aggiornamento dei dispositivi presenti nel file CAB estratto, che sarà denominato UCUpdates.cab. Per informazioni dettagliate, vedere [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Dopo aver importato le regole di aggiornamento del dispositivo, è possibile usare la pagina di **aggiornamento del dispositivo** per visualizzare e gestire queste regole per i dispositivi dell'organizzazione.

> [!TIP]
> È possibile verificare gli aggiornamenti del firmware e successivamente renderli disponibili per tutti i dispositivi pertinenti in uso nell'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Aggiornamento dispositivi** è possibile eseguire le attività seguenti:

- Approvare aggiornamenti dei dispositivi nell'elenco.

- Annullare o ripristinare aggiornamenti dei dispositivi in sospeso.

- Eliminare aggiornamenti dei dispositivi dall'elenco.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Modifica** Puoi usare questa opzione per eseguire le operazioni seguenti:

  - **Seleziona tutto** Questa opzione consente di selezionare tutti gli aggiornamenti dei dispositivi nell'elenco.

  - **Eliminare** Questa opzione consente di eliminare tutti gli aggiornamenti del dispositivo selezionati.

- **Azione** È possibile selezionare uno o più aggiornamenti nell'elenco e quindi eseguire le operazioni seguenti:

  - **Annullare gli aggiornamenti in sospeso** Questa opzione impedisce la distribuzione dell'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Approva** Questa opzione consente di distribuire l'aggiornamento selezionato nei dispositivi dell'organizzazione.

  - **Ripristinare** Questa opzione consente di distribuire un aggiornamento approvato in precedenza ai dispositivi dell'organizzazione

- **Aggiornare** Puoi aggiornare l'elenco per verificare lo stato di tutti gli aggiornamenti del dispositivo.

Per informazioni dettagliate sul servizio Web Aggiornamento dispositivi, vedere [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) nella documentazione relativa alla pianificazione.
## <a name="see-also"></a>Vedere anche

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
