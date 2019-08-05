---
title: Modificare le impostazioni degli utenti di Microsoft teams in blocco
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire le impostazioni utente di Microsoft teams in blocco nell'interfaccia di amministrazione di Microsoft teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a80b39513fe86e0c49cd88988cb3f245129b2d0
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184321"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Modificare le impostazioni degli utenti di Microsoft teams in blocco

Come amministratore, puoi gestire le impostazioni degli utenti dei team nell'interfaccia di amministrazione di Microsoft teams. Nella pagina **utenti** è possibile visualizzare informazioni come account e dettagli sulle licenze e modificare i criteri e altre impostazioni. È possibile modificare le impostazioni per gli utenti singolarmente o per più utenti contemporaneamente.

## <a name="edit-user-settings-in-bulk"></a>Modificare le impostazioni utente in blocco

Usare l'interfaccia di amministrazione di Microsoft teams per modificare le impostazioni per più utenti alla volta. Ti consigliamo di modificare le impostazioni per 20 utenti alla volta. Per modificare le impostazioni per un numero elevato di utenti, usare PowerShell. Per altre informazioni, Vedi [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**.
2. Cercare gli utenti da modificare o filtrare la visualizzazione per mostrare gli utenti che si desidera modificare.
3. Nella colonna **&#x2713;** (segno di spunta) selezionare utenti eseguendo una delle operazioni seguenti:
    - Selezionare gli utenti uno alla volta. Accanto a ogni utente selezionato viene visualizzato un **&#x2713;** . Se si selezionano più di 20 utenti, non verranno bloccati, ma si terrà presente che più utenti si selezionano, più lungo sarà il completamento dell'operazione.

        ![Screenshot della pagina utenti che mostra la selezione dell'utente](media/bulk-edit-user-settings-select-users.png)

    - Fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella per selezionare tutti gli utenti (fino a un massimo di 20 utenti), quindi nella finestra di dialogo **limite selezione** fare clic su **continua selezionare tutto** per completare la selezione.

        ![Screenshot della pagina utenti che mostra il limite di selezione](media/bulk-edit-user-settings-select-all-limit.png) <br> Accanto agli utenti selezionati viene visualizzata una **&#x2713;** .

        ![Screenshot della pagina utenti che Mostra 20 utenti selezionati](media/bulk-edit-user-settings-select-all.png)
4. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **Salva**.

    ![Screenshot del riquadro Modifica impostazioni](media/bulk-edit-user-settings-edit-settings.png)
