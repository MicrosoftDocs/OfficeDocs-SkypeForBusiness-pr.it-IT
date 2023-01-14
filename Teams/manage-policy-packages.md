---
title: Gestire i pacchetti di criteri in Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare, gestire e personalizzare i pacchetti di criteri in Microsoft Teams per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti.
ms.openlocfilehash: 79e9bd09745d5d691abe468acf78f6b1ebf453d1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69807466"
---
# <a name="managing-policy-packages-in-teams"></a>Gestione di pacchetti di criteri in Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Un Pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione. I pacchetti di criteri sono stati creati per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti all'interno dell'organizzazione.  

È possibile usare i [pacchetti di criteri inclusi in Teams](#policy-packages-included-in-teams) o [creare pacchetti di criteri personalizzati](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione." lightbox="media/policy-packages-admin-center.png":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutte le impostazioni vengono aggiornate per tutti gli utenti assegnati al pacchetto. È possibile gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare le funzionalità di Teams che si vogliono consentire o limitare per gruppi specifici di persone all'interno dell'organizzazione. Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri e impostazioni dei criteri predefiniti che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.

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
|Responsabile in prima linea |Crea un set di criteri e applica tali impostazioni ai responsabili della prima linea dell'organizzazione. |
|Personale in prima linea |Crea un set di criteri e applica tali impostazioni ai frontline worker dell'organizzazione. |
|Operatore sanitario  |Creare un set e impostazioni di criteri che forniscano agli operatori sanitari, ad esempio infermieri, medici e operatori sociali accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni. |
|Operatore dell'informazione sanitaria  |Crea un set di criteri e impostazioni di criteri che forniscono agli operatori dell'informazione, ad esempio personale in ambito IT e finanziario, responsabili della conformità, accesso completo alle chat, alle chiamate e alle riunioni.|
|Sale per i pazienti nell'organizzazione sanitaria  |Crea un set di criteri e impostazioni di criteri da applicare alle sale dei pazienti nell'organizzazione sanitaria. |
|Responsabile della sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.|
|Utente di piccole e medie imprese (Business Voice) |Crea un criterio di configurazione dell'app che include le app per un'esperienza vocale aziendale per gli utenti.|
|Utente di piccole e medie imprese (senza Business Voice) |Crea criteri di configurazione delle app rilevanti per gli utenti di Teams aziendali di piccole e medie dimensioni senza funzionalità vocali aziendali.

> [!NOTE]
> Verranno aggiunti altri pacchetti di criteri nelle versioni future di Teams, quindi controllare di nuovo la disponibilità di informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.
Ad esempio, quando si assegna il pacchetto di criteri Istruzione (docenti) agli insegnanti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

:::image type="content" source="media/teams-policy-packages-education.png" alt-text="Screenshot del pacchetto di criteri Istruzione (docenti)." lightbox="media/teams-policy-packages-education.png":::

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

> [!NOTE]
> I pacchetti di criteri personalizzati richiedono Teams Premium.

I pacchetti di criteri personalizzati consentono di raggruppare un set di criteri personalizzato per gli utenti con ruoli simili nell'organizzazione. Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzato:

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti criteri** e quindi fare clic su **Aggiungi**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina Pacchetti di criteri nell'interfaccia di amministrazione." lightbox="media/policy-packages-add.png":::

2. Immetti un nome e una descrizione per il pacchetto.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzato." lightbox="media/policy-packages-add-custom.png":::

3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.

4. Selezionare **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

Di seguito viene illustrato come usare i pacchetti di criteri nell'organizzazione.

![Panoramica su come usare i pacchetti di criteri.](media/manage-policy-packages-overview.png)

- **[Visualizzazione](#view-the-settings-of-a-policy-in-a-policy-package)**: visualizzare i criteri in un pacchetto di criteri. Quindi, visualizzare le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Assicurati di comprendere ogni impostazione. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario cambiarli in modo che siano più restrittivi o meno in base alle esigenze dell'organizzazione.

    Se un criterio viene eliminato, è comunque possibile visualizzare le impostazioni, ma non modificarle. I criteri eliminati vengono ricreati con le impostazioni predefinite quando si assegna il pacchetto di criteri.

- **[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.

- **[Assegna](#assign-a-policy-package)**: assegnare il pacchetto di criteri agli utenti.  

> [!NOTE]
> È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo l'assegnazione di un pacchetto. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti di** criteri e quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.

2. Selezionare il criterio da visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

È possibile modificare le impostazioni di un criterio tramite la pagina **Pacchetti di criteri** o passando direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Microsoft Teams eseguire una delle operazioni seguenti:
    - Selezionare **Pacchetti di criteri** e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Selezionare il tipo di criterio.  Ad esempio, fare clic su **Criteri di messaggistica**.

2. Selezionare il criterio da modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.

3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

È possibile assegnare un pacchetto di criteri a un singolo utente, un gruppo o un batch di utenti. Per altre informazioni su come assegnare pacchetti di criteri, vedere [Assegnare pacchetti di criteri a utenti e gruppi](assign-policy-packages.md).

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare pacchetti di criteri](assign-policy-packages.md)
- [Pacchetti di criteri di Teams per gli amministratori EDU](policy-packages-edu.md)
- [Pacchetti di criteri di Teams per il settore sanitario](policy-packages-healthcare.md)
- [Pacchetti di criteri di Teams per enti pubblici](policy-packages-gov.md)
