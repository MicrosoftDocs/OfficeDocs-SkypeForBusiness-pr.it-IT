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
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft Teams per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti.
ms.openlocfilehash: 1173f5a626d6ea559dadd75149a0517f515d821b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51699311"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gestire i pacchetti di criteri in Microsoft Teams

Un Pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione. Sono stati creati pacchetti di criteri per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti all'interno dell'organizzazione.  

È possibile usare i [pacchetti di criteri inclusi in Teams](#policy-packages-included-in-teams) o creare pacchetti di criteri [personalizzati.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. È possibile gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare le funzionalità di Teams che si vogliono consentire o limitare per set specifici di persone all'interno dell'organizzazione. Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche per quel ruolo.

I pacchetti di criteri supportano i tipi di criteri di Teams seguenti:

- Criteri di messaggistica
- Criterio di riunione
- Criteri di configurazione delle app
- Criteri di chiamata
- Criteri per gli eventi live

## <a name="policy-packages-included-in-teams"></a>Pacchetti di criteri inclusi in Teams

Teams attualmente include i pacchetti di criteri seguenti.

| Nome pacchetto | Descrizione |
|---------|---------|
|Istruzione (studente di istruzione superiore)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti dell'istruzione superiore.|
|Istruzione (studente della scuola primaria)   |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti primari.|
|Istruzione (studente di scuola secondaria)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti secondari.         |
|Istruzione (docente)    |Crea un set di criteri e impostazioni dei criteri che si applicano ai docenti.      |
|Istruzione (docente della scuola primaria che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli insegnanti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Istruzione (studente della scuola primaria che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli studenti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Frontline Manager |Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea dell'organizzazione. |
|Operaio in prima linea |Crea un set di criteri e applica tali impostazioni ai lavoratori frontline dell'organizzazione. |
|Operatore sanitario  |Creare un set e impostazioni di criteri che forniscano agli operatori sanitari, ad esempio infermieri, medici e operatori sociali accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni. |
|Operatore dell'informazione sanitaria  |Crea un set di criteri e impostazioni di criteri che forniscono agli operatori dell'informazione, ad esempio personale in ambito IT e finanziario, responsabili della conformità, accesso completo alle chat, alle chiamate e alle riunioni.|
|Sale per i pazienti nell'organizzazione sanitaria  |Crea un set di criteri e impostazioni di criteri da applicare alle sale dei pazienti nell'organizzazione sanitaria.|
|Utente small e medium business (Business Voice) |Crea un criterio di configurazione dell'app che include le app per un'esperienza vocale aziendale.|
|Utente di piccole e medie imprese (senza Voce aziendale) |Crea un criterio di configurazione dell'app pertinente per gli utenti di Teams di piccole e medie imprese (esperienza vocale non aziendale).
|Responsabile della sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.|

> [!NOTE]
> Nelle versioni future di Teams verranno aggiunti altri pacchetti di criteri, quindi controllare di nuovo le informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.
Ad esempio, quando si assegna il pacchetto di criteri Education (Teacher) agli insegnanti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto di criteri Education (Teacher)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

**I pacchetti di criteri personalizzati non sono ancora disponibili per Government Community Cloud (GCC)**

I pacchetti di criteri personalizzati consentono di raggruppare il proprio set di criteri per gli utenti con ruoli simili nell'organizzazione. Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzato:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti criteri** e quindi fare clic su **Aggiungi.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina Pacchetti criteri nell'interfaccia di amministrazione":::

2. Immettere un nome e una descrizione per il pacchetto.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzato":::

3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.

4. Fare clic su **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

Di seguito viene descritto come usare i pacchetti di criteri nell'organizzazione.

![Panoramica dell'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- **[Visualizza:](#view-the-settings-of-a-policy-in-a-policy-package)** visualizzare i criteri in un pacchetto di criteri. Quindi, visualizzare le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Assicurarsi di aver compreso ogni impostazione. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli in modo che siano più restrittivi o meno in base alle esigenze dell'organizzazione.

    Se un criterio viene eliminato, è comunque possibile visualizzare le impostazioni, ma non modificarle. I criteri eliminati vengono ri-creati con le impostazioni predefinite quando si assegna il pacchetto di criteri.

- **[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.

- **[Assegna:](#assign-a-policy-package)** assegnare il pacchetto di criteri agli utenti.  

> [!NOTE]
> È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo aver assegnato un pacchetto. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare Pacchetti criteri **e** quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.

2. Fare clic sul criterio da visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

È possibile modificare le impostazioni di un criterio tramite **la** pagina Pacchetti criteri o passando direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams eseguire una delle operazioni seguenti:
    - Fare **clic su Pacchetti** criteri e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Fare clic sul tipo di criterio.  Ad esempio, fare clic su **Criteri di messaggistica.**

2. Selezionare il criterio da modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.

3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

È possibile assegnare un pacchetto di criteri a un singolo utente, a un gruppo o a un batch di utenti. Per altre informazioni su come assegnare pacchetti di criteri, vedere [Assegnare pacchetti di criteri a utenti e gruppi.](assign-policy-packages.md)

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare pacchetti di criteri](assign-policy-packages.md)
- [Pacchetti di criteri di Teams per gli amministratori di EDU](policy-packages-edu.md)
- [Pacchetti di criteri di Teams per il settore sanitario](policy-packages-healthcare.md)
- [Pacchetti di criteri di Teams per enti pubblici](policy-packages-gov.md)
