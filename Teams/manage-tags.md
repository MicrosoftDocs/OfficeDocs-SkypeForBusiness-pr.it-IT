---
title: Gestire i tag in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire i tag usati nell'organizzazione in Microsoft teams.
ms.openlocfilehash: 965de27b2671106bed4e5c877f26a7132bf61040
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940526"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gestire i tag in Microsoft Teams

> [!NOTE]
> Una delle caratteristiche descritte in questo articolo, **contrassegnate per turno**, non è ancora stata rilasciata. È stata annunciata e arriverà presto.Se si è un amministratore, è possibile scoprire quando questa funzionalità verrà rilasciata nel centro messaggi (nell'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/adminportal/home)). Per rimanere in primo piano sulle caratteristiche future per i team, consulta la [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Panoramica

I tag in Microsoft teams consentono agli utenti di connettersi in modo rapido e semplice con un sottoinsieme di persone in un team. È possibile creare e assegnare tag personalizzati per suddividere in categorie gli utenti in base agli attributi, ad esempio ruolo, progetto, abilità o posizione. In alternativa, i tag possono essere assegnati automaticamente agli utenti in base alle informazioni relative a pianificazione e spostamento nell' [app turni](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (presto disponibile). Dopo che un tag viene aggiunto a uno o più membri del team, può essere usato in @mentions da chiunque nel team in un post di canale o per avviare una conversazione solo con le persone a cui è stato assegnato il tag.

Come accennato in precedenza, esistono due tipi di tag in teams.

- **Tag personalizzati**: i proprietari del team e i membri del team (se la funzionalità è abilitata per gli utenti) possono creare e assegnare manualmente tag alle persone. Ad esempio, un tag "designer" o "radiologo" raggiungerà questi set di persone in un team senza dover digitare i loro nomi.
- **Tagging per turno** (presto disponibile): con questa funzionalità, agli utenti vengono assegnati automaticamente i tag che corrispondono al nome del gruppo pianificazione e spostamento nell' [app turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in teams. Ad esempio, il tag "EngineerOnCall" raggiunge tutti gli ingegneri che sono programmati in turni per lavorare quando il tag viene usato in una chat o in un post di canale. Con il contrassegno tramite turno, teams Elimina l'ipotesi di conoscere il nome del personale in turno quando gli utenti devono inoltrare rapidamente le informazioni. Il tagging per turno può anche essere supportato dai principali sistemi di gestione della forza lavoro, come JDA, Kronos e AMiON, tramite l'integrazione con i turni in teams. Per altre informazioni su come configurare questa funzionalità, vedere Configurare la [codifica tramite Maiusc](#set-up-tagging-by-shift-coming-soon).

> [!NOTE]
> I tag non sono ancora supportati nei canali privati. I tag non sono ancora disponibili nelle organizzazioni US Government community Cloud (GCC), GCC High o Department of Defense (DoD).

## <a name="how-tags-work"></a>Come funzionano i tag

Un tag può essere aggiunto manualmente o assegnato automaticamente a una persona in un team specifico. Può quindi essere usato in @mentions nella riga **a** in una chat o in un post su qualsiasi canale standard del team. Ecco alcuni esempi di come i tag possono essere usati in teams:

- Un responsabile dello Store pubblica un annuncio su un canale per inviare una notifica a tutti i cassieri.
- Un amministratore dell'ospedale Invia un messaggio a tutti i radiologi di un canale.
- Un responsabile marketing avvia una chat di gruppo con tutte le finestre di progettazione.
- Un infermiere Invia un messaggio a tutti i cardiologi di chiamata. (disponibile a breve)
- Un ingegnere di sistema pubblica un annuncio su un canale per inviare una notifica a tutti i tecnici del campo di spostamento. (disponibile a breve)

Quando un tag viene @mentioned in una conversazione di canale, i membri del team associati al tag riceveranno una notifica, come qualsiasi altra @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gestire i tag personalizzati per l'organizzazione

Come amministratore, puoi controllare il modo in cui i tag vengono usati in tutta l'organizzazione nell'interfaccia di amministrazione di Microsoft teams.

![Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams](media/manage-tags-admin-settings.png)

Un team può avere fino a 100 tag, fino a 100 i membri del team possono essere assegnati a un tag e può essere assegnato un massimo di 25 tag a un singolo utente. 

### <a name="set-who-can-add-custom-tags"></a>Impostare gli utenti che possono aggiungere tag personalizzati

Per impostazione predefinita, i proprietari del team possono aggiungere tag personalizzati. È possibile modificare questa impostazione per consentire ai proprietari del team e ai membri del team di creare, modificare, eliminare e gestire i tag oppure disattivare i tag per l'organizzazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su impostazioni **di Team impostazioni a livello di organizzazione**  >  **Teams settings**.
2. In **contrassegno**, accanto a **tag gestiti da**, selezionare una delle opzioni seguenti:

    - **Proprietari e membri del team**: consentire ai proprietari e ai membri del team di gestire i tag.
    - **Proprietari del team**: consentire ai proprietari del team di gestire i tag.
    - **Disabilitato**: disattivare i contrassegni.

### <a name="configure-custom-tags-settings"></a>Configurare le impostazioni di tag personalizzati

Puoi configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag personalizzati vengono usati nell'organizzazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, fare clic su impostazioni **di Team impostazioni a livello di organizzazione**  >  **Teams settings**.
2. In **tagging**impostare le operazioni seguenti in base alle esigenze dell'organizzazione.

    - **Consentire ai proprietari del team di ignorare chi può gestire i tag**: quando si attiva questa impostazione, i proprietari del team possono impostare se i membri del team possono creare e gestire i tag all'interno di un team e il valore dei **tag viene gestito** impostando il valore predefinito per ogni team. Se si disattiva questa impostazione, i **tag vengono gestiti** impostando non può essere modificata per ogni team.
    - **Tag predefiniti suggeriti**: usare questa opzione per aggiungere un set di tag predefiniti. È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri. I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.
    - **Consentire la creazione di tag personalizzati**: attivare questa impostazione per consentire agli utenti di aggiungere tag diversi dai tag predefiniti suggeriti impostati. Se questa opzione è disattivata, gli utenti possono usare solo i tag predefiniti suggeriti. Se si disattiva questa opzione, assicurarsi di aggiungere uno o più tag predefiniti.

## <a name="manage-custom-tags-settings-for-a-team"></a>Gestire le impostazioni dei tag personalizzati per un team

Se è stata attivata l'opzione **consentire ai proprietari del team di ignorare chi può gestire** le impostazioni dei tag nell'interfaccia di amministrazione di Microsoft teams, i proprietari del team possono impostare se i membri possono aggiungere tag a livello di team. A questo scopo, nella scheda **Impostazioni** di un team passa a **tag**e quindi scegli chi può aggiungere i tag.

![Screenshot dell'impostazione di tag a livello di Team](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usare i tag

Ecco come aggiungere tag personalizzati e come configurare i contrassegni per turno (se si usa l'app turni in teams). Per altre informazioni, vedere [usare i contrassegni in teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Creare e assegnare tag personalizzati

Per creare e assegnare tag personalizzati, selezionare **Teams** sul lato sinistro dell'app e quindi trovare il team nell'elenco. Selezionare **˙ ˙ ˙ altre opzioni**e quindi scegliere **Gestisci contrassegni**. In questo caso, è possibile creare i tag e assegnarli agli utenti del team.

![Screenshot che illustra come applicare i tag nel client Teams ](media/manage-tags-teams.png)

Per eliminare un contrassegno, selezionare **˙ ˙ ˙ altre opzioni** accanto al tag e quindi selezionare **Elimina contrassegno**.

### <a name="set-up-tagging-by-shift-coming-soon"></a>Configurare la codifica per turno (presto disponibile)

1. In teams passare all' [app turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Creare [gruppi di turni](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) e denominarli dopo un attributo, ad esempio un ruolo. Ad esempio, EngineerOnCall. Il nome del gruppo maiuscole sarà il nome del tag.
3. [Compilare una programmazione](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) assegnando i turni ai membri del team. Al termine, nell'angolo in alto a destra dell'app turni selezionare **Condividi con Team**.
4. Attendere 15 minuti per i turni pianificati per popolare il servizio di tagging.
5. Usa il tag ovunque usi i tag in teams.

La codifica tramite Shift consente agli utenti di raggiungere i turni di persone in tempo reale. Le notifiche vengono inviate solo alle persone che si trovano in turno quando viene usato un tag per avviare una chat o in un post di canale.

## <a name="related-topics"></a>Argomenti correlati

[Uso di tag in teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gestire l'app Turni per l'organizzazione in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Sposta la documentazione della Guida](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
