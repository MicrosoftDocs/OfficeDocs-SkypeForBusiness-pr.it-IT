---
title: Gestire i tag in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 2e099c611cbbfd22cc2cc32c189edc8243ea362d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711580"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gestire i tag in Microsoft Teams

## <a name="overview"></a>Panoramica

I tag in Microsoft Teams consentono agli utenti di connettersi in modo semplice e rapido a un sottoinsieme di persone di un team. È possibile creare e assegnare tag personalizzati per categorizzare le persone in base ad attributi, ad esempio ruolo, progetto, competenza o posizione. Oppure, i tag possono essere assegnati automaticamente alle persone in base alle informazioni sulla pianificazione e sul turno [nell'app Turni](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Dopo aver aggiunto un tag a uno o più membri del team, può essere usato in @mentions da chiunque nel team in un post del canale o per avviare una conversazione solo con le persone a cui è assegnato il tag.

Come accennato in precedenza, sono disponibili due tipi di tag Teams.

- **Tag personalizzati**: i proprietari del team e i membri del team (se la caratteristica è abilitata per loro) possono creare e assegnare manualmente i tag alle persone. Ad esempio, un tag "Designer" o "Radiologi" raggiungerà i set di persone di un team senza dover digitare i nomi.
- **Assegnazione di tag per** turno: con questa caratteristica, alle persone vengono assegnati automaticamente tag che corrispondono al nome del gruppo di turni e di pianificazione [nell'app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) Turni in Teams. Ad esempio, il tag "EngineerOnCall" raggiunge tutti i tecnici programmati in Turni per lavorare nel momento in cui il tag viene usato in una chat o in un post del canale. Con l'aggiunta di tag per turno, Teams le congetture non consentono di conoscere il nome del personale a turno quando gli utenti devono inoltrare rapidamente le informazioni. L'assegnazione di tag per turno può essere supportata anche dai principali sistemi di gestione della forza lavoro, come JDA, Kronos e AMiON, integrandoli con Turni in Teams. Per altre informazioni su come configurare questa funzionalità, vedere [Configurare l'assegnazione di tag per turno](#set-up-tagging-by-shift).

> [!NOTE]
> I tag non sono supportati nei canali privati o condivisi. I tag non sono disponibili nelle organizzazioni del Department of Defense (DoD). 

## <a name="how-tags-work"></a>Come funzionano i tag

Un tag può essere aggiunto manualmente o assegnato automaticamente a una persona in un team specifico. Può quindi essere usato in @mentions nella riga A in una chat  o in un post su qualsiasi canale standard del team. Ecco alcuni esempi di come è possibile usare i tag nelle Teams:

- Un responsabile del negozio pubblica un annuncio in un canale per informare tutti i cassieri.
- Un amministratore dell'ospedale invia un messaggio a tutti i radiologi di un canale.
- Un responsabile marketing avvia una chat di gruppo con tutti i progettisti.
- Un infermiere invia un messaggio a tutti i cardiologi a chiamata. (presto disponibile)
- Un tecnico di sistema pubblica un annuncio in un canale per informare tutti i tecnici del campo a turno. (presto disponibile)

Quando un tag viene @mentioned in una conversazione di canale, i membri del team associati al tag riceveranno una notifica, come qualsiasi altro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gestire tag personalizzati per l'organizzazione

Gli amministratori possono controllare il modo in cui i tag vengono usati nell'intera organizzazione nell'Microsoft Teams di amministrazione. Attualmente non è possibile usare PowerShell per gestire i tag.

![Screenshot delle impostazioni di tagging nell'Microsoft Teams di amministrazione.](media/manage-tags-admin-settings.png)

Un team può avere fino a 100 tag, fino a 100 membri del team possono essere assegnati a un tag e fino a 25 tag possono essere assegnati a un singolo utente. 

### <a name="set-who-can-add-custom-tags"></a>Impostare gli utenti che possono aggiungere tag personalizzati

Per impostazione predefinita, i proprietari del team possono aggiungere tag personalizzati. È possibile modificare questa impostazione per consentire ai proprietari del team e ai membri del team di creare, modificare, eliminare e gestire i tag oppure disattivare i tag per l'organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Impostazioni a** >  **livello di organizzazione Teams impostazioni**.
2. In **Tagging** selezionare una delle opzioni seguenti accanto a **Tag** gestiti da:

    - **Proprietari e membri del team**: consente ai proprietari e ai membri del team di gestire i tag.
    - **Proprietari del team**: consente ai proprietari del team di gestire i tag.
    - **Disabilitato**: disattiva i contrassegni.

### <a name="configure-custom-tags-settings"></a>Configurare le impostazioni dei tag personalizzati

È possibile configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag personalizzati vengono usati nell'organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Impostazioni a** >  **livello di organizzazione Teams impostazioni**.
2. In **Tagging** impostare quanto segue, a seconda delle esigenze dell'organizzazione.

    - **Consentire** ai proprietari del team di ignorare chi può gestire i tag: quando si attiva questa impostazione, i proprietari del team possono specificare se i membri del team possono creare e gestire i tag  all'interno di un team e il valore dell'impostazione Tag viene gestito dall'impostazione è il valore predefinito per ogni team. Se si disattiva questa impostazione **, l'impostazione** Contrassegni gestiti da non può essere modificata per ogni team.
    - **Tag predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti. È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri. I proprietari e i membri del team (se la caratteristica è abilitata per loro) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.
    - **Consentire la creazione di tag personalizzati**: attivare questa impostazione per consentire agli utenti di aggiungere tag diversi da quelli predefiniti suggeriti. Se questa opzione è disattivata, gli utenti possono usare solo i tag predefiniti suggeriti. Se si disattiva questa opzione, assicurarsi di aggiungere uno o più tag predefiniti.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gestire le impostazioni dei tag personalizzati per un team

Se è stata attivata l'impostazione Consenti ai proprietari del **team** di ignorare chi può gestire i tag nell'interfaccia di amministrazione di Microsoft Teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team. A questo scopo, nella scheda **Impostazioni** per un team passare a Contrassegni **e quindi** scegliere chi può aggiungere i contrassegni.

![Screenshot dell'impostazione dei tag a livello di team.](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usare i tag

Ecco come aggiungere tag personalizzati e come configurare il tagging per turno (se si usa l'app Turni in Teams). Per altre informazioni, vedere [Uso dei tag in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Creare e assegnare tag personalizzati

Per creare e assegnare tag personalizzati, **selezionare** Teams sul lato sinistro dell'app e quindi trovare il team nell'elenco. Selezionare **̇ ̇ ̇ Altre opzioni** e quindi scegliere **Gestisci tag**. Qui è possibile creare tag e assegnarli alle persone del team.

![Screenshot che illustra come applicare tag nel client Teams client.](media/manage-tags-teams.png)

Per eliminare un tag, **selezionare ̇ ̇ ̇ altre opzioni** accanto al tag e quindi selezionare **Elimina tag**.

### <a name="set-up-tagging-by-shift"></a>Configurare il tagging per turno

L'aggiunta di tag in base al turno consente agli utenti di raggiungere le persone a turno in tempo reale. Teams assegna automaticamente agli utenti i contrassegni corrispondenti alla pianificazione e al nome del gruppo di turni dall'app Turni, abilitando la messaggistica dinamica basata sui ruoli. Le notifiche vengono inviate solo alle persone che sono in turno nel momento in cui un tag viene usato per avviare una chat o in un post del canale. 

1. In Teams passare [all'app Turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Creare [gruppi di turni](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e assegnare loro un nome dopo un attributo, ad esempio un ruolo. Ad esempio, EngineerOnCall. Il nome del gruppo di turni sarà il nome del tag.
3. [Compilare una pianificazione](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) assegnando turni ai membri dei team. Al termine, nell'angolo in alto a destra dell'app Turni selezionare **Condividi con il team**.
4. Attendere 15 minuti che i turni pianificati popolano il servizio di tagging.
5. Usare il tag ovunque si usino i tag Teams.

## <a name="related-topics"></a>Argomenti correlati

[Uso di tag in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gestire l'app Turni per l'organizzazione in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentazione della Guida di Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
