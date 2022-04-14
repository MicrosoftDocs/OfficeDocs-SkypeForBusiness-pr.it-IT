---
title: Gestire pacchetti di criteri in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare e gestire pacchetti di criteri in Microsoft Teams per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti.
ms.openlocfilehash: 173d5d1488196ea048a64ce12916f8115362c572
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "63055306"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>Gestire pacchetti di criteri per Microsoft Teams

Un Pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione. I pacchetti di criteri sono stati creati per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti all'interno dell'organizzazione.  

È possibile usare i [pacchetti di criteri inclusi in Teams](#policy-packages-included-in-teams) o [creare pacchetti di criteri personalizzati](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione.":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutte le impostazioni vengono aggiornate per tutti gli utenti assegnati al pacchetto. Per gestire i pacchetti di criteri, è possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

> [!NOTE]
> Questa caratteristica è temporaneamente disponibile in anteprima pubblica per tutti i clienti Microsoft Teams. Per ottenere questa funzionalità dopo l'anteprima, ogni utente avrà bisogno della licenza per il componente aggiuntivo Advanced Communications. Per ulteriori informazioni, vedere [Componente aggiuntivo per comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare Teams caratteristiche da consentire o limitare per gruppi specifici di persone all'interno dell'organizzazione. Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri e impostazioni dei criteri predefiniti che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.

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
|Istruzione (studenti di istruzione superiore)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti dell'istruzione superiore.|
|Istruzione (studente della scuola primaria)   |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti primari.|
|Istruzione (studente della scuola secondaria)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti secondari.         |
|Istruzione (docente)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli insegnanti.      |
|Istruzione (insegnante della scuola primaria che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli insegnanti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Istruzione (studente della scuola primaria che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli studenti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Gestore in prima linea |Crea un set di criteri e applica tali impostazioni ai responsabili della prima linea dell'organizzazione. |
|Frontline worker |Crea un set di criteri e applica tali impostazioni ai frontline worker dell'organizzazione. |
|Operatore sanitario  |Creare un set e impostazioni di criteri che forniscano agli operatori sanitari, ad esempio infermieri, medici e operatori sociali accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni. |
|Operatore dell'informazione sanitaria  |Crea un set di criteri e impostazioni di criteri che forniscono agli operatori dell'informazione, ad esempio personale in ambito IT e finanziario, responsabili della conformità, accesso completo alle chat, alle chiamate e alle riunioni.|
|Sale per i pazienti nell'organizzazione sanitaria  |Crea un set di criteri e impostazioni di criteri da applicare alle sale dei pazienti nell'organizzazione sanitaria.|
|Utente di piccole e medie imprese (Teams Sistema telefonico con bundle di piani per chiamate) |Crea un criterio di configurazione dell'app che include le app per un Teams Sistema telefonico con l'esperienza bundle del piano per chiamate.|
|Utente di piccole e medie imprese (senza Teams Sistema telefonico con bundle di piani per chiamate) |Crea criteri di configurazione delle app rilevanti per le piccole e medie imprese Teams gli utenti (non Teams Sistema telefonico con l'esperienza di aggregazione del piano per chiamate).
|Responsabile della sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.|

> [!NOTE]
> Verranno aggiunti altri pacchetti di criteri nelle versioni future di Teams, quindi controllare di nuovo la disponibilità delle informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.
Ad esempio, quando si assegna il pacchetto di criteri Istruzione (docenti) agli insegnanti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto di criteri Istruzione (docenti).](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

I pacchetti di criteri personalizzati consentono di raggruppare un set di criteri personalizzato per gli utenti con ruoli simili nell'organizzazione. Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzato:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti di criteri** e quindi fare clic su **Aggiungi**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina Pacchetti di criteri nell'interfaccia di amministrazione.":::

2. Immetti un nome e una descrizione per il pacchetto.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzato.":::

3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.

4. Fare clic su **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

Di seguito viene illustrato come usare i pacchetti di criteri nell'organizzazione.

![Panoramica su come usare i pacchetti di criteri.](media/manage-policy-packages-overview.png)

- **[Visualizzazione](#view-the-settings-of-a-policy-in-a-policy-package)**: visualizzare i criteri in un pacchetto di criteri. Quindi, visualizzare le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Assicurati di comprendere ogni impostazione. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario cambiarli in modo che siano più restrittivi o meno in base alle esigenze dell'organizzazione.

    Se un criterio viene eliminato, è comunque possibile visualizzare le impostazioni, ma non modificarle. I criteri eliminati vengono ricreati con le impostazioni predefinite quando si assegna il pacchetto di criteri.

- **[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.

- **[Assegna](#assign-a-policy-package)**: assegnare il pacchetto di criteri agli utenti.  

> [!NOTE]
> È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo l'assegnazione di un pacchetto. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti** di criteri e quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.

2. Fare clic sul criterio da visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

È possibile modificare le impostazioni di un criterio tramite la pagina **Pacchetti** di criteri o direttamente nella pagina dei criteri nell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams eseguire una delle operazioni seguenti:
    - Fare clic su **Pacchetti di criteri** e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Fare clic sul tipo di criterio.  Ad esempio, fare clic su **Criteri di messaggistica**.

2. Selezionare il criterio da modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.

3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

È possibile assegnare un pacchetto di criteri a un singolo utente, un gruppo o un batch di utenti. Per altre informazioni su come assegnare pacchetti di criteri, vedere [Assegnare pacchetti di criteri a utenti e gruppi](assign-policy-packages.md).

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare pacchetti di criteri](assign-policy-packages.md)
- [Pacchetti di criteri di Teams per gli amministratori EDU](policy-packages-edu.md)
- [Pacchetti di criteri di Teams per il settore sanitario](policy-packages-healthcare.md)
- [pacchetti politici Teams per il governo](policy-packages-gov.md)
