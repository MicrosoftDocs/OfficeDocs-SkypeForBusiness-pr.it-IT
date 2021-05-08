---
title: Gestire i team nell'Microsoft Teams di amministrazione
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Informazioni su come visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione nell'Microsoft Teams di amministrazione.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237542"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gestire i team nell'Microsoft Teams di amministrazione
==========================================

## <a name="overview"></a>Panoramica

Questo articolo fornisce una panoramica degli strumenti di gestione per Teams nell'interfaccia Microsoft Teams amministrazione.

L'amministratore potrebbe dover visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione oppure potrebbe essere necessario eseguire azioni di correzione, ad esempio l'assegnazione di proprietari per i team senza proprietario. È possibile gestire i team usati nell'organizzazione tramite il modulo Microsoft Teams PowerShell e l'Microsoft Teams di amministrazione. È possibile accedere all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Per le funzionalità di amministrazione complete che usano questi due set di strumenti, è consigliabile assicurarsi di avere uno dei ruoli seguenti:

- Amministratore globale
- Teams Amministratore

Per altre informazioni sui ruoli di amministratore in Teams, vedere Usare i ruoli di amministratore di Microsoft Teams per gestire [Teams](using-admin-roles.md)e altre informazioni su come usare i cmdlet di PowerShell per la gestione dei team nella guida di riferimento ai cmdlet di [Microsoft Teams.](/powershell/teams/?view=teams-ps)



## <a name="teams-overview-grid"></a>Teams griglia panoramica

Gli strumenti di gestione per i team **si** Teams nodo Microsoft Teams di amministrazione. Nell'interfaccia di amministrazione selezionare **Teams**  >  **Gestire i team.)** Ogni team è supportato da un gruppo Microsoft 365 e questo nodo offre una visualizzazione dei gruppi abilitati Microsoft Teams nell'organizzazione.

![Screenshot della griglia Teams panoramica](media/manage-teams-in-modern-portal-grid.png)  

La griglia visualizza le proprietà seguenti:

