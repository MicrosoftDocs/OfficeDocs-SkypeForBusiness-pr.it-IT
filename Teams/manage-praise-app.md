---
title: Gestire l'app Complimento nell'interfaccia di amministrazione di Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Informazioni su come gestire l'app Complimento nell'interfaccia di amministrazione di Microsoft Teams.
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.openlocfilehash: 5771aaa9122ddc79d4555c74d509d2c4a77f57fb
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655872"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app Complimento nell'interfaccia di amministrazione di Microsoft Teams

L'app Complimento in Microsoft Teams consente agli utenti di mostrare apprezzamento ai membri dell'organizzazione o della classe. I badge in Complimento sono progettati per riconoscere l'impegno che va nell'ampia gamma di lavoro svolto dagli utenti di Teams, dai docenti ai dipendenti in prima linea. Per altre informazioni, vedere [Inviare complimenti alle persone](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Gli amministratori devono avere una licenza di Teams per accedere a questa funzionalità. Se si prova ad accedere a questa funzionalità senza una licenza di Teams, viene visualizzato un messaggio di errore.

> [!NOTE]
> L'app Complimento è disponibile per l'ambiente cloud GCC, ma non per GCC High o DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Abilitare o disabilitare Complimento nell'organizzazione

L'complimento è abilitato per impostazione predefinita per tutti gli utenti di Teams nell'organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot della pagina Dei dettagli dell'app Complimento nell'interfaccia di amministrazione di Teams, con l'interruttore Stato.":::

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestire app**.
2. Nell'elenco delle app cerca l'app Complimento, selezionala e quindi imposta **l'interruttore Stato** su **Bloccato** o **Consentito**.

Tenere presente che questa impostazione influisce sia sull'app Complimento che sulla funzionalità Complimento nell'app Viva Insights in Teams.

Se si imposta Stato su Bloccato, l'app Complimento viene bloccata entro pochi minuti per Teams. Tuttavia, un complimento in Viva Insights può richiedere da 7 a 9 giorni per essere bloccato.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Complimento per utenti specifici dell'organizzazione

Per consentire o bloccare l'uso di Complimenti da parte di utenti specifici dell'organizzazione, verificare che l'opzione Complimento sia attivata per l'organizzazione nella pagina [Gestisci app](manage-apps.md) . Creare quindi un criterio personalizzato per le autorizzazioni per le app e assegnarlo a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

## <a name="badges"></a>Distintivi

Ecco il set predefinito di badge in Complimento. Gli utenti di Teams nell'organizzazione possono usare questi badge per riconoscere i loro colleghi per andare oltre con il loro lavoro.

:::image type="content" source="media/default-set-praise.png" alt-text="Immagine di badge nel set di notifiche predefinito.":::

> [!NOTE]
> A partire da febbraio 2022, gli utenti possono inviare e ricevere solo badge predefiniti. I badge personalizzati non sono più disponibili e le opzioni per i badge personalizzati sono state rimosse dall'interfaccia di amministrazione di Teams.

## <a name="related-articles"></a>Articoli correlati

[Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
