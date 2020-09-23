---
title: Gestire i pacchetti di criteri in Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft teams per semplificare, snellire e garantire la coerenza quando si gestiscono i criteri per i gruppi di utenti.
ms.openlocfilehash: bdbfed095cf522702f55963ba7e46d79b765d59c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48220013"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Gestire i pacchetti di criteri in Microsoft Teams

> [!NOTE]
> Una delle caratteristiche descritte in questo articolo, [pacchetti di criteri personalizzati](#custom-policy-packages), non è ancora stata rilasciata. Verrà presto in anteprima privata.

Un pacchetto di criteri in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione. I pacchetti di criteri sono stati creati per semplificare, snellire e garantire la coerenza della gestione dei criteri per i gruppi di utenti nell'organizzazione.  

Puoi usare i [pacchetti di criteri inclusi in teams](#policy-packages-included-in-teams) o [creare pacchetti di criteri personalizzati](#custom-policy-packages) (presto in anteprima privata).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina dei pacchetti di criteri nell'interfaccia di amministrazione":::

È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti. Quando si modificano le impostazioni dei criteri in un pacchetto, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate. Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare le caratteristiche dei team che si desidera concedere o limitare per set specifici di persone nell'organizzazione. Ogni pacchetto di criteri in teams è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.

I pacchetti di criteri supportano i tipi di criteri Team seguenti:

- Criteri di messaggistica
- Criteri per le riunioni
- Criteri di configurazione dell'app
- Criteri di chiamata
- Criteri per gli eventi live

## <a name="policy-packages-included-in-teams"></a>Pacchetti di criteri inclusi in teams

I team attualmente includono i seguenti pacchetti di criteri.

|**Nome pacchetto**  |**Descrizione** |
|---------|---------|
|Istruzione (studente di istruzione superiore)    |Crea un set di criteri e impostazioni dei criteri applicabili agli studenti dell'istruzione superiore.|
|Istruzione (studente di scuola elementare)   |Crea un set di criteri e impostazioni dei criteri applicabili agli studenti primari.|
|Istruzione (studente di scuola secondaria)    |Crea un set di criteri e impostazioni dei criteri applicabili agli studenti secondari.         |
|Istruzione (insegnante)    |Crea un set di criteri e impostazioni dei criteri applicabili agli insegnanti.      |
|Istruzione (insegnante di scuola elementare che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli insegnanti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Istruzione (studente della scuola elementare che usa l'apprendimento remoto)    |Crea una serie di criteri che si applicano agli studenti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.      |
|Gestione i FIRSTLINE |Crea un set di criteri e applica tali impostazioni ai responsabili di I FIRSTLINE dell'organizzazione. |
|Lavoratore i FIRSTLINE |Crea un set di criteri e applica tali impostazioni agli operatori I FIRSTLINE dell'organizzazione. |
|Lavoratore clinico sanitario  |Crea un set di criteri e impostazioni dei criteri che conferiscono agli operatori clinici, ad esempio infermieri registrati, addebiti infermieri, medici e assistenti sociali, l'accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni. |
|Information Worker sanitari  |Crea un set di criteri e impostazioni dei criteri che forniscono agli Information Worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo alla chat, alle chiamate e alle riunioni.|
|Sala paziente sanitaria  |Crea un set di criteri e impostazioni dei criteri applicabili alle sale del paziente nell'organizzazione sanitaria.|
|Utente di piccole e medie imprese (Business Voice) |Crea un criterio di configurazione dell'app che include le app per un'esperienza di Business Voice.|
|Utente di piccole e medie imprese (senza Business Voice) |Crea un criterio di configurazione dell'app pertinente per gli utenti di team commerciali di piccole e medie dimensioni (non-Business Voice Experience).
|Addetto alla sicurezza pubblica   |Crea un set di criteri e impostazioni dei criteri applicabili agli addetti alla sicurezza pubblica dell'organizzazione.|

> [!NOTE]
> Aggiungeremo altri pacchetti di criteri nelle versioni future dei team, quindi controlla le informazioni più aggiornate.  

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.
Ad esempio, quando si assegna il pacchetto di criteri Education (Teacher) agli insegnanti dell'Istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto di criteri Education (Teacher)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Pacchetti di criteri personalizzati

**Questa funzionalità sarà presto disponibile in anteprima privata**

I pacchetti di criteri personalizzati consentono di raggruppare il proprio set di criteri per gli utenti con ruoli simili nell'organizzazione. Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.

Per creare un nuovo pacchetto di criteri personalizzato:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**e quindi fare clic su **Aggiungi**.
    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina pacchetti di criteri nell'interfaccia di amministrazione":::
2. Immettere un nome e una descrizione per il pacchetto.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzato":::
3. Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.
4. Fare clic su **Salva**.

## <a name="how-to-use-policy-packages"></a>Come usare i pacchetti di criteri

La procedura seguente illustra come usare i pacchetti di criteri nell'organizzazione.

![Panoramica sull'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- **[Visualizzazione](#view-the-settings-of-a-policy-in-a-policy-package)**: visualizzare i criteri in un pacchetto di criteri. Quindi, Visualizza le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto. Verificare di aver compreso tutte le impostazioni. Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.

    Se un criterio viene eliminato, è comunque possibile visualizzarne le impostazioni, ma non si potranno modificare le impostazioni. I criteri eliminati vengono ricreati con le impostazioni predefinite quando si assegna il pacchetto di criteri.

- **[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto dei criteri per adattarle alle esigenze dell'organizzazione.

- **[Assegna](#assign-a-policy-package)**: assegna il pacchetto di criteri agli utenti.  

> [!NOTE]
> È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo l'assegnazione di un pacchetto. Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.

Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Visualizzare le impostazioni di un criterio in un pacchetto di criteri

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**e quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
2. Fare clic sul criterio che si vuole visualizzare.

### <a name="customize-policies-in-a-policy-package"></a>Personalizzare i criteri in un pacchetto di criteri

È possibile modificare le impostazioni di un criterio tramite la pagina **pacchetti di criteri** o accedendo direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams eseguire una delle operazioni seguenti:
    - Fare clic su **pacchetti di criteri**e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.
    - Fare clic sul tipo di criterio.  Ad esempio, fare clic su **criteri di messaggistica**.
2. Selezionare il criterio che si vuole modificare. I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="assign-a-policy-package"></a>Assegnare un pacchetto di criteri

#### <a name="assign-a-policy-package-to-one-user"></a>Assegnare un pacchetto di criteri a un utente

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Nella pagina dell'utente fare clic su **criteri**e quindi fare clic su **modifica**accanto a **pacchetto criteri**.
3. Nel riquadro **Assegna criteri del pacchetto** selezionare il pacchetto da assegnare e quindi fare clic su **Salva**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Assegnare un pacchetto di criteri a più utenti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri**e quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.
2. Fare clic su **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Assegnare un pacchetto di criteri a un set di grandi dimensioni (batch) di utenti

USA assegnazione pacchetto criteri batch per assegnare un pacchetto di criteri a set di grandi dimensioni di utenti alla volta. Si usa il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri che si vuole assegnare. Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.

Un batch può contenere fino a 5.000 utenti. È possibile specificare gli utenti per l'ID oggetto, l'UPN, l'indirizzo SIP o l'indirizzo di posta elettronica. Per altre informazioni, vedere [assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Viene visualizzato un messaggio di errore quando si assegna un pacchetto di criteri**

Questo problema può verificarsi se uno o più criteri del pacchetto non sono stati creati o applicati correttamente. Riassegnare il pacchetto di criteri agli utenti. Il tentativo di riprovare l'operazione in genere risolve questo problema.

## <a name="related-topics"></a>Argomenti correlati

[Assegnare criteri agli utenti in teams](assign-policies.md)

[Pacchetti di criteri team per gli amministratori EDU](policy-packages-edu.md)

[Pacchetti di criteri team per l'assistenza sanitaria](policy-packages-healthcare.md)

[Pacchetti di criteri per le squadre per enti pubblici](policy-packages-gov.md)
