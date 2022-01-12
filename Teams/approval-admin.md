---
title: Disponibilità dell'applicazione Approvazioni in Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità dell'applicazione Approvazioni in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c0e4ec40368b8348833b596d55f34adcb0c316d
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766389"
---
# <a name="teams-approvals-app-availability"></a>Disponibilità dell'app Approvazioni in Teams

L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.
Offre un modo semplice per ottenere controlli, conformità, rendicontazione e flussi di lavoro delle approvazioni strutturate e non strutturate in Teams.

 ![mostra l'app approvazioni.](media/approvals-selection.png)

Gli utenti possono aggiungere l'app Approvazioni e salvarla nella barra dei menu.

 ![mostra l'app approvazioni con l'opzione pin.](media/approvalApp-pin.png)

La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione Approvazioni nell'ambiente CDS (Common Data Service) predefinito. Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito.

Questo articolo descrive i ruoli e i requisiti dell'app Approvazioni.

> [!NOTE]
> Questa funzionalità non è ancora stata rilasciata per gli utenti Government Community Cloud High (GCCH) e Department of Defense (DOD).

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze richieste

Per distribuire l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:

- Autorizzazioni per la creazione di un database Microsoft CDS.

- Account su [flow.microsoft.com](https://flow.microsoft.com/)

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per [Power Automate,](/power-automate/get-started-approvals)Office 365 o Dynamics 365.

- La licenza per Microsoft Forms è necessaria per consentire agli utenti di configurare nuovi modelli di approvazione.

Per usare l'app Approvazioni, è necessaria una licenza per Power Automate e l'account verrà aggiunto automaticamente al ruolo utente di Approvazioni nell'ambiente di destinazione alla prima assegnazione di approvazione.

## <a name="storage-with-cds"></a>Archiviazione su CDS

Common Data Model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e di analisi in CDS. È costituito da un set di schemi di dati standardizzati ed estendibili pubblicati da Microsoft e dai nostri partner che consentono la coerenza dei dati e il relativo significato tra le applicazioni e i processi aziendali. Per altre informazioni, vedere [Common Data Model di Microsoft Power Platform](/power-automate/get-started-approvals).

Altre informazioni sui [flussi di lavoro di Approvazioni](/power-automate/modern-approvals).

Approvazioni creati da un modello archiviano comunque i dati in CDS, ad esempio il titolo, i dettagli, l'ID del modello e altro ancora. Le risposte inviate nella richiesta di approvazione vengono archiviate in Moduli. Altre informazioni  [sull'archiviazione dei dati per Microsoft Forms.](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)

>[!Note]
>Se si elimina il modello di modulo nel sito Di Microsoft Forms, il modello Approvazione verrà eliminato e gli utenti non saranno in grado di avviare la richiesta. Gli utenti riceveranno un messaggio di errore "Tabella CDBNonFound" quando si prova ad aprire un modello approvazione eliminato in Microsoft Forms.

I modelli con ambito organizzazione condividono la stessa durata del tenant e i modelli con ambito di team condividono la stessa durata del team. Pertanto, l'eliminazione definitiva del team elimina i modelli correlati.

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

- Tutti i proprietari dei team possono creare un modello di approvazione per i team di cui sono proprietari.

- Quando un amministratore crea un modello per l'intera organizzazione per la prima volta, crea automaticamente un nuovo gruppo Azure Active Directory (AAD) per tutti gli amministratori del tenant, inclusi gli amministratori dei servizi globali e Teams. Questi amministratori verranno aggiunti come proprietari del gruppo, in modo che possano gestire i modelli dell'organizzazione in modalità co-gestione. Gli amministratori che non hanno più accesso all'organizzazione dopo la creazione del team devono essere aggiunti manualmente come proprietari dei gruppi, in modo da avere le stesse autorizzazioni per gestire i modelli a livello di organizzazione.

> [!Note]
> Se un amministratore elimina il gruppo, è necessario un mese per ripristinarlo all'interno del portale Azure Active Directory (AAD) per ripristinare tutti i dati correlati. Dopo un mese o se l'amministratore elimina questo gruppo nel Cestino, si perderanno tutti i dati correlati.

## <a name="disable-the-approvals-app"></a>Disabilitare l'app Approvazioni

L'app Approvazioni è disponibile per impostazione predefinita. È possibile disabilitarla nell'interfaccia di amministrazione di Teams.

  1. Passare all'interfaccia di amministrazione di Teams.

  2. Passare alle **app Teams gestisci** le  >  **app**.

  3. Cercare l'app Approvazioni.

     ![mostra la struttura di spostamento dell'interfaccia di amministrazione con Teams app > Gestisci app evidenziata.](media/manage-approval-apps.png)

  4. Selezionare **Approvazioni**.

  5. Selezionare l'interruttore per disabilitare l'app per l'organizzazione.

     :::image type="content" alt-text="mostra i dettagli per l Approvazioni app." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="retention-policy"></a>Criteri di conservazione

Approvazioni creati dall'app Approvazioni vengono archiviati nell'ambiente CDS predefinito, che al momento non supporta i backup. Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

I dati archiviati in Forms non verranno eliminati finché i proprietari del team non lo puliranno dalla **scheda** Moduli eliminati nell'app Web Microsoft Forms.

## <a name="data-limitations"></a>Limitazioni dei dati

Ogni team può contenere al massimo 400 modelli di approvazione e ogni modello può raccogliere un massimo di 50.000 richieste in base alla funzionalità corrente in Microsoft Forms.

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

Per accedere ad altre approvazioni di controllo all'interno del flusso, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione principali Approvazione, Richiesta di approvazione e Risposta di approvazione. Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record di approvazione. Per altre informazioni, vedere [Dati di controllo e attività degli utenti per la sicurezza e la conformità - Power Platform \| Microsoft Docs](/power-platform/admin/audit-data-user-activity).

Il controllo può essere personalizzato ulteriormente nel [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).

1. Per usare i report preconfigurati, accedere al Centro sicurezza e conformità di Microsoft 365.

2. Selezionare **Ricerche e indagini**.

3. Cercare nel log di audit e selezionare la scheda **Attività di Dynamics 365**.

Altre informazioni su [Microsoft Dataverse e registrazione delle attività delle app basata su modello - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicurezza

Tramite l'app Approvazioni di Teams, gli utenti hanno accesso alla creazione di nuove approvazioni e alla visualizzazione di quelle inviate e ricevute. Gli utenti non possono accedere alle approvazioni create da altri utenti a meno che non abbiano risposto o visualizzato la richiesta.

> [!Note]
> L'utente riceve il ruolo di visualizzatore della richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione. Non è possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato il ruolo specifico.

## <a name="approvals-e-signature-integration"></a>Approvazioni di firma elettronica

Per usare la Approvazioni di firma elettronica dell'app, è necessaria una licenza per lo specifico provider di firme elettroniche che si vuole usare. Per ottenere una licenza per l'organizzazione, è necessario accedere al sito del provider.
### <a name="enable-or-disable-e-signature-providers"></a>Abilitare o disabilitare i provider di firme elettroniche

È possibile usare l'Teams di amministrazione per controllare quali provider di firme elettroniche di terze parti sono disponibili per gli utenti nell'app Approvazioni. Per impostazione predefinita, i provider di firme elettroniche sono abilitati nell Approvazioni app. Quando si disabilita un provider di firme elettroniche, gli utenti non potranno accedere a tale provider quando creano le approvazioni. Gli utenti non saranno inoltre in grado di visualizzare le richieste di firma elettronica create con tale provider.

1. Nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a Teams  >  **app Gestisci app**.
2. Cercare l'app Approvazioni e quindi selezionarla.
3. Passare alla scheda **Impostazioni** e quindi eseguire una o più delle operazioni seguenti:

    - Per abilitare o disabilitare Adobe Sign, impostare l'interruttore su **Attivato** o **Disattivato.**
    - Per abilitare o disabilitare DocuSign, impostare l'interruttore su **Attivato** o **Disattivato.**
4. Selezionare **Invia**.

Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nell'ambiente cloud del provider selezionato. Per esportare i dati sulle firme elettroniche, è necessario accedere al sito del provider. Per altre informazioni sull'archiviazione, l'esportazione e la conservazione dei contratti di firma elettronica, vedere la documentazione del provider.
