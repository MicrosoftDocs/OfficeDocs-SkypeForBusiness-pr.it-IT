---
title: Gestire l'app Approvazioni in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: how-to
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni su come gestire l'app Approvazioni per l'organizzazione in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbedcfb7215adbde9ee8b8dd2afb3e88422e28c2
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131185"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Gestire l'app Approvazioni in Microsoft Teams

L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.
Offre un modo semplice per ottenere controlli, conformità, rendicontazione e flussi di lavoro delle approvazioni strutturate e non strutturate in Teams.

 ![mostra l'app approvazioni.](media/approvals-selection.png)

Gli utenti possono aggiungere l'app Approvazioni e salvarla nella barra dei menu.

 ![mostra l'app approvazioni con l'opzione aggiungi.](media/approvalApp-pin.png)

La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione approvazione nell'ambiente predefinito Microsoft Dataverse. Le approvazioni create dall'app Approvazioni verranno archiviate nell'ambiente predefinito Microsoft Dataverse.

Questo articolo descrive i ruoli e i requisiti dell'app Approvazioni.

> [!NOTE]
> Questa funzionalità non è ancora stata rilasciata agli utenti di Government Community Cloud High (GCCH) e Department of Defense (DOD).

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze richieste

Per distribuire l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:

- Autorizzazioni per creare un database Microsoft Dataverse.

- Un account in [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per [Power Automate](/power-automate/get-started-approvals), Office 365 o Dynamics 365.

- Agli utenti è necessaria una licenza per Microsoft Forms per configurare nuovi modelli di approvazione.

Per usare l'app Approvazioni, è necessaria una licenza per Power Automate e l'account viene aggiunto automaticamente al ruolo Utente Approvazioni nell'ambiente di destinazione alla prima assegnazione di approvazione.

## <a name="storage-with-microsoft-dataverse"></a>Archiviazione con Microsoft Dataverse

Il common data model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e analitiche in Microsoft Dataverse. È costituito da un set di schemi di dati estendibili standardizzati pubblicati da Microsoft e dai nostri partner che consentono la coerenza dei dati e il relativo significato tra le applicazioni e i processi aziendali. Per altre informazioni, vedere [Common Data Model di Microsoft Power Platform](/power-automate/get-started-approvals).

Altre informazioni sui [flussi di lavoro di Approvazioni](/power-automate/modern-approvals).

Le approvazioni create da un modello archiviano comunque i dati in Microsoft Dataverse, ad esempio il titolo, i dettagli, l'ID modello e altro ancora. Le risposte inviate nella richiesta di approvazione vengono archiviate in Forms. Altre informazioni [sull'archiviazione dei dati per Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se si elimina il modello di modulo nel sito Microsoft Forms, il modello di approvazione verrà interrotto e gli utenti non saranno in grado di avviare la richiesta. Gli utenti ricevono un errore "CDB TableNotFound" quando provano ad aprire un modello di approvazione eliminato in Microsoft Forms.

I modelli con ambito organizzazione condividono la stessa durata del tenant e i modelli con ambito team condividono la stessa durata del team. Di conseguenza, l'eliminazione definitiva del team comporta l'eliminazione dei modelli correlati.

## <a name="approvals-teams-app-permissions"></a>Autorizzazioni dell'app Approvazioni di Teams

L'app Approvazioni di Teams consente di accedere alle funzionalità seguenti:

- Ricevere messaggi e dati forniti dall'utente.

- Invio di messaggi e notifiche dell'utente.

- Render delle app e delle finestre di dialogo personali senza intestazione fornita da Teams.

- Accesso alle informazioni del profilo, ad esempio nome, indirizzo di posta elettronica, nome della società e lingua preferita.

- Ricevere messaggi e dati forniti dai membri del team nel canale.

- Inviare messaggi e notifiche in un canale.

- Accedere alle informazioni del team:
  - nome del team
  - elenco dei canali
  - elenco partecipanti (nomi e indirizzi di posta elettronica dei membri del team).

- Uso delle informazioni del team per i contatti.

Autorizzazioni per i modelli di approvazione

- Tutti i proprietari del team possono creare un modello di approvazione per i team di cui sono proprietari.

- Quando un amministratore crea un modello per l'intera organizzazione per la prima volta, crea automaticamente un nuovo gruppo di Azure Active Directory (AAD) per tutti gli amministratori del tenant, inclusi gli amministratori globali e del servizio Teams. Questi amministratori vengono aggiunti come proprietari del gruppo, in modo che possano co-gestire i modelli dell'organizzazione. Gli amministratori che non hanno più accesso all'organizzazione dopo la creazione del team devono essere aggiunti manualmente come proprietari del gruppo in modo che abbiano le stesse autorizzazioni per gestire i modelli a livello di organizzazione.

> [!Note]
> Se un amministratore elimina il gruppo, hai un mese per ripristinarlo nel portale di Azure Active Directory (AAD) per ripristinare tutti i dati correlati. Dopo un mese o se l'amministratore elimina questo gruppo nel Cestino, si perderanno tutti i dati correlati.

## <a name="disable-the-approvals-app"></a>Disabilitare l'app Approvazioni

L'app Approvazioni è disponibile per impostazione predefinita. È possibile disabilitarla nell'interfaccia di amministrazione di Teams.

  1. Passare all'interfaccia di amministrazione di Teams.

  2. Passare a **app Teams** >  **Gestisci app**.

  3. Cercare l'app Approvazioni.

     ![mostra la struttura di spostamento centrale Amministrazione con l'opzione App di Teams > Gestisci app evidenziata.](media/manage-approval-apps.png)

  4. Selezionare **Approvazioni**.

  5. Selezionare l'interruttore per disabilitare l'app per l'organizzazione.

     :::image type="content" alt-text="mostra i dettagli per l'app Approvazioni." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Aggiungere approvazioni a Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Usare l'esperienza app in prima linea personalizzata per aggiungere approvazioni e altre app a Teams

L'esperienza personalizzata per le app in prima linea in Teams aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Le app aggiunte includono Approvazioni, Walkie-talkie, attività e turni. Per impostazione predefinita, questa funzionalità è attivata e offre ai dipendenti in prima linea un'esperienza personalizzata in base alle loro esigenze.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams, dove gli utenti possono accedervi rapidamente e facilmente.

Per altre informazioni, incluso il funzionamento dell'esperienza con i criteri delle app impostati, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Usare i criteri di configurazione delle app per aggiungere approvazioni a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per aggiungere app più importanti per gli utenti degli utenti.

Per aggiungere l'app Approvazioni per gli utenti, è possibile modificare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati nei criteri di configurazione delle app. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Criteri di conservazione

Le approvazioni create dall'app Approvazioni vengono archiviate nell'ambiente predefinito Microsoft Dataverse, che al momento non supporta i backup. Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

I dati archiviati in Forms non verranno eliminati finché i proprietari del team non lo puliranno dalla scheda **moduli eliminati** nell'app Web Microsoft Forms.

## <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Attualmente, l'app Approvazioni in Teams non supporta i criteri di accesso condizionale impostati per Microsoft Teams.

## <a name="data-limitations"></a>Limitazioni dei dati

Ogni team può contenere al massimo 400 modelli di approvazione e ogni modello può raccogliere un massimo di 50.000 richieste in base alla funzionalità corrente di Microsoft Forms.

## <a name="auditing"></a>Controllo

L'app Approvazioni registra gli eventi di controllo all'interno del Centro sicurezza e conformità di Microsoft 365. È possibile visualizzare il log di audit.

1. Passare al sito Conformità di Microsoft 365.

2. Selezionare la sezione **Controllo**.

3. Cercare le attività in **Attività di approvazione di Microsoft Teams**.

È possibile cercare le attività seguenti:

- Creazione di una nuova richiesta di approvazione

- Visualizzazione dei dettagli della richiesta di approvazione

- Richieste di approvazione approvate

- Richieste di approvazione rifiutate

- Richieste di approvazione annullate

- Richieste di approvazione condivise

- File allegato alle richieste di approvazione

- Richieste di approvazione riassegnate

- Firma elettronica aggiunta alle richieste di approvazione

- Dettagli della richiesta di firma elettronica visualizzati

- Richiesta di firma elettronica esaminata

- Richiesta di firma elettronica annullata

- Creare un nuovo modello

- Modificare un modello esistente

- Abilitare/disabilitare un modello

- Modello visualizzato

Per accedere ad altre approvazioni di controllo in Power Automate, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione primarie Approvazione, Richiesta di approvazione e Risposta approvazione. Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione. Per altre informazioni, vedere [Dati di controllo e attività degli utenti per la sicurezza e la conformità - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

Il controllo può essere personalizzato ulteriormente nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Per usare i report preconfigurati, accedere al Centro sicurezza e conformità di Microsoft 365.

2. Selezionare **Ricerche e indagini**.

3. Cercare nel log di audit e selezionare la scheda **Attività di Dynamics 365**.

Altre informazioni su [Microsoft Dataverse e registrazione delle attività delle app basata su modello - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicurezza

Tramite l'app Approvazioni di Teams, gli utenti hanno accesso alla creazione di nuove approvazioni e alla visualizzazione di quelle inviate e ricevute. Gli utenti non possono accedere alle approvazioni create da altri utenti a meno che non abbiano risposto o visualizzato la richiesta.

>[!Note]
> A un utente viene assegnato il ruolo di visualizzatore di una richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione. Non è possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato il ruolo specifico.

## <a name="approvals-e-signature-integration"></a>Integrazione delle firme e-mail di approvazione

Per usare la funzionalità di firma elettronica dell'app Approvazioni, è necessaria una licenza per il provider di firma elettronica specifico che si vuole usare. Per ottenere una licenza per l'organizzazione, è necessario accedere al sito del provider.

### <a name="enable-or-disable-e-signature-providers"></a>Abilitare o disabilitare i provider di firme elettronica

È possibile usare l'interfaccia di amministrazione di Teams per controllare quali provider di firma elettronica di terze parti sono disponibili per gli utenti nell'app Approvazioni. Per impostazione predefinita, i provider di firme elettronica sono abilitati nell'app Approvazioni. Quando si disabilita un provider di firme elettronica, gli utenti non avranno accesso a tale provider quando creano approvazioni. Inoltre, gli utenti non potranno visualizzare le richieste di firma elettronica create con tale provider.

1. Nel riquadro sinistro dell'interfaccia di amministrazione di Teams passare alle app  > **di Teams****Gestire le app**.
2. Cerca l'app Approvazioni e quindi selezionala.
3. Passare alla scheda **Impostazioni** e quindi eseguire una o più delle operazioni seguenti:

    - Per abilitare o disabilitare Adobe Sign, impostare l'interruttore **su Attivato** o **Disattivato**.
    - Per abilitare o disabilitare DocuSign, impostare l'interruttore **su Attivato** o **Disattivato**.
4. Seleziona **Invia**.

Le approvazioni delle firme elettronica create dall'app Approvazioni vengono archiviate nell'ambiente cloud del provider selezionato. Per esportare i dati sulle firme elettronica, è necessario passare al sito del provider. Per altre informazioni sull'archiviazione, l'esportazione e la conservazione dei contratti di firma elettronica, vedere la documentazione del provider.
