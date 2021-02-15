---
title: Disponibilità delle applicazioni di approvazione in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla disponibilità delle applicazioni Approvazione in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f916b4e794c862a05a42f075ca2f210a079ff42a
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909520"
---
# <a name="teams-approvals-app-availability"></a>Disponibilità dell'app Approvazione Teams

L'app Approvazioni è disponibile come app personale per tutti gli utenti di Microsoft Teams.
L'app Approvazioni offre un modo semplice per portare il controllo, la conformità, la responsabilità e i flussi di lavoro nelle approvazioni strutturate e non strutturate in Teams.

 ![mostra l'app Approvazioni](media/approvals-selection.png)

Gli utenti possono aggiungere l'app Approvazioni per salvarla sulla barra dei menu.

 ![mostra l'app Approvazioni con l'opzione Aggiungi](media/approvalApp-pin.png)

La prima approvazione creata dall'app Approvazioni attiverà il provisioning della soluzione di approvazione nell'ambiente CDS (Common Data Service) predefinito. Le approvazioni create dall'app Approvazioni verranno archiviate nell'ambiente CDS predefinito.

Questo articolo descrive i requisiti e i ruoli dell'app Approvazione.

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze necessarie

Per usare l'app Approvazioni, è necessaria l'autorizzazione per gli elementi seguenti:

- Autorizzazioni per la creazione di un database CDS Microsoft.

- Un account [flow.microsoft.com](https://flow.microsoft.com/)

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per [Power Automate,](https://docs.microsoft.com/power-automate/get-started-approvals)Office 365 o Dynamics 365.

## <a name="storage-with-cds"></a>Archiviazione con CDS

Il modello CDM (Common Data Model) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e analitiche in CDS. È costituito da un set di schemi di dati estendibili standardizzati pubblicati da Microsoft e dai nostri partner che consentono la coerenza dei dati e il relativo significato in applicazioni e processi aziendali. Altre informazioni sul [modello di dati comuni della piattaforma Microsoft Power.](https://docs.microsoft.com/power-automate/get-started-approvals)

Altre informazioni sul flusso [di lavoro Approvazione.](https://docs.microsoft.com/power-automate/modern-approvals)

## <a name="approvals-teams-app-permissions"></a>Autorizzazioni dell'app Approvals Teams

L'app Approvals Teams consente di accedere alle caratteristiche seguenti:

- Ricevere messaggi e dati forniti dall'utente.

- Inviarti messaggi e notifiche.

- Visualizzare le app e le finestre di dialogo personali senza un'intestazione fornita da Teams.

- Accedere alle informazioni del profilo, ad esempio il nome, l'indirizzo di posta elettronica, il nome della società e la lingua preferita.

- Ricevere messaggi e dati forniti dai membri del team in un canale.

- Inviare messaggi e notifiche in un canale.

- Accedere alle informazioni del team:
  - nome del team
  - elenco canali
  - (i nomi e gli indirizzi di posta elettronica dei membri del team).

- Usare le informazioni del team per contattarlo.

## <a name="disable-the-approvals-app"></a>Disabilitare l'app Approvazioni

L'app Approvazioni è disponibile per impostazione predefinita. È possibile disabilitare l'app nell'interfaccia di amministrazione di Teams.

  1. Accedere all'interfaccia di amministrazione di Teams.

  2. Espandere **le app di Teams** e selezionare Gestisci **app.**

  3. Cercare l'app Approvazioni.

![mostra la struttura di spostamento dell'interfaccia di amministrazione con l'opzione App di Teams > Gestisci app evidenziata](media/manage-approval-apps.png)

  4. Selezionare Approvazioni.

  5. Seleziona l'interruttore per disabilitare l'app per l'organizzazione.

![mostra i dettagli per l'app Approvazioni](media/approvals-details.png)

## <a name="retention-policy"></a>Criteri di conservazione

Le approvazioni create dall'app Approvazioni vengono archiviate nell'ambiente CDS predefinito, che al momento non supporta i backup. Altre informazioni su come eseguire [il backup e il ripristino di ambienti - Power Platform Microsoft \| Docs.](https://docs.microsoft.com/power-platform/admin/backup-restore-environments)

## <a name="auditing"></a>Controllo

L'app Approvazione registra gli eventi di controllo all'interno del Centro sicurezza e conformità di Microsoft 365. È possibile visualizzare il log di controllo.

1. Passare al sito conformità di Microsoft 365.

2. Selezionare la **sezione** Controllo.

3. Cercare le attività nelle **attività di approvazione di Microsoft Teams.**

È possibile cercare le attività seguenti:

- Creare una nuova richiesta di approvazione

- Visualizzare i dettagli della richiesta di approvazione

- Richiesta di approvazione approvata

- Richiesta di approvazione rifiutata

- Richiesta di approvazione annullata

- Richiesta di approvazione condivisa

- File allegato alla richiesta di approvazione

- Richiesta di approvazione riassegnata

- Aggiunta di una firma elettronica alla richiesta di approvazione

Per l'accesso ad altre approvazioni di controllo all'interno di Flow, abilitare e configurare il controllo nell'ambiente predefinito per le entità di approvazione principali Approvazione, Richiesta di approvazione e Risposta di approvazione. Le operazioni di creazione, aggiornamento ed eliminazione sono eventi controllabili per i record Approvazione. Altre informazioni sui dati di controllo e sulle attività degli utenti per la sicurezza e la [conformità - Documenti Microsoft della piattaforma \| Power.](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity)

Il controllo può essere ulteriormente personalizzato nel Centro sicurezza e [conformità di Microsoft 365.](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)

1. Per usare i report preconfigurati, accedere a Sicurezza e conformità di Microsoft 365.

2. Selezionare **Ricerche & indagini.**

3. Eseguire ricerche nel log di controllo e selezionare la **scheda Attività di Dynamics 365.**

Altre informazioni sulla registrazione attività delle app basata su modello e [Microsoft Dataverse - Piattaforma Power.](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing)

## <a name="security"></a>Sicurezza

Dall'app Approvazioni di Teams, gli utenti hanno accesso per creare nuove approvazioni e visualizzare le approvazioni inviate e ricevute. Gli utenti non hanno accesso alle Approvazioni create da altri, a meno che non siano un risponditore o un visualizzatore della richiesta.

> [!Note]
> L'utente avrà il ruolo di visualizzatore di una richiesta se fa parte della chat o del canale in cui è stata creata l'approvazione. Non sarà possibile intervenire sulla richiesta se al momento della creazione dell'approvazione non è stato assegnato quel ruolo.
