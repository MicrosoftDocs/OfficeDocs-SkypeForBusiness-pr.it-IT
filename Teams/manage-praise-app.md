---
title: Gestire l'app Complimenti nell'interfaccia di amministrazione di Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Informazioni su come gestire l'app Complimenti nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: e9da2a1903c53f469d6a64c6773715bfe1697743
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646275"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gestire l'app Complimenti nell'interfaccia di amministrazione di Microsoft Teams

L'app Complimenti in Microsoft Teams consente agli utenti di mostrare apprezzamento ai membri dell'organizzazione o della classe. I badge in Complimenti sono progettati per riconoscere l'impegno nell'ampia gamma di lavoro svolto dagli utenti Teams, dai docenti ai dipendenti in prima linea. Per altre informazioni, vedere [Inviare Complimenti alle persone](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Gli amministratori devono avere una licenza di Teams per accedere a questa funzionalità. Se si prova ad accedere a questa funzionalità senza una licenza di Teams, viene visualizzato un messaggio di errore.

> [!NOTE]
> L'app Complimenti è disponibile per GCC ambiente cloud, ma non per GCC High o DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Abilitare o disabilitare Complimenti nell'organizzazione

Complimenti è abilitata per impostazione predefinita per tutti gli utenti Teams dell'organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Screenshot della pagina dei dettagli dell'app Complimenti nell'interfaccia di amministrazione di Teams con l'interruttore Stato.":::

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams** **appGesti** >  app.
2. Nell'elenco delle app cerca l'app Complimenti, selezionala e quindi imposta **Stato** su **Bloccato** o **Consentito**.

Tieni presente che questa impostazione influisce sia sull'app Complimenti che sulla funzionalità Complimenti nell'app Viva Insights in Teams.

Se imposti Lo stato su Bloccato, l'app Complimenti viene bloccata entro pochi minuti per Teams. Tuttavia, un complimento in Viva Insights può richiedere da 7 a 9 giorni per essere bloccato.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Complimenti per utenti specifici dell'organizzazione

Per consentire o bloccare l'uso di Complimenti da parte di utenti specifici dell'organizzazione, verificare che Complimenti sia attivato per l'organizzazione nella pagina [Gestisci app](manage-apps.md). Creare quindi un criterio di autorizzazione per le app personalizzato e assegnarlo a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

## <a name="badges"></a>Distintivi

Ecco il set predefinito di badge in Complimenti. Teams gli utenti dell'organizzazione possono usare questi badge per riconoscere i colleghi per andare oltre il lavoro.

:::image type="content" source="media/default-set-praise.png" alt-text="Immagine di badge nel set di notifiche predefinito.":::

> [!NOTE]
> A partire da febbraio 2022, gli utenti possono inviare e ricevere solo badge predefiniti. I badge personalizzati non sono più disponibili e le opzioni per i badge personalizzati sono state rimosse dall'interfaccia di amministrazione di Teams.

## <a name="related-articles"></a>Articoli correlati

[Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
