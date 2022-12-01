---
title: Assegnare proprietari e membri del team nell Microsoft interfaccia di amministrazione di Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Informazioni su come assegnare ruoli e autorizzazioni al proprietario e membri del team in Microsoft Teams, incluse le autorizzazioni per creare team.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b25a5d654e4bd7a807918aa86e0bfd52aff2ca04
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198758"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Assegnare proprietari e membri del team nell Microsoft interfaccia di amministrazione di Teams

**Proprietario** e **membro** sono i due ruoli utente all'interno di Microsoft Teams. Per impostazione predefinita, all'utente che crea un nuovo team viene concesso lo stato di proprietario. Proprietari e membri hanno diversi tipi di autorizzazioni e funzionalità durante l'interazione con un team e i relativi canali. Per altre informazioni sui ruoli in Teams, vedere [Panoramica di team e canali in Microsoft Teams](teams-channels-overview.md).

> [!NOTE]
> Se un team viene creato da un gruppo di Microsoft 365 esistente, le autorizzazioni vengono ereditate.

## <a name="assign-a-user-role-in-teams-admin-center"></a>Assegnare un ruolo utente nell'interfaccia di amministrazione di Teams

1. Nell'interfaccia di amministrazione di Teams espandere **Teams** e selezionare **Gestisci team**.
2. Selezionare il nome del team sotto la colonna del nome visualizzato.
3. Nella scheda Membri è possibile aggiungere o rimuovere membri e assegnare ruoli di proprietario e moderatore ai membri.

## <a name="restrict-permission-to-create-teams"></a>Limitare le autorizzazioni per la creazione di team

Tutti gli utenti con una cassetta postale in Exchange Online hanno le autorizzazioni per creare gruppi di Microsoft 365 e un team all'interno di Microsoft Teams. Impedire agli utenti di creare nuovi team e gruppi di Microsoft 365 delegando i diritti di creazione e gestione dei gruppi a un set di utenti. Se questa restrizione è attiva, né i proprietari né i membri del team possono creare nuovi team. Per altre informazioni, vedere [Gestire chi può creare gruppi di Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="user-permissions-based-on-assigned-roles"></a>Autorizzazioni utente in base ai ruoli assegnati

La tabella seguente mostra le differenze tra l'autorizzazione di un proprietario e quella di un membro

### <a name="teams"></a>Teams

|Attività di Teams| Proprietario di un team | Membro del team |
|---------|---------|---------|
|Creare/eliminare un team  |    Sì     |     No    |
|Modifica il nome e la descrizione del team   |     Sì    |     No     |
|Aggiungere membri al team privato    |     Sì    |  No |
|Aggiungere membri al team pubblico    |     Sì    |     Sì   |
|Richiesta di aggiunta di un nuovo membro   |     N/D    |    Sì   |
|Alzare/abbassare di livello lo stato dell'utente | Sì | No |
|Abbandona il team  |    Sì     |     Sì    |
|Aggiungere/rimuovere app   |     Sì    |     Sì, se abilitato dal proprietario del team     |

### <a name="channels"></a>Canali

|***Attività di canale standard** _ | _ *Proprietario del team** | **Membro del team**|
|----|----|----|
|Creare/eliminare un canale  |     Sì    |    Sì, se abilitato dal proprietario del team      |
|Modificare il nome/la descrizione del canale    |    Sì     |     Sì, se abilitato dal proprietario del team    |
|***Attività del canale privato***|
|Creare canali    |    Sì     |    Sì, se abilitato dal proprietario del team      |
|Elimina canale    |    Sì     |    No     |
|Modificare il nome/la descrizione del canale |     No    |    N/D     |
|***Attività dei canali condivisi***
|Creare canali    |    Sì     |     No    |
|Elimina canale | Sì | No |
|Modificare il nome/la descrizione del canale    |    No     |     No    |
