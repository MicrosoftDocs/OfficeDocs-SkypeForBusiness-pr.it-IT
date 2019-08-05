---
title: Configurazione registro dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è consigliabile impostare le soglie per la dimensione della cache dei dati del log, le dimensioni dei file di log o il periodo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione. Se non si desidera che il servizio Web aggiornamento dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.
ms.openlocfilehash: 7c4f532af6e74f8ef13b3b2de17017b66afc0b59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195181"
---
# <a name="device-log-configuration"></a>Configurazione registro dispositivo

Il servizio Web aggiornamento dispositivi crea automaticamente file di log in cui viene registrata l'attività di aggiornamento dei dispositivi. Come parte della strategia di gestione dei dati dell'organizzazione, è consigliabile impostare le soglie per la dimensione della cache dei dati del log, le dimensioni dei file di log o il periodo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione. Se non si desidera che il servizio Web aggiornamento dispositivi elimini automaticamente i file di log, è possibile eliminarli manualmente, se necessario. Le impostazioni dei log possono essere modificate a livello globale o per singoli siti.

> [!NOTE]
> È anche possibile configurare l'ora del giorno in cui si vuole che il servizio di aggiornamento del dispositivo web elimini automaticamente i file di log antecedenti al numero di giorni in cui il servizio è stato configurato per conservare i file di log (per impostazione predefinita, ovvero i file di log con più di 10 giorni di età). Questa impostazione non può essere modificata usando il pannello di controllo di Skype for Business Server. Devi invece usare Skype for Business Server Management Shell. Per specificare l'ora del giorno in cui eliminare i file di log scaduti, usare il cmdlet **New-CsDeviceUpdateConfiguration** con il parametro-LogCleanUpTimeOfDay. Per informazioni dettagliate, vedere [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Configurazione log dispositivo** è possibile eseguire le attività seguenti:

- Aggiungere una configurazione dei log dispositivo a livello globale o per un sito o pool specifico.

- Modificare le opzioni per una configurazione del log del dispositivo esistente.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Nuovo** È possibile aggiungere una nuova configurazione del log dei dispositivi con l'ambito seguente:

  - Globale

  - Sito

- **Modifica** È possibile modificare le opzioni di una configurazione del log dei dispositivi nell'elenco. Usando questa voce, è possibile scegliere tra le opzioni seguenti:

  - **Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni per una configurazione del log dei dispositivi.

  - **Seleziona tutto** Questa opzione Seleziona tutta la configurazione del log dei dispositivi nell'elenco.

  - **Eliminare** Questa opzione Elimina tutta la configurazione del log del dispositivo selezionata.

- **Aggiornare** È possibile aggiornare l'elenco di configurazione del log dei dispositivi per verificare lo stato delle opzioni di tutta la configurazione del log dei dispositivi.

## <a name="see-also"></a>Vedere anche

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
