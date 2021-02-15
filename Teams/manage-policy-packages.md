---
title: Gestire i pacchetti dei criteri in Microsoft Teams
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
ms.openlocfilehash: 395b0f2c05278224bf024c1cf3e453a2f51bd725
ms.sourcegitcommit: de7d0807186a64dfe1cca15d34c39bdbad6af836
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50085184"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gestire i pacchetti dei criteri in Microsoft Teams

> [!NOTE]
> Una delle caratteristiche illustrate in questo articolo, pacchetti di [criteri](#custom-policy-packages)personalizzati, è attualmente in anteprima privata.

Un pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione. Sono stati creati pacchetti di criteri per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti nell'organizzazione.  

Puoi usare i pacchetti [dei criteri inclusi in Teams](#policy-packages-included-in-teams) o creare pacchetti di criteri [personalizzati](#custom-policy-packages) (in anteprima privata).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. È possibile gestire i pacchetti dei criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri ti consentono di controllare le funzionalità di Teams che vuoi consentire o limitare per gruppi specifici di persone all'interno dell'organizzazione. Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche di quel ruolo.

I pacchetti dei criteri supportano i tipi di criteri di Teams seguenti:

- Criteri di messaggistica
- Criterio di riunione
- Criteri di configurazione delle app
- Criteri di chiamata
- Criteri per gli eventi live

## <a name="policy-packages-included-in-teams"></a>Pacchetti dei criteri inclusi in Teams

Teams attualmente include i pacchetti di criteri seguenti.

|**Nome pacchetto**  |**Descrizione** |
|---------|---------|
|Education (studente del settore dell'istruzione superiore)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti del settore dell'istruzione superiore.|
|Education (studente della scuola primaria)   |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti primari.|
|Education (studente di un istituto di istruzione secondario)    |Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti secondari.         |
|Education (docente)    |Crea un set di criteri e impostazioni dei criteri che si applicano ai docenti.      |
|Education (insegnante della scuola elementare che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli insegnanti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Education (studente della scuola elementare che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli studenti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Frontline manager |Crea un set di criteri e applica queste impostazioni ai responsabili della linea in prima linea nell'organizzazione. |
|Frontline worker |Crea un set di criteri e applica queste impostazioni ai dipendenti in prima linea nell'organizzazione. |
|Operatore medico  |Crea un set di criteri e impostazioni dei criteri che conferiranno a operatori clinici come infermieri specializzati, infermieri con addebito, medici e social worker l'accesso completo a chat, chiamate, gestione dei turni e riunioni. |
|Information Worker sanitario  |Crea un set di criteri e impostazioni dei criteri che forniscono a information worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo a chat, chiamate e riunioni.|
|Sala pazienti sanitaria  |Crea un set di criteri e impostazioni dei criteri che si applicano alle sale pazienti dell'organizzazione sanitaria.|
|Utenti aziendali di piccole e medie dimensioni (Voce aziendale) |Crea un criterio di configurazione delle app che include le app per un'esperienza vocale aziendale.|
|Utenti piccole e medie imprese (senza VoIP aziendale) |Crea un criterio di configurazione delle app pertinente per gli utenti di Teams di piccole e medie imprese (esperienza vocale non aziendale).
|Responsabile della sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri da applicare ai responsabili della sicurezza pubblica dell'organizzazione.|

> [!NOTE]
> Nei prossimi rilasci di Teams aggiungeremo altri pacchetti di criteri, quindi controlla di nuovo le informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.
Ad esempio, quando si assegna il pacchetto di criteri Education (docente) ai docenti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto di criteri Education (docente)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

**Questa funzionalità è in anteprima privata**

I pacchetti di criteri personalizzati consentono di raggruppare il proprio set di criteri per gli utenti con ruoli simili nell'organizzazione. Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzati:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, seleziona Pacchetti **criteri,** quindi fai clic su **Aggiungi.**
    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina Pacchetti criteri nell'interfaccia di amministrazione":::
2. Immetti un nome e una descrizione per il pacchetto.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzati":::
3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.
4. Fare clic su **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

Di seguito viene illustrato come usare i pacchetti di criteri nell'organizzazione.

![Panoramica dell'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- **[Visualizzazione:](#view-the-settings-of-a-policy-in-a-policy-package)** consente di visualizzare i criteri in un pacchetto di criteri. Quindi, visualizza le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Assicurarsi di comprendere tutte le impostazioni. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli in modo che siano più restrittivi o limitati in base alle esigenze dell'organizzazione.

    Se vengono eliminati criteri, è comunque possibile visualizzare le impostazioni, ma non modificarle. I criteri eliminati vengono ri creati di nuovo con le impostazioni predefinite quando si assegna il pacchetto di criteri.

- **[Personalizza:](#customize-policies-in-a-policy-package)** personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.

- **[Assegna:](#assign-a-policy-package)** assegnare il pacchetto di criteri agli utenti.  

> [!NOTE]
> È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo aver assegnato un pacchetto. Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, seleziona Pacchetti **criteri,** quindi seleziona un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
2. Fare clic sul criterio da visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

È possibile modificare le impostazioni di un criterio tramite **la** pagina Pacchetti criteri o passando direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, eseguire una delle operazioni seguenti:
    - Fai **clic su** Pacchetti criteri e quindi seleziona il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Fare clic sul tipo di criterio.  Ad esempio, fare clic **su Criteri di messaggistica.**
2. Selezionare il criterio da modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri 

#### <a name="assign-a-policy-package-to-one-user"></a>Assegnare un pacchetto di criteri a un utente

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Nella pagina dell'utente fare clic **su** Criteri, quindi accanto a Pacchetto **di criteri** fare clic su **Modifica.**
3. Nel riquadro **Assegna pacchetto dei** criteri seleziona il pacchetto che vuoi assegnare e quindi fai clic su **Salva.**

#### <a name="assign-a-policy-package-to-multiple-users"></a>Assegnare un pacchetto di criteri a più utenti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a Pacchetti **criteri,** quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.
2. Fare **clic su Gestisci utenti.**
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, fare clic su **Salva.**

#### <a name="assign-a-policy-package-to-a-group"></a>Assegnare un pacchetto di criteri a un gruppo

**Questa funzionalità è in anteprima privata**

L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione. L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza. Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza. Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.

Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)

Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta. Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation). Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica. Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Viene visualizzato un messaggio di errore quando si assegna un pacchetto di criteri**

Questo problema può verificarsi se uno o più criteri nel pacchetto non sono stati creati o applicati correttamente. Riassegnare il pacchetto di criteri agli utenti. Se si riprova l'operazione, in genere si risolve il problema.

## <a name="related-topics"></a>Argomenti correlati

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[Pacchetti dei criteri di Teams per amministratori EDU](policy-packages-edu.md)

[Pacchetti di criteri di Teams per il settore sanitario](policy-packages-healthcare.md)

[Pacchetti di criteri di Teams per enti pubblici](policy-packages-gov.md)
