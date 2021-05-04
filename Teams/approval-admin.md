---
title: Disponibilità dell'applicazione Approvazioni in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: farhazk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità dell'applicazione Approvazioni in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71f08840ffa9c41622d07376933c14a7ae6b493
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2021
ms.locfileid: "52129795"
---
# <a name="teams-approvals-app-availability"></a>Disponibilità dell'app Approvazioni in Teams

L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.
Offre un modo semplice per ottenere controlli, conformità, rendicontazione e flussi di lavoro delle approvazioni strutturate e non strutturate in Teams.

 ![mostra l'app approvazioni](media/approvals-selection.png)

Gli utenti possono aggiungere l'app Approvazioni e salvarla nella barra dei menu.

 ![mostra l'app approvazioni con l'opzione di aggiunta](media/approvalApp-pin.png)

La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione Approvazioni nell'ambiente CDS (Common Data Service) predefinito. Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito.

Questo articolo descrive i ruoli e i requisiti dell'app Approvazioni.

> [!NOTE]
> Questa funzionalità non è ancora stata rilasciata per gli utenti Government Community Cloud (GCC), Government Community Cloud High (GCCH) e DoD (Department of Defense).

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze richieste

Per usare l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:

- Autorizzazioni per la creazione di un database Microsoft CDS.

- Account su [flow.microsoft.com](https://flow.microsoft.com/)

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per [Power Automate](/power-automate/get-started-approvals), Office 365 o Dynamics 365.

## <a name="storage-with-cds"></a>Archiviazione su CDS

Common Data Model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e di analisi in CDS. È costituito da un set di schemi di dati standardizzati ed estendibili pubblicati da Microsoft e dai propri partner, che consentono la coerenza dei dati e il loro significato nelle applicazioni e nei processi aziendali. Per altre informazioni, vedere [Common Data Model di Microsoft Power Platform](/power-automate/get-started-approvals).

Altre informazioni sui [flussi di lavoro di Approvazioni](/power-automate/modern-approvals).

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

## <a name="disable-the-approvals-app"></a>Disabilitare l'app Approvazioni

L'app Approvazioni è disponibile per impostazione predefinita. È possibile disabilitarla nell'interfaccia di amministrazione di Teams.

  1. Passare all'interfaccia di amministrazione di Teams.

  2. Espandere **App di Teams** e selezionare **Gestisci app**.

  3. Cercare l'app Approvazioni.

     ![mostra lo spostamento dell'interfaccia di amministrazione di Teams con le opzioni App di Teams > Gestisci app evidenziate](media/manage-approval-apps.png)

  4. Selezionare Approvazioni.

  5. Selezionare l'interruttore per disabilitare l'app per l'organizzazione.

     ![mostra i dettagli dell'app Approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a>Criteri di conservazione

Le approvazioni create dall'app Approvazioni sono archiviate nell'ambiente CDS predefinito, che al momento non supporta i backup. Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

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

## <a name="approvals-e-signature-integration"></a>Integrazione delle firme elettroniche per le approvazioni

Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nell'ambiente cloud del provider selezionato. Per altre informazioni sull'archiviazione relativa al contratto di firma elettronica, vedere la documentazione di archiviazione del provider selezionato.

Per usare la caratteristica di firma elettronica dell'app Approvazioni, sono necessari gli elementi seguenti:

- Licenza per lo specifico provider di firme elettroniche che si sceglie di usare. Per ottenere una licenza per l'organizzazione, è necessario accedere al sito del provider.

Per la funzionalità di firma elettronica Approvazioni, i partner delle firme di terze parti verranno visualizzati nell'app Teams approvazioni per impostazione predefinita. È possibile disabilitare specifici provider di firme elettroniche accedendo alle impostazioni dell'app nell'Teams di amministrazione.

1. Nell'Teams di amministrazione, in **Gestisci app,** selezionare l'app Approvazioni e scegliere **Impostazioni**. 

2. Per impostazione predefinita, ogni provider di firme elettroniche ha un interruttore accanto alla posizione attiva (a destra). Scorrere l'interruttore verso sinistra per disabilitare uno specifico provider di firme elettroniche. Se un Teams disabilita un provider, gli utenti finali non potranno vedere il provider durante la creazione di un'approvazione. Gli utenti finali non saranno inoltre in grado di visualizzare le richieste di firma elettronica effettuate con il provider.

Le approvazioni delle firme elettroniche create dall'app Approvazioni vengono archiviate nel cloud del provider selezionato. Sarà quindi necessario accedere al sito del provider per esportare i dati relativi alle firme elettroniche. Fare riferimento alla documentazione del provider relativa all'esportazione e alla conservazione di questi contratti.
