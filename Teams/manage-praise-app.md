---
title: Gestire l'app Complimenti nell'interfaccia Teams di amministrazione
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Informazioni su come gestire l'app Complimenti nell'Microsoft Teams di amministrazione.
ms.openlocfilehash: 364fb60b6a729062e358685426acd98704c7ac02
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442682"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app Complimenti nell'interfaccia Microsoft Teams di amministrazione

L Complimenti app in Microsoft Teams consente agli utenti di mostrare apprezzamento ai membri dell'organizzazione o della classe. I badge in Complimenti sono progettati per aiutare a riconoscere l'impegno che si fa nell'ampia gamma di lavoro che Teams gli utenti, dagli educatori ai lavoratori in prima linea. Per altre informazioni, vedere [Inviare Complimenti alle persone](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Gli amministratori devono avere una licenza Teams per accedere a questa funzionalità. Se si prova ad accedere a questa funzionalità senza Teams licenza, viene visualizzato un messaggio di errore.

> [!NOTE]
> L Complimenti app è disponibile per GCC cloud, ma non per GCC High o DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Abilitare o disabilitare Complimenti'organizzazione

Complimenti è abilitato per impostazione predefinita per tutti Teams utenti dell'organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot della pagina Complimenti dettagli dell'app nell'interfaccia Teams di amministrazione, con l'interruttore Stato.":::

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Nell'elenco delle app cercare l'app Complimenti, selezionarla e quindi impostare l'interruttore Stato su  **Bloccato o** **Consentito**.

Tenere presente che questa impostazione influisce sia sull'app Complimenti che sulla funzionalità di Complimenti nell'app Viva Insights in Teams.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Complimenti utenti specifici dell'organizzazione

Per consentire o impedire a utenti specifici dell'organizzazione di usare Complimenti, verificare che l'Complimenti sia attivato per l'organizzazione nella pagina [Gestisci app](manage-apps.md). Creare quindi criteri di autorizzazione dell'app personalizzati e assegnarli a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

## <a name="badges"></a>Badge

Ecco il set predefinito di badge in Complimenti. Teams utenti dell'organizzazione possono usare questi badge per riconoscere i colleghi per andare oltre con il proprio lavoro.

:::image type="content" source="media/default-set-praise.png" alt-text="Immagine dei badge nel set di badge predefinito.":::

> [!NOTE]
> A partire da febbraio 2022, gli utenti possono inviare e ricevere solo badge predefiniti. I badge personalizzati non sono più disponibili e le opzioni per i badge personalizzati sono state rimosse dall'Teams di amministrazione.

## <a name="related-articles"></a>Articoli correlati

[Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
