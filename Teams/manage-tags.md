---
title: Gestire i tag in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire i tag usati nell'organizzazione in Microsoft teams.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034509"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gestire i tag in Microsoft Teams

> [!NOTE]
> Questa funzionalità non è ancora visualizzata nell'interfaccia di amministrazione di Microsoft Teams? Attualmente viene implementato e potrebbe non essere ancora disponibile nell'organizzazione. Per rimanere in primo piano sulle caratteristiche future per i team, consulta la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

I tag in Microsoft teams consentono agli utenti di comunicare con un sottoinsieme di persone in un team. I tag possono essere aggiunti a uno o più membri del team per connettersi facilmente con il sottoinsieme giusto di persone. I proprietari e i membri del team (se la funzionalità è abilitata) possono aggiungere uno o più tag a una persona. I tag possono quindi essere usati in @mentions da chiunque nel team in un post del canale per comunicare solo con gli utenti a cui è stato assegnato il tag.

> [!NOTE]
> I tag non sono ancora supportati nei canali privati.

## <a name="how-tags-work"></a>Come funzionano i tag

Un tag può essere aggiunto a una persona in un team specifico. Dopo l'aggiunta di un tag, può essere usato in @mentions in qualsiasi canale standard del team. Ecco alcuni esempi di come i tag possono essere usati in teams:

- Un responsabile dello Store vuole pubblicare un annuncio su un canale e inviare una notifica a tutti i cassieri.
- Un Product Manager di gruppo vuole Message tutti i responsabili di prodotto in un canale.
- Un amministratore dell'ospedale vuole inviare un messaggio a tutti i radiologi di un canale.

Per altre informazioni, vedere [usare i contrassegni in teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

## <a name="manage-tags-for-your-organization"></a>Gestire i tag per l'organizzazione

Come amministratore, puoi controllare chi può aggiungere tag e come vengono usati i tag in tutta l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.

![Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a>Impostare gli utenti che possono aggiungere tag

Per impostazione predefinita, i proprietari del team possono aggiungere tag. Puoi modificare questa impostazione per consentire ai proprietari del team e ai membri del team di aggiungere tag oppure disattivare i tag per l'organizzazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su**impostazioni di Team** **Impostazioni** > a livello di organizzazione.
2. In **contrassegno**, accanto a **contrassegno è abilitato per**Selezionare una delle opzioni seguenti:

    - **Proprietari e membri del team**: consentire ai proprietari e ai membri del team di aggiungere tag.
    - **Proprietari del team**: consentire ai proprietari del team di aggiungere tag.
    - **Disabilitato**: disattivare i contrassegni.

### <a name="configure-tags-settings"></a>Configurare le impostazioni di tag

Puoi configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag vengono usati nell'organizzazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su**impostazioni di Team** **Impostazioni** > a livello di organizzazione.
2. In **tagging**impostare le operazioni seguenti in base alle esigenze dell'organizzazione.

    - Il **proprietario del team può eseguire l'override di chi può applicare i tag**: quando questo è attivato, i proprietari del team possono consentire o impedire ai membri di aggiungere tag nelle impostazioni del team.
    - **I membri possono aggiungere tag aggiuntivi**: se si consente ai membri del team di aggiungere tag, attivare questa opzione per consentire ai membri del team di aggiungere tag diversi dai tag predefiniti consigliati impostati. Se questa opzione è disattivata, i membri del team possono usare solo i tag predefiniti.
    - **Tag predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti. È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri. I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.

## <a name="manage-tags-settings-for-a-team"></a>Gestire le impostazioni dei tag per un team

Se è stato attivato il **proprietario del team può eseguire l'override di chi può applicare** l'impostazione di tag nell'interfaccia di amministrazione di Microsoft teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team. A questo scopo, nella scheda **Impostazioni** di un team passa a **tag**e quindi scegli chi può aggiungere i tag.

![Screenshot dell'impostazione di tag a livello di Team](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a>Aggiungere tag in teams

In teams la scheda **membri** della pagina Manage team per un team include una colonna **Tags** . I proprietari e i membri del team (se la funzionalità è abilitata) possono fare clic su **Gestisci Tag** accanto a un membro per visualizzare l'elenco dei tag suggeriti per il membro e aggiungere i tag all'elenco.

![Screenshot che illustra come applicare i tag nel client Teams ](media/manage-tags-teams.png) 