- **Nome del team**
- **Canali:** conteggio di tutti i canali del team, incluso il canale generale predefinito.
- **Membri del** team: numero totale di utenti, inclusi proprietari, guest e membri del tenant.
- **Proprietari:** numero di proprietari per questo team.
- **Guest:** numero di Azure Active Directory utenti guest B2B che sono membri di questo team.
- **Privacy:** visibilità/AccessType del gruppo di Microsoft 365 di backup.
- **Stato:** lo stato Archiviato o Attivo per questo team. Altre informazioni sui team di archiviazione in [Archiviare o ripristinare un team.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)
- **Descrizione:** descrizione del gruppo di Microsoft 365 di backup.
- **Classificazione:** classificazione (se usata nell'organizzazione) assegnata al gruppo di Microsoft 365 di backup. Per altre informazioni sulle classificazioni, vedere [Creare classificazioni per Office gruppi nell'organizzazione.](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- **GROUPID:** l'ID Gruppo univoco del gruppo Microsoft 365 di backup.

> [!NOTE]
> Se tutte queste proprietà non sono visualizzate nella griglia, fare clic **sull'icona Modifica** colonne. Nel riquadro **Modifica colonne** è possibile usare gli interruttori per attivare o disattivare le colonne nella griglia. Al termine, fare clic su **Applica.**

### <a name="add"></a>Aggiungi

Per aggiungere un nuovo team, fare clic su **Aggiungi**. Nel riquadro **Aggiungi un nuovo team** assegnare un nome e una descrizione al team, specificare se si vuole impostarlo come team privato o pubblico e impostare la classificazione.

> [!NOTE]
> I team appena creati possono essere gestiti immediatamente nell'interfaccia di amministrazione di Teams, a differenza dell'esperienza di altri client come Outlook.

### <a name="edit"></a>Modifica

Per modificare le impostazioni specifiche del gruppo e del team, selezionare il team facendo clic a sinistra del nome del team e quindi selezionare **Modifica**.

### <a name="archive"></a>Archivia

È possibile archiviare un team. L'archiviazione di un team consente al team di entrare in modalità di sola lettura all'interno Teams. Gli amministratori possono archiviare e annullare l'archiviazione dei team per conto dell'organizzazione nell'interfaccia di amministrazione. 

### <a name="delete"></a>Elimina

L'eliminazione di un team è un'eliminazione soffice del team e del gruppo Microsoft 365 gruppo. Per ripristinare un team eliminato per errore, seguire le istruzioni in [Ripristinare un gruppo eliminato.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Ricerca

La ricerca attualmente supporta la stringa "Inizia con" ed esegue la ricerca nel **campo Nome** team.

## <a name="team-profile"></a>Profilo del team

È possibile passare alla pagina del profilo del team di qualsiasi team dalla griglia di panoramica dei team principali facendo clic sul nome del team. La pagina del profilo del team mostra i membri, i proprietari e gli utenti guest che appartengono al team (e il relativo gruppo di Microsoft 365 di supporto), nonché i canali e le impostazioni del team. Dalla pagina del profilo del team è possibile:

- Aggiungere o rimuovere membri e proprietari.
- Aggiungere o rimuovere canali (si noti che non è possibile rimuovere il canale Generale).
- Modificare le impostazioni del team e del gruppo.
 
![Screenshot di un profilo del team di esempio](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Apportare modifiche ai team

Nella pagina del profilo del team è possibile modificare gli elementi seguenti di un team:

- **Membri:** aggiungere o rimuovere membri e alzare o abbassare di livello i proprietari.
- **Canali:** aggiungere nuovi canali e modificare o rimuovere i canali esistenti. Tenere presente che non è possibile eliminare il canale generale predefinito.
- **Nome del team**
- **Descrizione**
- **Privacy:** specificare se il team è pubblico o privato.
- **Classificazione:** questa opzione è supportata dalle Microsoft 365 di gruppo. Scegliere **Riservato,** **Altamente riservato** o **Generale.**
- **Impostazioni conversazioni:** consente di specificare se i membri possono modificare ed eliminare i messaggi inviati.
- **Impostazioni canali:** consente di specificare se i membri possono creare nuovi canali e modificare quelli esistenti e aggiungere, modificare e rimuovere schede, connettori e app.

Le modifiche apportate a un team vengono registrate. Se si modificano le impostazioni del gruppo (modificando il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), le modifiche vengono attribuite tramite la pipeline di controllo. Se si eseguono azioni Teams impostazioni specifiche, le modifiche vengono rilevate e attribuite all'utente nel canale Generale del team.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Problema: Teams nella griglia panoramica del team**

Alcuni dei team non sono presenti nell'elenco dei team nella griglia Teams panoramica.

**Causa:** questo problema si verifica quando il team è stato profilato in modo non corretto (o non ancora) dal sistema, causando la perdita di una proprietà per il riconoscimento.

**Soluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**

Sostituire **{groupid}** nella query per l'effettivo GroupId in questione, che è possibile ottenere tramite powershell di Exchange Online, con il cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** come attributo "**ExternalDirectoryObjectId**".

1. Accedere [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

2. Accedere a Graph Explorer nel menu a sinistra.

3. Modificare la riga della query in: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .

4. Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["Team"]}.

5. Eseguire la query in alto a destra.

6. Verificare che il team venga visualizzato correttamente nell'interfaccia Microsoft Teams di amministrazione - Panoramica del team.

## <a name="learn-more"></a>Altre informazioni

- [Teams cmdlet](/powershell/teams/?view=teams-ps)  
- [Usare Teams di amministratore per gestire i Teams](using-admin-roles.md)
- [Pianificare la gestione del ciclo di vita in Teams](plan-teams-lifecycle.md)