---
title: Espansione delle impostazioni del registrar SBA
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si modificano le impostazioni per la resilienza e si configurano le proprietà seguenti:'
ms.openlocfilehash: 7eb90efde862b6326ea6f43f27937751ebff0ce9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797247"
---
# <a name="registrar-sba-settings-expander"></a>Espansione delle impostazioni del registrar SBA

Si modificano le impostazioni per la **resilienza** e si configurano le proprietà seguenti:

- Selezionare **servizio utente associato e pool di registrar di backup** dall'elenco.

    Facoltativamente, selezionare la casella **di controllo failover automatico e failback per la voce** .

    Configurare l' **intervallo di rilevamento errori vocali (sec)** e l' **intervallo di failback vocale (sec)**. Per impostazione predefinita, gli intervalli sono 120 secondi per il rilevamento dell'errore vocale e 240 secondi per il failback vocale.

    > [!CAUTION]
    > Il numero di secondi definiti per gli intervalli di failover e failback deve essere testato con attenzione per verificare che la resilienza funzioni come previsto. L'impostazione dell'intervallo su basso (ovvero meno di 120 secondi) o il failover e il failback impostati troppo da vicino può causare il failover effettivo e il failback non funzionano come previsto.

  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.

  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.

  **Guida** Consente di visualizzare questa schermata della Guida.

## <a name="see-also"></a>Vedere anche

[Pianificazione della resilienza di Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
