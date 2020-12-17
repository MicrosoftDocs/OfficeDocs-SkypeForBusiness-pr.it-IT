---
title: Assegnare proprietari e membri dei team in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Informazioni su come assegnare ruoli e autorizzazioni al proprietario e membri del team in Microsoft Teams, incluse le autorizzazioni per creare team.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc85b682ee24b466514e297532dc9ac0deb56924
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739284"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Assegnare proprietari e membri dei team in Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

All'interno di Microsoft Teams sono disponibili due ruoli utente: **proprietario** e **membro**. Per impostazione predefinita, a un utente che crea un nuovo team viene concesso lo stato di proprietario. Inoltre, i proprietari e i membri del team possono assumere funzioni di moderatore per un canale, purché la funzionalità di moderazione sia stata configurata. Se si crea un team da un gruppo esistente di Microsoft 365, le autorizzazioni vengono ereditate da quel gruppo.

La tabella seguente mostra le differenze tra l'autorizzazione di un proprietario e quella di un membro


|    Attività                               | Proprietario di un team | Membro del team |
|-----------------------------------|------------|-------------|
|          **Crea un team**          |    Sì<sup>1</sup>     |     No      |
|          **Abbandona il team**           |    Sì     |     Sì     |
|  **Modifica il nome e la descrizione del team**   |    Sì     |     No      |
|          **Elimina il team**          |    Sì     |     No      |
|          **Aggiunge un canale standard**          |    Sì     |    Sì<sup>2</sup>|
| **Modifica il nome e la descrizione del canale standard** |    Sì     |    Sì<sup>2</sup>|
|        **Elimina un canale standard**         |    Sì     |    Sì<sup>2</sup>|
|          **_Aggiunge un canale privato_*          |    Sì     |    Sì<sup>2</sup>|
| **_Modifica il nome e la descrizione del canale privato_* |    No     |    N/D|
|        **_Elimina un canale privato_*         |    Sì     |    No|
|          **Aggiunge membri**          |  Sì<sup>3</sup>   |     No<sup>4</sup>    |
|          **Richiedere l'aggiunta di membri**          |  N/D   |     Sì<sup>5</sup>     |
|           **Aggiunge app**            |    Sì     |    Sì<sup>2</sup>|

<sup>1</sup> I proprietari dei team possono creare team a meno che gli sia stato limitato. [Autorizzazioni per la creazione di team](#permissions-to-create-teams) vedere in fondo alla pagina.<br>
<sup>2</sup> Un proprietario può disattivare questi elementi a livello di team, nel qual caso i membri non avessero accesso ad essi.<br>
<sup>3</sup> Dopo aver aggiunto un membro a un team, un proprietario può anche alzare di livello un membro e passarlo a proprietario. È anche possibile che il proprietario abbassi il proprio stato a membro.<br>
<sup>4</sup> I membri del team possono aggiungere altri membri a un team pubblico.<br>
<sup>5</sup> Sebbene un membro del team non possa aggiungere direttamente membri a un team privato, può richiedere che qualcuno venga aggiunto a un team di cui è già membro. Quando un membro richiede che qualcuno venga aggiunto a un team, i proprietari del team ricevono un avviso che indica che hanno una richiesta in sospeso che possono accettare o rifiutare.

* Per altre informazioni sulle autorizzazioni per i canali privati, vedere [Canali privati in Teams](private-channels.md).

> [!NOTE]
> I proprietari possono rendere proprietari altri membri nell’opzione **Visualizza team**. Un team può avere un massimo di 100 proprietari. È consigliabile disporre di almeno alcuni proprietari per aiutare a gestire il team. Questo impedirà anche gruppi orfani, nel caso in cui il solo proprietario lasci l'organizzazione. Per altre informazioni sui gruppi orfani, vedere [Assegnare un nuovo proprietario a un gruppo orfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Funzionalità moderatore

Inoltre, se viene attivata la moderazione per un team, i proprietari e i membri del team possono assumere le funzioni di moderatore per un canale. I moderatori possono avviare nuovi post nel canale e controllare se i membri del team possono rispondere ai messaggi esistenti nel canale. Possono anche controllare se i bot e i connettori possono inviare messaggi di canale.

Le funzionalità di moderatore sono assegnate a livello di canale. Per impostazione predefinita, i proprietari del team hanno funzionalità di moderatore. Per impostazione predefinita, le funzionalità di moderatore dei membri del team sono disattivate. Tuttavia, il proprietario del team può assegnare a un membro del team le funzionalità di moderatore del canale. I moderatori all'interno di un canale possono aggiungere e rimuovere altri moderatori all'interno del canale.

Per altre informazioni sulle le funzioni di moderatore, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Assegnare un ruolo utente

Per assegnare un ruolo utente, in Teams selezionare il nome del team e quindi fare clic su **Altre opzioni** > **Gestisci team**. Nella scheda **Membri** è possibile aggiungere membri e scegliere proprietari e moderatori se si hanno autorizzazioni sufficienti. Per altre informazioni, vedere [Modificare le impostazioni del team in Microsoft Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Autorizzazioni per la creazione di team

Per impostazione predefinita, tutti gli utenti che dispongono di una cassetta postale in Exchange Online hanno le autorizzazioni necessarie per creare gruppi di Microsoft 365 e pertanto un team in Microsoft Teams. È possibile avere un controllo più rigoroso e limitare la creazione di nuovi team e la creazione di nuovi gruppi di Microsoft 365, delegando i diritti di creazione e gestione del gruppo a un insieme di utenti. Per istruzioni, vedere [Gestire chi può creare gruppi di Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


|Icona|Titolo|Descrizione|
|---------|---------|---------|
| ![Icona che rappresenta un punto decisionale](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto decisionale         |Tutti gli utenti di Microsoft Teams potranno creare team (consigliato)?         |
| ![Icona che rappresenta i passaggi successivi](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Passaggi successivi         |Modificare le autorizzazioni predefinite per gli utenti che possono creare gruppi di Microsoft 365, se si vuole limitare chi può creare team         |
