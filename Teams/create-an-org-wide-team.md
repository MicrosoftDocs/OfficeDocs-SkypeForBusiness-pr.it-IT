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
description: Informazioni su come creare e gestire un team a livello di organizzazione in Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99acc2e1756c0915f404f6bf6b1bfab1e30fcaf6
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288734"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Creare un team a livello di organizzazione in Microsoft Teams

I team a livello di organizzazione forniscono agli utenti delle organizzazioni di piccole e medie dimensioni una modalità automatica di partecipazione a un singolo team per la collaborazione.

Con i team a livello di organizzazione, gli amministratori globali possono creare facilmente un team pubblico che include tutti gli utenti dell'organizzazione e mantiene l'appartenenza aggiornata con Active Directory man mano che gli utenti entrano nell'organizzazione o la lasciano. Solo gli amministratori globali possono creare team a livello di organizzazione. Attualmente, un team a livello di organizzazione è limitato alle organizzazioni con un massimo di 5.000 utenti. Esiste anche un limite di cinque team a livello di organizzazione per tenant. Se questi requisiti sono soddisfatti, gli amministratori globali vedranno l'opzione **A livello di organizzazione** quando selezionano **Crea un team da zero** durante la creazione di un team. 

![Screenshot dell'opzione per la creazione di un team a livello di organizzazione](media/create-org-wide-team.png "Screenshot dell'opzione per la creazione di un team a livello di organizzazione")

Quando viene creato un team a livello di organizzazione, tutti gli amministratori globali vengono aggiunti come proprietari del team e tutti gli utenti attivi vengono aggiunti come membri del team. Anche gli utenti senza licenza vengono aggiunti al team. La prima volta che un utente senza licenza accede a Teams, gli viene assegnata una licenza di valutazione Microsoft Teams Commercial Cloud Trial. Per altre informazioni sulla licenza di valutazione, vedere [Gestire l'offerta Microsoft Teams Commercial Cloud Trial](iw-trial-teams.md). 

Questi tipi di account non verranno aggiunti al team a livello di organizzazione:

- Account ai quali è impedito l'accesso
- Utenti guest
- Account di servizio
- Account di sale o attrezzature
- Account basati su una cassetta postale condivisa

Quando la directory dell'organizzazione viene aggiornata per includere nuovi utenti attivi oppure se alcuni gli utenti non lavorano più presso l'azienda e i loro account vengono disabilitati, le modifiche vengono sincronizzate automaticamente e gli utenti vengono aggiunti o rimossi dal team. I membri del team non possono abbandonare un team a livello di organizzazione. Il proprietario del team può aggiungere o rimuovere manualmente utenti, se necessario.

> [!NOTE]
> - Se si è un amministratore globale e l'opzione **A livello di organizzazione** non viene visualizzata durante la creazione di un team, è possibile che la funzionalità sia ancora in fase di distribuzione, che sia stato raggiunto il limite di cinque team a livello di organizzazione oppure che l'organizzazione abbia più dei 5.000 membri attualmente consentiti. Contiamo di aumentare il limite in futuro. I team a livello di organizzazione non sono ancora disponibili per Teams per l'istruzione.
> - Le sale che non fanno parte di un elenco di account di sale, attrezzature e risorse potrebbero essere aggiunte o sincronizzate con il team dell'organizzazione. I proprietari del team possono rimuovere facilmente questi account dal team.
> - Tutte le azioni del sistema per aggiungere o rimuovere membri sono pubblicate nel canale Generale. Inoltre, nel client di Teams sarà indicato che il canale ha nuove attività.
> - Se l'organizzazione non ha più di 5.000 utenti e ha appena implementato Teams, creeremo automaticamente un team a livello di organizzazione. Il nome del team rifletterà il nome del tenant e avrà un canale Generale. Gli amministratori globali possono modificare questo team come qualsiasi altro team. 

## <a name="best-practices"></a>Procedure consigliate

Per sfruttare al meglio un team a livello di organizzazione, si consiglia ai proprietari del team di eseguire le operazioni seguenti.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Consentire solo ai proprietari del team di pubblicare post nel canale Generale

Ridurre gli elementi di distrazione facendo pubblicare nel canale Generale solo i proprietari del team. Passare al team e fare clic su **˙˙˙ Altre opzioni** > **Gestisci il team**. Nella scheda **Impostazioni** fare clic su **Autorizzazioni dei membri** > selezionare **Solo i proprietari possono pubblicare messaggi**.

### <a name="turn-off-team-and-team-name-mentions"></a>Disattivare le menzioni @canale e @[nome canale]

 Ridurre le @menzioni per evitare di sovraccaricare l'organizzazione. Passare al team e fare clic su **˙˙˙ Altre opzioni** > **Gestisci il team**. Nella scheda **Impostazioni** fare clic su <strong>@menzioni</strong> > disattivare **Mostra ai membri la possibilità di utilizzare le menzioni @canale o @[nome canale]**. 

### <a name="automatically-show-important-channels"></a>Mostrare automaticamente i canali importanti

Mostrare canali importanti per assicurarsi che tutti gli utenti dell'organizzazione partecipino a specifiche conversazioni. Per altre informazioni, vedere [Canali preferiti automaticamente per l'intero team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurare la moderazione dei canali

Valutare l'opportunità di configurare la moderazione dei canali e di fornire capacità di moderazione ad alcuni membri del team. Quando è configurata la moderazione, i proprietari del team ricevono automaticamente le funzionalità moderatore. I moderatori possono controllare chi può creare un nuovo post in un canale, aggiungere e rimuovere moderatori, controllare se i membri del team possono rispondere ai messaggi esistenti nel canale e controllare se i bot e i connettori possono inviare messaggi nel canale. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Rimuovere gli account non idonei

Anche se i membri non possono abbandonare un team a livello di organizzazione, i proprietari del team possono gestire l'elenco dei partecipanti rimuovendo gli account che non dovrebbero appartenervi. **Assicurarsi di usare Teams per rimuovere gli utenti dal team a livello di organizzazione**. Se si usa un altro metodo, ad esempio si procede tramite l'interfaccia di amministrazione di Microsoft 365 o un gruppo in Outlook, l'utente potrebbe essere aggiunto di nuovo al team a livello di organizzazione.

## <a name="faq"></a>Domande frequenti

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Esiste un modo per creare un team a livello di organizzazione diverso dall'uso del client di Teams?

Gli amministratori globali possono creare un team a livello di organizzazione solo usando il client di Teams. Se l'organizzazione impone la creazione di team con PowerShell, la soluzione alternativa consigliata consiste nell'aggiungere gli amministratori globali al gruppo di sicurezza degli utenti che possono creare un team. Per altre informazioni, vedere [Gestire chi può creare gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Se questo non è possibile, è possibile usare PowerShell per creare un team pubblico e aggiungere un amministratore globale come proprietario del team. Quindi, l'amministratore globale deve fare clic su **Altre opzioni** accanto al nome del team, fare clic su **Modifica team** e modificare la privacy in **A livello di organizzazione: tutti gli utenti dell'organizzazione verranno aggiunti automaticamente**. Tenere presente che solo i proprietari del team possono accedere all'opzione **Modifica team** e solo gli amministratori globali possono vedere l'opzione **A livello di organizzazione**.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Esiste un modo per convertire un team esistente in un team a livello di organizzazione?

Gli amministratori globali possono convertire un team esistente in un team a livello di organizzazione modificandolo nel client di Teams. Passare al nome del team, fare clic su **Altre opzioni** > **Modifica team**.

## <a name="see-also"></a>Vedere anche

Guardare un video su come [creare un team a livello aziendale in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).
