---
title: Creare un team a livello di organizzazione in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e gestire un team a livello di organizzazione in teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: db7caa3879e016b6e8453ad151785578d2391dd1
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516651"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Creare un team a livello di organizzazione in Microsoft Teams

I team a livello di organizzazione rappresentano un modo automatico per consentire a tutti gli utenti di una società di piccole e medie dimensioni di partecipare a un singolo team per la collaborazione.

Con i team a livello di organizzazione, gli amministratori globali possono facilmente creare un team pubblico che si occupa di ogni utente dell'azienda e mantiene l'appartenenza aggiornata con Active Directory quando gli utenti partecipano e lasciano l'organizzazione. Solo gli amministratori globali possono creare team a livello di organizzazione e attualmente un team a livello di organizzazione è limitato alle organizzazioni che non hanno più di 5.000 utenti. Esiste anche un limite di cinque team per tenant a livello di organizzazione. Se questi requisiti sono soddisfatti, gli amministratori globali vedranno l' **intera organizzazione** come opzione quando scelgono di creare un team **da zero** durante la creazione di un team. 

![Screenshot dell'opzione a livello di organizzazione per creare un team a livello di organizzazione](media/create-org-wide-team.png "Screenshot dell'opzione a livello di organizzazione per creare un team a livello di organizzazione")

Quando viene creato un team a livello di organizzazione, tutti gli amministratori globali vengono aggiunti come proprietari del team e tutti gli utenti attivi vengono aggiunti come membri del team. Al team vengono aggiunti anche utenti senza licenza. La prima volta che un utente senza licenza accede a teams, all'utente viene assegnata una licenza per la versione di valutazione cloud commerciale di Microsoft teams. Per altre informazioni sulla licenza di valutazione, vedere [gestire l'offerta di valutazione cloud commerciale teams](iw-trial-teams.md). 

Questi tipi di account non verranno aggiunti al team a livello di organizzazione:

- Account bloccati dall'accesso
- Utenti Guest
- Account del servizio
- Account di sala o attrezzature
- Account supportato da una cassetta postale condivisa

Dato che la directory dell'organizzazione viene aggiornata per includere nuovi utenti attivi o se gli utenti non lavorano più presso la società e il loro account è disabilitato, le modifiche vengono sincronizzate automaticamente e gli utenti vengono aggiunti o rimossi dal team. I membri del team non possono uscire da un team a livello di organizzazione. In qualità di proprietario del team, è possibile aggiungere o rimuovere manualmente gli utenti, se necessario.

> [!NOTE]
> - Se non si vede l'opzione a **livello** di organizzazione quando si crea un team e si è un amministratore globale, è possibile che la caratteristica venga ancora distribuita, che sia stato raggiunto il limite di cinque team a livello di organigramma oppure che la società possa avere più del limite di dimensione corrente dei membri di 5.000. Stiamo cercando di aumentare questo limite in futuro.
> - Le camere che non fanno parte di un elenco di chat room, attrezzature e risorse potrebbero essere aggiunte o sincronizzate con il team a livello di organizzazione. I proprietari del team possono facilmente rimuovere questi account dal team.
> - Tutte le azioni del sistema per aggiungere o rimuovere membri vengono pubblicate nel canale generale. Il canale verrà contrassegnato anche come avente una nuova attività nel client teams.

## <a name="best-practices"></a>Procedure consigliate

Per ottenere il massimo dal team a livello di organizzazione, è consigliabile eseguire le operazioni seguenti per i proprietari del team.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Consentire solo ai proprietari del team di inserire il post nel canale generale

Per ridurre il rumore dei canali, è possibile inserire solo i proprietari del team nel canale generale. Accedere al team e fare clic su **˙ ˙ ˙ altre opzioni** > **Gestisci team**. Nella scheda **Impostazioni** fare clic su **autorizzazioni membro** > selezionare **solo i proprietari possono pubblicare messaggi**.

### <a name="turn-off-team-and-team-name-mentions"></a>Disattivare @team e @ [nome Team] menzioni

 Ridurre @mentions per evitare di sovraccaricare l'intera organizzazione. Accedere al team e fare clic su **˙ ˙ ˙ altre opzioni** > **Gestisci team**. Nella scheda **Impostazioni** fare clic su <strong>@mentions</strong> > disattivare **mostra membri l'opzione per @team o @ [nome Team]**. 

### <a name="automatically-favorite-important-channels"></a>Canali importanti Preferiti automaticamente

Canali principali preferiti per garantire che tutti gli utenti dell'organizzazione si impegnino in conversazioni specifiche. Per altre informazioni, Vedi [canali preferiti di auto per l'intero team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Configurare la moderazione del canale

Valuta la possibilità di configurare la moderazione dei canali e dare funzionalità di moderatore a determinati membri del team. Quando la moderazione è configurata, i proprietari del team ricevono automaticamente le funzionalità di moderatore. I moderatori possono controllare chi può avviare un nuovo post in un canale, aggiungere e rimuovere i moderatori, controllare se i membri del team possono rispondere ai messaggi del canale esistenti e controllare se i bot e i connettori possono inviare messaggi di canale. Per altre informazioni, vedere [configurare e gestire la moderazione dei canali in Microsoft teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Rimuovere gli account che potrebbero non appartenere

Anche se i membri non possono uscire da un team a livello di organizzazione, come proprietario del team, puoi gestire il roster del team rimuovendo gli account che non appartengono. Assicurarsi **di usare teams per rimuovere utenti dal team dell'organizzazione**. Se si usa un altro metodo per rimuovere un utente, ad esempio l'interfaccia di amministrazione di Microsoft 365 o da un gruppo in Outlook, l'utente potrebbe essere aggiunto al team dell'organizzazione.

## <a name="faq"></a>Domande frequenti

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Esiste un modo per creare un team a livello di organizzazione diverso dall'uso del client Teams?

Gli amministratori globali possono solo creare un team a livello di organizzazione usando il client teams. Se l'organizzazione limita la creazione di team all'uso di PowerShell, la soluzione alternativa consigliata consiste nell'aggiungere gli amministratori globali al gruppo di sicurezza degli utenti che possono creare un team. Per altre informazioni, vedere [Gestire chi può creare gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Se non si tratta di un'opzione, è possibile usare PowerShell per creare un team pubblico e aggiungere un amministratore globale come proprietario del team. Quindi, fare in modo che l'amministratore globale faccia clic su **altre opzioni** accanto al nome del team, fare clic su **modifica team**e quindi modificare la privacy in modo che **tutti gli utenti dell'organizzazione vengano aggiunti automaticamente**. Tieni presente che solo i proprietari del team possono accedere all'opzione **modifica team** e solo gli amministratori globali possono vedere l'opzione **a livello di organizzazione** .

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Esiste un modo per convertire un team esistente in un team a livello di organizzazione?

Gli amministratori globali possono convertire un team esistente in un team a livello di organizzazione mediante la modifica nel client teams. Vai al nome del team, fai clic su **altre opzioni** > **modifica team**.
