---
title: Creare un team a livello di organizzazione in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e gestire un team a livello di organizzazione in Teams per fornire un modo automatico a tutti gli utenti di un'organizzazione di piccole e medie dimensioni di collaborare.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8a45da6af484209fcae5569d52ad03476b9ead4ff6da266d6ca5925c0be815b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337984"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>Creare un team a livello di organizzazione in Microsoft Teams

I team a livello di organizzazione consentono a tutti gli utenti di un'organizzazione di piccole e medie dimensioni di far parte di un unico team collaborativo.

Con i team a livello di organizzazione, gli amministratori globali possono creare facilmente un team pubblico con le caratteristiche seguenti:
- Estrae tutti gli utenti dell'organizzazione 
- Mantiene aggiornata l'appartenenza ad Active Directory quando gli utenti aderiscono e abbandonano l'organizzazione.

Solo gli amministratori globali possono creare team a livello di organizzazione. Attualmente, un team a livello di organizzazione è limitato alle organizzazioni con non più di 10.000 utenti. Esiste anche un limite di cinque team a livello di organizzazione per ogni tenant. Quando si crea un team, se questi requisiti vengono soddisfatti, gli amministratori globali vedono **a** livello di organizzazione un'opzione quando selezionano **Crea un team da zero.** 

![Screenshot dell'opzione a livello di organizzazione per creare un team a livello di organizzazione](media/create-org-wide-team.png "Schermata dell'opzione a livello di organizzazione per creare un team a livello di organizzazione")

Quando viene creato un team a livello di organizzazione, tutti gli amministratori globali e gli amministratori dei servizi Teams vengono aggiunti come proprietari del team e tutti gli utenti attivi vengono aggiunti come membri del team. Anche gli utenti senza licenza vengono aggiunti al team. La prima volta che un utente senza licenza accede a Teams, all'utente viene assegnata una Microsoft Teams Exploratory. Per altre informazioni sulla licenza Esplorativa, vedere Gestire [la licenza esplorativa Microsoft Teams esplorativa](teams-exploratory.md). 

I tipi di account seguenti non verranno aggiunti al team a livello di organizzazione:

- Account ai quali è impedito l'accesso
- Utenti guest
- Account delle risorse o del servizio, ad esempio account associati a operatori automatici e code di chiamata
- Account di sale o attrezzature
- Account basati su una cassetta postale condivisa

Quando la directory dell'organizzazione viene aggiornata per includere nuovi utenti attivi o per disabilitare gli account degli utenti che non lavorano più nell'azienda, le modifiche vengono sincronizzate automaticamente e gli utenti vengono aggiunti o rimossi dal team. I membri del team non possono uscire da un team a livello di organizzazione. Il proprietario del team può aggiungere o rimuovere manualmente utenti, se necessario.

> [!NOTE]
> - Se l'opzione A  livello di organizzazione non è visualizzata quando si crea un team e si è un amministratore globale, è possibile che sia stato raggiunto il limite di cinque team a livello di organizzazione oppure che l'organizzazione abbia più del limite di dimensioni corrente di 10.000 membri. Contiamo di aumentare il limite in futuro. I team a livello di organizzazione non sono ancora disponibili per Teams per l'istruzione.
> - Le chat room che non fanno parte di un elenco di chat room, apparecchiature e account delle risorse potrebbero essere aggiunte o sincronizzate con il team a livello di organizzazione. I proprietari del team possono rimuovere facilmente questi account dal team.
> - Tutte le azioni del sistema per aggiungere o rimuovere membri sono pubblicate nel canale Generale. Inoltre, nel client di Teams sarà indicato che il canale ha nuove attività.
> - Verrà creato automaticamente un team a livello di organizzazione per l'organizzazione se l'organizzazione non ha più di Teams e non ha più di 5.000 utenti. Il nome del team rifletterà il nome del tenant e avrà un canale Generale. Gli amministratori globali possono modificare questo team come qualsiasi altro team.

## <a name="best-practices"></a>Procedure consigliate

Per ottenere il massimo dal team a livello di organizzazione, è consigliabile che i proprietari del team esercitino le attività seguenti:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Consentire solo ai proprietari del team di pubblicare post nel canale Generale

Ridurre gli elementi di distrazione facendo pubblicare nel canale Generale solo i proprietari del team. 

1. Passare al team, individuare il canale Generale e quindi selezionare ̇ ̇ ̇ **Altre opzioni**  >  **Gestisci canale**. 
2. Nella scheda **Impostazioni canale fare** clic su **Autorizzazioni** e quindi selezionare Solo i proprietari **possono pubblicare messaggi.**

### <a name="turn-off-team-and-team-name-mentions"></a>Disattivare le menzioni @canale e @[nome canale]

Ridurre le @menzioni per evitare di sovraccaricare l'organizzazione. 

1. Passare al team e fare clic su **˙˙˙ Altre opzioni** > **Gestisci il team**. 
2. Nella scheda **Impostazioni** fare clic su <strong>@menzioni</strong> > disattivare **Mostra ai membri la possibilità di utilizzare le menzioni @canale o @[nome canale]**. 

### <a name="automatically-show-important-channels"></a>Mostrare automaticamente i canali importanti

Mostrare canali importanti per assicurarsi che tutti gli utenti dell'organizzazione partecipino a specifiche conversazioni. Per altre informazioni, vedere [Canali preferiti automaticamente per l'intero team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurare la moderazione dei canali

Valutare l'opportunità di configurare la moderazione dei canali e di fornire capacità di moderazione ad alcuni membri del team. Quando è impostata la moderazione, ai proprietari del team vengono automaticamente fornite le funzionalità di moderatore. I moderatori possono:

- Controllare chi può avviare un nuovo post in un canale
- Aggiungere e rimuovere moderatori
- Controllare se i membri del team possono rispondere ai messaggi del canale esistenti
- Controllare se bot e connettori possono inviare messaggi di canale.

Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Rimuovere gli account non idonei

Anche se i membri non possono lasciare un team a livello di organizzazione, come proprietario del team, è possibile gestire l'elenco dei team rimuovendo gli account che non appartengono. **Assicurarsi di usare Teams per rimuovere gli utenti dal team a livello di organizzazione**. Se si usa un altro modo per rimuovere un utente, ad esempio il interfaccia di amministrazione di Microsoft 365 o da un gruppo in Outlook, l'utente potrebbe essere aggiunto di nuovo al team a livello di organizzazione.

## <a name="faq"></a>Domande frequenti

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>Esiste un modo per creare un team a livello di organizzazione diverso dall'Teams client?

Solo gli amministratori globali possono creare un team a livello di organizzazione usando il client Teams globale. Se l'organizzazione impone la creazione di team con PowerShell, la soluzione alternativa consigliata consiste nell'aggiungere gli amministratori globali al gruppo di sicurezza degli utenti che possono creare un team.

Per altre informazioni, vedere [Gestire gli utenti che possono creare gruppi.](/microsoft-365/admin/create-groups/manage-creation-of-groups)

Se questa soluzione alternativa non è un'opzione, è possibile usare PowerShell per creare un team pubblico e aggiungere un amministratore globale come proprietario del team. Quindi, l'amministratore globale deve fare clic su **Altre opzioni** accanto al nome del team, fare clic su **Modifica team** e modificare la privacy in **A livello di organizzazione: tutti gli utenti dell'organizzazione verranno aggiunti automaticamente**. 

> [!NOTE]
> Solo i proprietari del team possono accedere all'opzione **Modifica team** e solo gli amministratori globali possono vedere **l'opzione a livello di** organizzazione.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>Esiste un modo per convertire un team esistente in un team a livello di organizzazione?

Gli amministratori globali possono convertire un team esistente in un team a livello di organizzazione modificandolo nel client Teams globale. Passare al nome del team, fare clic su **Altre opzioni** > **Modifica team**.

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>È possibile creare un team a livello di organizzazione usando un modello di team?

I modelli di team non possono essere usati per creare un team a livello di organizzazione. Il lavoro per questa caratteristica è in corso. 

## <a name="see-also"></a>Vedere anche

Guardare un video sulla creazione di un team a livello aziendale [in Microsoft Teams.](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)
