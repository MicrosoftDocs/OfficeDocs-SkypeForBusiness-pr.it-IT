---
title: Configurazione dei log del dispositivo
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
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati di registro, le dimensioni del file di registro o il periodo di tempo in cui un file di registro viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base alle esigenze dell'organizzazione. Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.
ms.openlocfilehash: b20c7bb088f46491c99ada7c815b8c11d4bfe456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115284"
---
# <a name="device-log-configuration"></a>Configurazione dei log del dispositivo

Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati di registro, le dimensioni del file di registro o il periodo di tempo in cui un file di registro viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base alle esigenze dell'organizzazione. Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.

> [!NOTE]
> È inoltre possibile configurare un'ora del giorno in cui si desidera che il servizio Web Aggiornamento dispositivi elimini automaticamente i file di registro precedenti al numero di giorni in cui il servizio è stato configurato per mantenere i file di registro (per impostazione predefinita, si tratta di file di registro che hanno più di 10 giorni). Questa impostazione non può essere modificata utilizzando il Pannello di controllo di Skype for Business Server. È invece necessario utilizzare Skype for Business Server Management Shell. Per specificare l'ora del giorno in cui eliminare i file di registro scaduti, utilizzare il cmdlet **New-CsDeviceUpdateConfiguration** con il parametro -LogCleanUpTimeOfDay. Per informazioni dettagliate, [vedere New-CsDeviceUpdateConfiguration.](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)

> [!CAUTION]
> L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Configurazione log dispositivo** è possibile eseguire le attività seguenti:

- Aggiungere una configurazione dei log dispositivo a livello globale o per un sito o pool specifico.

- Modificare le opzioni per una configurazione dei log dispositivo esistente.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Nuovo** È possibile aggiungere una nuova configurazione del registro dei dispositivi con l'ambito seguente:

  - Globale

  - Sito

- **Modifica** È possibile modificare le opzioni di una configurazione del registro del dispositivo nell'elenco. Usando questa voce, è possibile scegliere tra le opzioni seguenti:

  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione del registro del dispositivo.

  - **Seleziona tutto** Questa opzione consente di selezionare tutta la configurazione del registro dei dispositivi nell'elenco.

  - **Elimina** Questa opzione consente di eliminare tutte le configurazioni del registro dei dispositivi selezionate.

- **Aggiorna** È possibile aggiornare l'elenco di configurazione dei log del dispositivo per verificare lo stato delle opzioni di tutte le configurazioni dei log dei dispositivi.

## <a name="see-also"></a>Vedere anche

[Modificare le impostazioni per i file di registro dell'attività di aggiornamento dei dispositivi](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)