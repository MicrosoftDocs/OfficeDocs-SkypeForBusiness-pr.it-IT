---
title: Impostazioni di registrar SBA
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Si modificano le impostazioni per la resilienza e si configurano le proprietà seguenti:'
ms.openlocfilehash: dc5f207653142374fce00cdc774bc3a88fcea1b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195774"
---
# <a name="registrar-sba-settings-expander"></a>Impostazioni di registrar SBA

Si modificano le impostazioni **** per la resilienza e si configurano le proprietà seguenti:

- Selezionare **servizio utente associato e pool** di registrar di backup dall'elenco.

    Facoltativamente, selezionare la casella **di controllo failover automatico e failback per la voce** .

    Configurare l' **intervallo di rilevamento errori vocali (sec)** e l' **intervallo di failback vocale (sec)**. Per impostazione predefinita, gli intervalli sono 120 secondi per il rilevamento dell'errore vocale e 240 secondi per il failback vocale.

    > [!CAUTION]
    > Il numero di secondi definiti per gli intervalli di failover e failback deve essere testato con attenzione per verificare che la resilienza funzioni come previsto. L'impostazione dell'intervallo su basso (ovvero meno di 120 secondi) o il failover e il failback impostati troppo da vicino può causare il failover effettivo e il failback non funzionano come previsto.

  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.

  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.

  **Guida** Consente di visualizzare questa schermata della Guida.

## <a name="see-also"></a>Vedere anche

[Pianificazione della resilienza di Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
