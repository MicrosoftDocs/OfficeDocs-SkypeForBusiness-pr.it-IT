---
title: Gestire i pacchetti di criteri in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft Teams per semplificare, semplificare e fornire coerenza durante la gestione dei criteri per gruppi di utenti.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341787"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gestire i pacchetti di criteri in Microsoft Teams

Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri predefiniti e impostazioni dei criteri che è possibile assegnare agli utenti con ruoli simili nell'organizzazione. Abbiamo creato pacchetti di criteri per semplificare, semplificare e garantire coerenza durante la gestione dei criteri per gruppi di utenti all'interno dell'organizzazione.  

Puoi usare i [pacchetti di criteri inclusi in Teams](#policy-packages-included-in-teams) o creare pacchetti di criteri [personalizzati.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutti gli utenti assegnati a tale pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti di criteri usando l'Microsoft Teams di amministrazione o PowerShell.You manage policy packages by using the Microsoft Teams admin center or PowerShell.

> [!NOTE]
> Ogni utente richiederà il componente aggiuntivo Advanced Communications per ricevere un'assegnazione di pacchetto di criteri personalizzati. Per ulteriori informazioni, vedere [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare Teams funzionalità che si desidera consentire o limitare per gruppi specifici di persone all'interno dell'organizzazione. Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.

I pacchetti di criteri supportano i Teams seguenti:

- Criteri di messaggistica
- Criteri riunione
- Criteri di configurazione dell'app
- Criteri di chiamata
- Criteri per gli eventi live

## <a name="policy-packages-included-in-teams"></a>Pacchetti di criteri inclusi in Teams

Teams attualmente include i pacchetti di criteri seguenti.

| Nome del pacchetto | Descrizione |
|---------|---------|
|Education (Higher education student)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti dell'istruzione superiore.|
|Education (Primary school student)   |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti primari.|
|Education (Secondary school student)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti secondari.         |
|Education (Teacher)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli insegnanti.      |
|Istruzione (insegnante della scuola primaria che usa l'apprendimento remoto)    |Crea un set di criteri che si applicano agli insegnanti principali per ottimizzare la sicurezza e la collaborazione degli studenti quando si usa l'apprendimento remoto.      |
|Education (Primary school student using remote learning)    |Crea un set di criteri che si applicano agli studenti primari per ottimizzare la sicurezza e la collaborazione degli studenti quando si usa l'apprendimento remoto.      |
|Frontline Manager |Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea nell'organizzazione. |
|Lavoratore in prima linea |Crea un set di criteri e applica tali impostazioni ai lavoratori frontline dell'organizzazione. |
|Operatore sanitario  |Crea un set di criteri e impostazioni di criteri che offrono agli operatori sanitari, ad esempio infermieri registrati, infermieri, medici e operatori sociali l'accesso completo a chat, chiamate, gestione dei turni e riunioni. |
|Information Worker per il settore sanitario  |Crea un set di criteri e impostazioni dei criteri che forniscono agli information worker, ad esempio personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo a chat, chiamate e riunioni.|
|Sala operatoria per pazienti  |Crea un set di criteri e impostazioni dei criteri che si applicano alle sale pazienti nell'organizzazione sanitaria.|
|Utente di piccole e medie imprese (Business Voice) |Crea un criterio di configurazione dell'app che include le app per un'esperienza vocale aziendale.|
|Utente di piccole e medie imprese (senza Business Voice) |Crea un criterio di configurazione dell'app pertinente per un'azienda di piccole e medie Teams utenti (esperienza non business voice).
|Responsabile della sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.|

> [!NOTE]
> Aggiungeremo altri pacchetti di criteri nelle versioni future di Teams, quindi controlla di nuovo per le informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.
Ad esempio, quando assegni il pacchetto di criteri Education (Teacher) agli insegnanti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto di criteri Education (Teacher)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

**I pacchetti di criteri personalizzati non sono ancora disponibili per Government Community Cloud (GCC)**

I pacchetti di criteri personalizzati ti consentono di aggregare il tuo set di criteri per gli utenti con ruoli simili nell'organizzazione. Crea pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzati:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione selezionare **Pacchetti di** criteri e quindi fare clic su **Aggiungi.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot of Add button on Policy packages page in the admin center":::

2. Immetti un nome e una descrizione per il pacchetto.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot of adding a new custom policy package":::

3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.

4. Fare clic su **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

Di seguito viene descritto come usare i pacchetti di criteri nell'organizzazione.

![Panoramica su come usare i pacchetti di criteri](media/manage-policy-packages-overview.png)

- **[Visualizza](#view-the-settings-of-a-policy-in-a-policy-package)**: consente di visualizzare i criteri in un pacchetto di criteri. Quindi, visualizza le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Assicurati di aver compreso ogni impostazione. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli in modo da essere più restrittivi o meno in base alle esigenze dell'organizzazione.

    Se un criterio viene eliminato, è comunque possibile visualizzare le impostazioni, ma non sarà possibile modificare alcuna impostazione. Un criterio eliminato viene ri-creato con le impostazioni predefinite quando assegni il pacchetto di criteri.

- **[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.

- **[Assegna](#assign-a-policy-package)**: assegna il pacchetto di criteri agli utenti.  

> [!NOTE]
> Puoi anche modificare le impostazioni dei criteri in un pacchetto di criteri dopo aver assegnato un pacchetto. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'Microsoft Teams di amministrazione.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione seleziona Pacchetti di criteri **e** quindi seleziona un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.

2. Fare clic sul criterio che si desidera visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

Puoi modificare le impostazioni di un criterio tramite **la** pagina Pacchetti di criteri o andando direttamente alla pagina dei criteri nell'interfaccia di amministrazione Microsoft Teams sicurezza.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, eseguire una delle operazioni seguenti:
    - Fai **clic su** Pacchetti di criteri e quindi seleziona il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Fare clic sul tipo di criterio.  Ad esempio, fare clic su **Criteri di messaggistica**.

2. Selezionare il criterio da modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.

3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

Puoi assegnare un pacchetto di criteri a un singolo utente, a un gruppo o a un batch di utenti. Per altre informazioni su come assegnare pacchetti di criteri, vedi [Assegnare pacchetti di criteri a utenti e gruppi.](assign-policy-packages.md)

## <a name="related-topics"></a>Argomenti correlati

- [Assegna pacchetti di criteri](assign-policy-packages.md)
- [Teams dei criteri per gli amministratori EDU](policy-packages-edu.md)
- [Teams dei criteri sanitari](policy-packages-healthcare.md)
- [Teams dei criteri per enti pubblici](policy-packages-gov.md)
