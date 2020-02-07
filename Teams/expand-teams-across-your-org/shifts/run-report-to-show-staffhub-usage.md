---
title: Eseguire un report per mostrare l'utilizzo di StaffHub attivo
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe7851e57cd6d812d0b8904668ca5fd67fd5999d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826694"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a>Eseguire un report per mostrare l'utilizzo di StaffHub attivo

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).  

Seguire i passaggi di questo articolo per eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione. Queste informazioni possono essere utili quando si preparano a [trasferire i team di StaffHub a Microsoft teams](move-staffhub-teams-to-shifts-in-teams.md). Nel report è necessario includere le comunicazioni quando si effettua il passaggio da StaffHub a teams.

Per eseguire la procedura descritta in questo articolo, è necessario avere Azure AD Premium.

1. Accedere a Azure Portal.
2. Nel riquadro sinistro fare clic sulla risorsa di **Azure Active Directory** .
3. In **monitoraggio**fare clic su **sign-ins**.
4. In **applicazione**digitare **Microsoft StaffHub**.
5. Impostare l'intervallo di date desiderato per il report e quindi fare clic su **applica**. 

    ![Schermata che mostra i passaggi per visualizzare l'uso di Active StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a>Argomenti correlati

- [Spostare i team di Microsoft StaffHub in turni in Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md)
