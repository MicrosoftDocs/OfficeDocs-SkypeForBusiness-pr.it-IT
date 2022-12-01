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
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come gestire l'uso dei tag nell'organizzazione in Microsoft Teams.
ms.openlocfilehash: ddf7956486db8bbd483ddde9d51c568450a7fe45
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199118"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gestire i tag in Microsoft Teams

I tag in Microsoft Teams consentono agli utenti di connettersi rapidamente e facilmente con un sottoinsieme di persone in un team. È possibile creare e assegnare tag personalizzati per categorizzare le persone in base ad attributi come ruolo, progetto, competenza o posizione. In alternativa, i tag possono essere assegnati automaticamente alle persone in base alla loro pianificazione e alle informazioni sui turni [nell'app Turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6). Dopo l'aggiunta di un tag a uno o più membri del team, può essere usato in @mentions da tutti i membri del team in un post di canale per notificare una conversazione solo alle persone a cui è stato assegnato.

Se sei proprietario di un team e vuoi gestire i tag nel tuo team, vedi [Uso dei tag in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

Come accennato in precedenza, ci sono due tipi di tag in Teams.

- **Tag personalizzati**: i proprietari e i membri del team (se hanno le autorizzazioni) possono creare e assegnare manualmente tag agli utenti. Ad esempio, un tag "Designer" o "Radiologist" raggiungerà questi gruppi di persone in un team senza doverne digitare i nomi.
- **Aggiunta di tag tramite turno**: con questa funzionalità, alle persone vengono assegnati automaticamente tag che corrispondono al nome del gruppo di pianificazione e turno [nell'app Turni](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) in Teams. Ad esempio, il tag "EngineerOnCall" raggiunge tutti i tecnici che sono pianificati in Turni per lavorare nel momento in cui il tag viene utilizzato in una chat o un post di canale. Con l'aggiunta di tag tramite turno, Teams elimina i tentativi di conoscere il nome del personale in turno quando gli utenti devono inoltrare rapidamente le informazioni.

> [!NOTE]
> I tag non sono supportati in canali privati o condivisi.

## <a name="how-tags-work"></a>Funzionamento dei tag

Un tag può essere aggiunto manualmente (tag personalizzato) o assegnato automaticamente a una persona in un team specifico (configurando Turni nell'app Turni). Il tag può quindi essere usato in @mentions nella riga **A** in una chat o in un post su qualsiasi canale standard del team. Ecco alcuni esempi di come i tag possono essere usati in Teams:

- Un responsabile dello Store pubblica un annuncio a un canale per informare tutti i cassieri.
- Un amministratore dell'ospedale invia un messaggio a tutti i radioologi in un canale.
- Un responsabile marketing avvia una chat di gruppo con tutti i progettisti.
- Un infermiere invia un messaggio a tutti i cardiologi di chiamata.
- Un tecnico di sistema pubblica un annuncio a un canale per inviare una notifica a tutti gli ingegneri sul campo in turno.

Quando un tag viene @mentioned in una conversazione del canale, i membri del team associati al tag riceveranno una notifica, proprio come qualsiasi altro @mention.

## <a name="manage-tags-for-your-organization"></a>Gestire i tag per l'organizzazione

Gli amministratori possono controllare il modo in cui i tag vengono usati nell'intera organizzazione nell'interfaccia di amministrazione di Microsoft Teams. Non è possibile usare PowerShell per gestire i tag.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Screenshot delle impostazioni di tagging nell'interfaccia di amministrazione di Microsoft Teams.":::

Un team può avere fino a 100 tag, a un tag possono essere assegnati fino a 200 membri del team e fino a 25 tag nello stesso team a un singolo utente.

### <a name="set-who-can-manage-tags"></a>Impostare chi può gestire i tag

Per impostazione predefinita, i proprietari del team possono creare, modificare ed eliminare tag. È possibile modificare l'impostazione **Chi può gestire i tag** per consentire ai proprietari e ai membri del team di gestire i tag oppure è possibile disattivare i tag per l'organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Impostazioni di Teams**\>.

2. In **Aggiunta di** tag, accanto a **Chi può gestire i tag**, selezionare una delle opzioni seguenti:

    - **Proprietari e membri** del team: consente ai proprietari e ai membri del team di gestire i tag.
    - **Proprietari del** team: consente ai proprietari del team di gestire i tag.
    - **Non abilitato**: disattivare i tag.

### <a name="configure-tagging-settings"></a>Configurare le impostazioni di tagging

È possibile configurare le impostazioni dei tag seguenti per controllare il modo in cui i tag vengono usati nell'intera organizzazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Impostazioni di Teams**\>.

2. In **Tagging** impostare quanto segue, a seconda delle esigenze dell'organizzazione.

    - **I proprietari del team possono modificare chi può gestire i tag**: quando si attiva questa impostazione, i proprietari del team possono specificare se i membri del team possono creare e gestire i tag all'interno di un team e il valore dell'impostazione **Chi può gestire i tag** è il valore predefinito per ogni team. Se si disattiva questa impostazione, l'impostazione **Chi può gestire i tag** non può essere modificata in base al team.
    - **Contrassegni suggeriti**: consente di aggiungere un set di contrassegni predefiniti. È possibile aggiungere fino a 25 tag e ogni tag può contenere un massimo di 25 caratteri. I proprietari e i membri del team (se la funzionalità è abilitata) possono usare questi suggerimenti, aggiungerli o creare un nuovo set di tag.
    - **Tag personalizzati**: attivare questa impostazione per consentire agli utenti di aggiungere tag diversi da quelli predefiniti suggeriti. Se questa opzione è disattivata, gli utenti possono usare solo i tag predefiniti suggeriti. Se si disattiva questa opzione, assicurarsi di aggiungere uno o più contrassegni predefiniti.
    - **L'app Turni può applicare tag**: attiva questa impostazione per abilitare l'app Turni per assegnare automaticamente i tag alle persone che sono in turno in tempo reale. Questi tag corrisponderanno alla pianificazione e al nome del gruppo di un utente in Turni. Le notifiche vengono inviate solo alle persone spostate nel momento in cui il tag viene usato in una chat o in un post del canale.

## <a name="related-topics"></a>Argomenti correlati

[Gestire l'app Turni](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentazione della Guida di Turni](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
