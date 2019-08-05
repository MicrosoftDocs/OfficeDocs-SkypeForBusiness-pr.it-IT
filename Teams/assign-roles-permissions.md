---
title: Assegnare proprietari e membri del team in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Informazioni su come assegnare il proprietario del team e i ruoli dei membri e le autorizzazioni in Microsoft teams, incluse le autorizzazioni per creare team.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eca4f5350e4e06d3f598191e020b8708b6f47563
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "36184981"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Assegnare proprietari e membri del team in Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

All'interno di Microsoft teams sono presenti due ruoli utente: **owner** e **member**. Per impostazione predefinita, viene concesso lo stato proprietario a un utente che crea un nuovo team. Inoltre, i proprietari e i membri possono avere funzionalità di moderatore per un canale (a condizione che sia stata configurata la moderazione). Se un team viene creato da un gruppo di Office 365 esistente, le autorizzazioni vengono ereditate.

La tabella seguente mostra la differenza tra le autorizzazioni di un proprietario e di un membro.


|                                   | Proprietario del team | Membro del team |
|-----------------------------------|------------|-------------|
|          **Creare un team**          |    Sì<sup>1</sup>     |     No      |
|          **Lascia il team**           |    Sì     |     Sì     |
|  **Modificare il nome del team/Descrizione**   |    Sì     |     No      |
|          **Elimina team**          |    Sì     |     No      |
|          **Aggiungi canale**          |    Sì     |    Sì<sup>2</sup>|
| **Modificare il nome del canale/Descrizione** |    Sì     |    Sì<sup>2</sup>|
|        **Elimina canale**         |    Sì     |    Sì<sup>2</sup>|
|          **Aggiungere membri**          |  Sì<sup>3</sup>   |     N.<sup>4</sup>    |
|          **Richiesta di aggiunta di membri**          |  N/D   |     Sì<sup>5</sup>     |
|           **Aggiungere schede**            |    Sì     |    Sì<sup>2</sup>|
|        **Aggiungere connettori**         |    Sì     |    Sì<sup>2</sup>|
|           **Aggiungere bot**            |    Sì     |    Sì<sup>2</sup>|

<sup>1</sup> i proprietari del team possono creare Teams a meno che non siano stati limitati. [Autorizzazioni per creare teams di](#permissions-to-create-teams) seguito.<br>
><sup>2</sup> un proprietario può disattivare questi elementi a livello di Team, in questo caso i membri non avrebbero accesso.<br>
<sup>3</sup> dopo l'aggiunta di un membro a un team, un proprietario può anche promuovere un membro in stato proprietario. È anche possibile che un proprietario abbassasse di livello il proprio stato a un membro.<br>
<sup>4</sup> i membri del team possono aggiungere altri membri a un team pubblico.<br>
<sup>5</sup> quando un membro del team non può aggiungere direttamente membri a un team privato, può richiedere che qualcuno venga aggiunto a un team di cui è già membro. Quando un membro richiede l'aggiunta di un utente a un team, i proprietari del team ricevono un avviso con una richiesta in sospeso che può accettare o rifiutare.

> [!NOTE]
> I proprietari possono rendere i proprietari degli altri membri nell'opzione **Visualizza teams** . Un team può avere fino a 100 proprietari. È consigliabile avere almeno alcuni proprietari per facilitare la gestione del team. verranno inoltre impediti gruppi orfani se un solo proprietario lascia l'organizzazione. Per altre informazioni sui gruppi orfani, vedere [assegnare un nuovo proprietario a un gruppo orfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Funzionalità del moderatore

Oltre ad altre funzionalità, i proprietari e i membri del team possono avere funzionalità di moderatore per un canale (a condizione che la moderazione sia attivata per un team). I moderatori possono avviare nuovi post in un canale e controllare se i membri del team possono rispondere ai messaggi del canale esistenti. Possono anche controllare se i bot e i connettori possono inviare messaggi di canale.

Le funzionalità di moderatore vengono assegnate a livello di canale. Per impostazione predefinita, i proprietari del team hanno funzionalità di moderatore. I membri del team hanno funzionalità di moderatore disattivate per impostazione predefinita, ma un proprietario del team può offrire funzionalità di moderatore per un canale a un membro del team. I moderatori all'interno di un canale possono aggiungere e rimuovere altri moderatori all'interno del canale.

Per altre informazioni sulle funzionalità di moderatore, vedere [configurare e gestire la moderazione dei canali in Microsoft teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Assegnare un ruolo utente

Per assegnare un ruolo utente, in teams selezionare il nome del team e fare clic su **altre opzioni** > **Gestisci team**. Nella scheda **membri** è possibile aggiungere membri e scegliere proprietari e moderatori (se si dispone di autorizzazioni sufficienti). Per altre informazioni, vedere [modificare le impostazioni del team in teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Autorizzazioni per la creazione di Team

Per impostazione predefinita, tutti gli utenti con una cassetta postale in Exchange Online hanno le autorizzazioni per creare gruppi di Office 365 e quindi un team in Microsoft teams. È possibile avere un controllo più rigoroso e limitare la creazione di nuovi team e quindi la creazione di nuovi gruppi di Office 365 delegando i diritti di creazione e gestione del gruppo a un insieme di utenti. Per istruzioni, vedere [gestire chi può creare gruppi di Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icona che rappresenta un punto decisionale](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto decisionale         |Tutti gli utenti di Microsoft teams saranno in grado di creare Teams (scelta consigliata)?         |
| ![Icona che rappresenta i passaggi successivi](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Operazioni successive         |Modificare le autorizzazioni predefinite per chi può creare gruppi di Office 365 se è necessario limitare chi può creare Teams         |
