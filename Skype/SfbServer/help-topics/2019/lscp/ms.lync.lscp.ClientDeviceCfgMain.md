---
title: Configurazione dei log del dispositivo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati del log, le dimensioni dei file di registro o il periodo di tempo in cui un file di registro viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione. Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.
ms.openlocfilehash: 118f2e6d90e9c3f7559a5e129c844ccdf1ea9bf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830336"
---
# <a name="device-log-configuration"></a>Configurazione dei log del dispositivo

Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è possibile impostare soglie per le dimensioni della cache dei dati del log, le dimensioni dei file di registro o il periodo di tempo in cui un file di registro viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione. Se non si desidera che il servizio Web di aggiornamenti dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.

> [!NOTE]
> È inoltre possibile configurare l'ora del giorno in cui si desidera che il servizio Web aggiornamento dispositivi elimini automaticamente i file di registro precedenti al numero di giorni in cui il servizio è stato configurato per mantenere i file di registro (per impostazione predefinita, ovvero i file di registro con più di 10 giorni). Questa impostazione non può essere modificata utilizzando il pannello di controllo di Skype for Business Server. Al contrario, è necessario utilizzare Skype for Business Server Management Shell. Per specificare l'ora del giorno in cui eliminare i file di registro scaduti, utilizzare il cmdlet **New-CsDeviceUpdateConfiguration** con il parametro-LogCleanUpTimeOfDay. Per informazioni dettagliate, vedere [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Configurazione log dispositivo** è possibile eseguire le attività seguenti:

- Aggiungere una configurazione dei log dispositivo a livello globale o per un sito o pool specifico.

- Modificare le opzioni per una configurazione dei log dispositivo esistente.

## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Nuovo** È possibile aggiungere una nuova configurazione dei log dispositivo con l'ambito seguente:

  - Globale

  - Sito

- **Modifica** È possibile modificare le opzioni di una configurazione del Registro dispositivi nell'elenco. Usando questa voce, è possibile scegliere tra le opzioni seguenti:

  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione dei log dispositivo.

  - **Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni dei log dispositivo nell'elenco.

  - **Eliminare** Questa opzione consente di eliminare tutte le configurazioni dei log dispositivo selezionate.

- **Aggiorna** È possibile aggiornare l'elenco di configurazione dei log dispositivo per verificare lo stato delle opzioni di tutte le configurazioni dei log dispositivo.

## <a name="see-also"></a>Vedere anche

[Modificare le impostazioni per i file di registro dell'attività di aggiornamento dei dispositivi](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
