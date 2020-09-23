---
title: Espansione delle impostazioni SBA del servizio di registrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'È possibile modificare le impostazioni della sezione Resilienza e configurare le proprietà seguenti:'
ms.openlocfilehash: 6424b43ea7c56760bb8d58ee35d9804c49c435dd
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217217"
---
# <a name="registrar-sba-settings-expander"></a>Espansione delle impostazioni SBA del servizio di registrazione

È possibile modificare le impostazioni della sezione **Resilienza** e configurare le proprietà seguenti:

- Selezionare **Pool di registrazione di backup e servizi utente associati** nell'elenco.

    Facoltativamente, selezionare la casella di controllo **Failover e failback automatico per VolP**.

    Configurare le opzioni **Intervallo rilevamento errori VolP (sec)** e **Intervallo failback VolP (sec)**. Per impostazione predefinita, gli intervalli sono di 120 secondi per il rilevamento errori VolP e di 240 secondi per il failback VolP.

    > [!CAUTION]
    > Il numero di secondi definito per gli intervalli di failover e failback deve essere testato attentamente per assicurare che la resilienza funzioni nel modo previsto. L'impostazione di un intervallo troppo basso, ovvero inferiore a 120 secondi, o l'impostazione di valori di failover e failback troppo vicini potrebbe compromettere il funzionamento del failover e del failback.

  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.

  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.

  **?** Visualizza questa schermata della Guida.

## <a name="see-also"></a>Vedere anche

[Pianificazione della resilienza di VoIP aziendale](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
