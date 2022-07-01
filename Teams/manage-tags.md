---
title: Gestire i tag in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire l'uso dei tag nell'organizzazione in Microsoft Teams.
ms.openlocfilehash: 146b8fa36eccb446921c87dd98aa3af44458ba00
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563714"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gestire i tag in Microsoft Teams

## <a name="overview"></a>Panoramica

I tag in Microsoft Teams consentono agli utenti di connettersi rapidamente e facilmente con un sottoinsieme di persone in un team. È possibile creare e assegnare tag personalizzati per categorizzare le persone in base ad attributi come ruolo, progetto, competenza o posizione. In alternativa, i tag possono essere assegnati automaticamente alle persone in base alle informazioni sui pianificare e sui turni [nell'app Turni](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Dopo l'aggiunta di un tag a uno o più membri del team, può essere usato in @mentions da tutti i membri del team in un post di canale o per avviare una conversazione solo con le persone a cui è assegnato.

Come accennato in precedenza, ci sono due tipi di tag in Teams.

- **Tag personalizzati**: i proprietari e i membri del team (se la funzionalità è abilitata per loro) possono creare e assegnare manualmente tag agli utenti. Ad esempio, un tag "Designer" o "Radiologist" raggiungerà questi gruppi di persone in un team senza doverne digitare i nomi.
- **Aggiunta di tag tramite turno**: con questa funzionalità, alle persone vengono assegnati automaticamente tag che corrispondono al nome del gruppo pianificare e turno [nell'app Turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams. Ad esempio, il tag "EngineerOnCall" raggiunge tutti i tecnici che sono pianificati in Turni per lavorare nel momento in cui il tag viene utilizzato in una chat o un post di canale. Con l'aggiunta di tag tramite turno, Teams elimina i tentativi di conoscere il nome del personale in turno quando gli utenti devono inoltrare rapidamente le informazioni. L'aggiunta di tag tramite turno può anche essere supportata dai principali sistemi di gestione della forza lavoro come JDA, Kronos e AMiON integrandoli con Turni in Teams. Per altre informazioni su come configurare questa funzionalità, vedere [Configurare l'aggiunta di tag tramite turno](#set-up-tagging-by-shift).

> [!NOTE]
> I tag non sono supportati in canali privati o condivisi.

## <a name="how-tags-work"></a>Funzionamento dei tag

Un tag può essere aggiunto manualmente o assegnato automaticamente a una persona di un team specifico. Può quindi essere usato in @mentions nella riga **A** in una chat o in un post su qualsiasi canale standard del team. Ecco alcuni esempi di come i tag possono essere usati in Teams:

- Un responsabile dello Store pubblica un annuncio a un canale per informare tutti i cassieri.
- Un amministratore dell'ospedale invia un messaggio a tutti i radioologi in un canale.
- Un responsabile marketing avvia una chat di gruppo con tutti i progettisti.
- Un infermiere invia un messaggio a tutti i cardiologi di chiamata. (presto disponibile)
- Un tecnico di sistema pubblica un annuncio a un canale per inviare una notifica a tutti gli ingegneri sul campo in turno. (presto disponibile)

Quando un tag viene @mentioned in una conversazione del canale, i membri del team associati al tag riceveranno una notifica, proprio come qualsiasi altro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gestire tag personalizzati per l'organizzazione

Gli amministratori possono controllare il modo in cui i tag vengono usati nell'intera organizzazione nell'interfaccia di amministrazione di Microsoft Teams. Attualmente non è possibile usare PowerShell per gestire i tag.

![Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams.](media/manage-tags-admin-settings.png)

Un team può avere fino a 100 tag, a un tag possono essere assegnati fino a 200 membri del team e fino a 25 tag nello stesso team a un singolo utente.

### <a name="set-who-can-add-custom-tags"></a>Impostare chi può aggiungere tag personalizzati

Per impostazione predefinita, i proprietari del team possono aggiungere tag personalizzati. È possibile modificare questa impostazione per consentire ai proprietari e ai membri del team di creare, modificare, eliminare e gestire i tag oppure è possibile disattivare i tag per l'organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Impostazioni di Teams** > .
2. In **Tag,** accanto a **Tag gestiti da**, selezionare una delle opzioni seguenti:

    - **Proprietari e membri** del team: consente ai proprietari e ai membri del team di gestire i tag.
    - **Proprietari del** team: consente ai proprietari del team di gestire i tag.
    - **Disabilitato**: disattivare i contrassegni.

### <a name="configure-custom-tags-settings"></a>Configurare le impostazioni dei tag personalizzati

È possibile configurare le impostazioni dei tag seguenti per controllare il modo in cui vengono usati i tag personalizzati nell'organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Impostazioni di Teams** > .
2. In **Tagging** impostare quanto segue, a seconda delle esigenze dell'organizzazione.

    - **Consenti ai proprietari del team di ignorare chi può gestire i tag**: quando attivi questa impostazione, i proprietari del team possono impostare se i membri del team possono creare e gestire i tag all'interno di un team e il valore dei **tag viene gestito tramite** l'impostazione è il valore predefinito per ogni team. Se si disattiva questa impostazione, l'impostazione **Tag viene gestita da** non può essere modificata in base al team.
    - **Contrassegni predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti. È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri. I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.
    - **Consentire la creazione di tag personalizzati**: attivare questa impostazione per consentire agli utenti di aggiungere tag diversi da quelli predefiniti suggeriti. Se questa opzione è disattivata, gli utenti possono usare solo i tag predefiniti suggeriti. Se si disattiva questa opzione, assicurarsi di aggiungere uno o più contrassegni predefiniti.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gestire le impostazioni dei tag personalizzati per un team

Se hai attivato l'impostazione **Consenti ai proprietari del team di ignorare chi può gestire i tag** nell'interfaccia di amministrazione di Microsoft Teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team. A questo scopo, nella scheda **Impostazioni** di un team passare a **Contrassegni** e quindi scegliere chi può aggiungere contrassegni.

![Screenshot dell'impostazione dei tag a livello di team.](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usare i contrassegni

Ecco come aggiungere tag personalizzati e come configurare i tag tramite turno (se usi l'app Turni in Teams). Per altre informazioni, vedere [Uso dei tag in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Creare e assegnare tag personalizzati

Per creare e assegnare tag personalizzati, selezionare **Team** sul lato sinistro dell'app e quindi trovare il team nell'elenco. Seleziona **... Altre opzioni** e quindi scegliere **Gestisci contrassegni**. Qui è possibile creare tag e assegnarli alle persone del team.

![Screenshot che illustra come applicare tag nel client di Teams.](media/manage-tags-teams.png)

Per eliminare un tag, seleziona **... Altre opzioni** accanto al contrassegno e quindi selezionare **Elimina contrassegno**.

### <a name="set-up-tagging-by-shift"></a>Configurare l'aggiunta di tag tramite maiusc

L'aggiunta di tag tramite turno consente agli utenti di raggiungere le persone in turno in tempo reale. Teams assegna automaticamente agli utenti tag corrispondenti al nome del gruppo pianificare e turno dall'app Turni, abilitando la messaggistica dinamica basata sui ruoli. Le notifiche vengono inviate solo alle persone che sono in turno nel momento in cui viene usato un tag per avviare una chat o in un post del canale.

1. In Teams, passa [all'app Turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Creare [gruppi di turni](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e denominarli dopo un attributo, ad esempio un ruolo. Ad esempio, EngineerOnCall. Il nome del gruppo di turni sarà il nome del tag.
3. [Compilare un pianificare](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) assegnando turni ai membri dei team. Al termine, nell'angolo in alto a destra dell'app Turni seleziona **Condividi con il team**.
4. Attendere 15 minuti per i turni pianificati per popolare il servizio di tagging.
5. Usa il tag ovunque usi i tag in Teams.

## <a name="related-topics"></a>Argomenti correlati

[Uso dei tag in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gestire l'app Turni per l'organizzazione in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentazione della Guida di Turni](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
