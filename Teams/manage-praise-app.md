---
title: Gestire l'app Complimento nell'interfaccia di amministrazione di Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: Informazioni su come gestire l'app Complimento nell'interfaccia di amministrazione di Microsoft Teams.
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 9b1155560c0f901b88d3983e2ff3738e5ffa6e47
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251769"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app Complimento nell'interfaccia di amministrazione di Microsoft Teams

L'app Complimento in Microsoft Teams aiuta gli utenti a mostrare apprezzamento ai membri dell'organizzazione o della classe. I badge in Complimento sono progettati per riconoscere l'impegno che va nell'ampia gamma di lavoro svolto dagli utenti di Teams, dai docenti ai dipendenti in prima linea. Per altre informazioni, vedere [Inviare complimenti alle persone](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Gli amministratori devono avere una licenza di Teams per accedere a questa funzionalità. Se si prova ad accedere a questa funzionalità senza una licenza di Teams, viene visualizzato un messaggio di errore.

> [!NOTE]
> L'app Complimento è disponibile per l'ambiente cloud GCC, ma non per GCC High o DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Abilitare o disabilitare Complimento nell'organizzazione

L'complimento è abilitato per impostazione predefinita per tutti gli utenti di Teams nell'organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot della pagina Dei dettagli dell'app Complimento nell'interfaccia di amministrazione di Teams, con l'interruttore Stato.":::

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestire app**.
2. Nell'elenco delle app cerca l'app Complimento, selezionala e quindi imposta **l'interruttore Stato** su **Bloccato** o **Consentito**.

Tenere presente che questa impostazione influisce sia sull'app Complimento che sulla funzionalità Complimento nell'app Viva Insights in Teams.

Se si imposta lo stato su **Bloccato**, l'app Complimento viene bloccata entro pochi minuti per Teams. Tuttavia, l'operazione Complimento in Viva Insights può richiedere da 7 a 9 giorni per essere bloccata.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Complimento per utenti specifici dell'organizzazione

Per consentire o bloccare l'uso di Complimenti da parte di utenti specifici dell'organizzazione, verificare che l'opzione Complimento sia attivata per l'organizzazione nella pagina [Gestisci app](manage-apps.md) . Creare quindi un criterio personalizzato per le autorizzazioni per le app e assegnarlo a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

## <a name="composer"></a>Compositore

Gli utenti di Teams nella tua organizzazione possono usare il compositore di complimenti per riconoscere i loro colleghi per andare al di là del loro lavoro. Mentre realizzano il loro messaggio, possono scegliere tra 14 titoli&mdash;come **Courage**, **Optimism**, **Kind heart** e **Creative**&mdash;per riconoscere il contributo dei loro colleghi.

:::image type="content" source="media/praise.png" alt-text="Screenshot del compositore di complimenti.":::

## <a name="related-articles"></a>Articoli correlati

[Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
