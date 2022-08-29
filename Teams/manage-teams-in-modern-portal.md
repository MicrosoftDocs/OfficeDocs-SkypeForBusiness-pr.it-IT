---
title: Gestire i team nell'interfaccia di amministrazione di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Informazioni su come visualizzare o aggiornare i team che l'organizzazione ha configurato per la collaborazione nell'Interfaccia di amministrazione di Microsoft Teams.
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fca16f3b09fc153717b24161eb8717f419171677
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396327"
---
# <a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Gestire i team nell'interfaccia di amministrazione di Microsoft Teams

## <a name="overview"></a>Panoramica

Questo articolo offre una panoramica degli strumenti di gestione per Teams nell'Interfaccia di amministrazione di Microsoft Teams.

L'amministratore potrebbe dover visualizzare o aggiornare i team che l'organizzazione ha impostato per la collaborazione oppure potrebbe dover eseguire azioni correttive come l'assegnazione di proprietari per i team senza proprietario. È possibile gestire i team usati nell'organizzazione tramite il modulo di PowerShell di Microsoft Teams e l'Interfaccia di amministrazione di Microsoft Teams. È possibile accedere all'Interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>. Per le funzionalità di amministrazione complete che usano questi due set di strumenti, è necessario assicurarsi di avere uno dei ruoli seguenti:

- Amministratore globale
- Amministratore di Teams

È possibile ottenere altre informazioni sui ruoli di amministratore in Teams in [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md)e altre informazioni su come usare i cmdlet di PowerShell per la gestione dei team in [Microsoft Teams cmdlet reference](/powershell/teams/).

> [!NOTE]
> Gli amministratori di Skype for Business Online possono gestire **Teams** e i criteri delle app di **Skype for Business Online** tramite PowerShell.

## <a name="teams-overview-grid"></a>Griglia panoramica di Teams

Gli strumenti di gestione per i team si trovano nel nodo **Teams** nell'Interfaccia di amministrazione di Microsoft Teams. Nell'interfaccia di amministrazione selezionare **Teams** >  **Gestire i team**. Ogni team è supportato da un gruppo di Microsoft 365 e questo nodo fornisce una visualizzazione dei gruppi abilitati per Microsoft Teams nell'organizzazione.

![Screenshot della griglia panoramica di Teams.](media/manage-teams-in-modern-portal-grid.png)  

Nella griglia vengono mostrate le seguenti proprietà:

- **Nome del team**
- **Canali**: conteggio di tutti i canali del team, incluso il canale generale predefinito.
- **Membri del team**: un conteggio degli utenti totali, inclusi i proprietari, gli utenti guest e membri del tenant.
- **Proprietari**: il conteggio dei proprietari del team.
- **Guest** : numero di guest B2B di Azure Active Directory che sono membri del team.
- **Privacy**: visibilità/tipo di accesso del gruppo Microsoft 365 di supporto.
- **Stato**: lo stato archiviato o attivo del team. Altre informazioni sull'archiviazione dei team in [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Descrizione**: la descrizione del gruppo di Microsoft 365 di supporto.
- **Classificazione**: la classificazione (se usata nell'organizzazione) assegnata al gruppo di Microsoft 365 di supporto. Per altre informazioni sulle classificazioni, vedere [Creare le classificazioni per i gruppi di Microsoft 365 all'interno dell'organizzazione](/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell#create-classifications-for-microsoft-365-groups-in-your-organization).
- **GroupID**: l'ID gruppo univoco del gruppo di Microsoft 365 di supporto.

> [!NOTE]
> Se nella griglia non sono visualizzate tutte queste proprietà, fare clic sull'icona **Modifica colonne**. Nel riquadro **Modifica colonne** è possibile usare gli interruttori per attivare o disattivare le colonne nella griglia. Al termine, fare clic su **Applica**.

### <a name="add"></a>Aggiungere

Per aggiungere un nuovo team, fare clic su **Aggiungi**. Nel riquadro **Aggiungi un nuovo team** assegnare al team un nome e una descrizione, impostare se si vuole renderlo un team privato o pubblico e impostare la classificazione.

> [!NOTE]
> I team appena creati possono essere gestiti immediatamente nell'Interfaccia di amministrazione di Teams, a differenza dell'esperienza in altri client, ad esempio in Outlook.

Questo video mostra i passaggi per creare un nuovo team e un canale per loro.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53TXG?autoplay=false]

### <a name="edit"></a>Modificare

Per modificare le impostazioni specifiche del gruppo e del team, selezionare il team facendo clic a sinistra del nome del team e quindi selezionare **Modifica**.

Questo video mostra la procedura per visualizzare e modificare i dettagli di un team esistente.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53JpG?autoplay=false]

### <a name="archive"></a>Archiviare

È possibile archiviare un team. L'archiviazione di un team attiva la modalità di sola lettura all'interno di Teams. L'amministratore può archiviare e annullare l'archiviazione dei team per conto dell'organizzazione nell'interfaccia di amministrazione. 

### <a name="delete"></a>Eliminare

L'eliminazione di un team consiste nell'eliminazione temporanea del team e del gruppo di Microsoft 365 corrispondente. Per ripristinare un team eliminato per errore, seguire le istruzioni in [Ripristinare un gruppo eliminato](/microsoft-365/admin/create-groups/restore-deleted-group).

### <a name="search"></a>Eseguire una ricerca

Al momento, la ricerca supporta la stringa "Inizia con" ed esegue una ricerca nel campo **Nome del team**.

## <a name="team-profile"></a>Profilo del team

È possibile passare alla pagina del profilo del team dalla griglia di panoramica dei team principali facendo clic sul nome del team. La pagina del profilo del team mostra i membri, i proprietari e gli utenti guest che appartengono al team (e il relativo gruppo Microsoft 365 di supporto), nonché i canali e le impostazioni del team. Dalla pagina del profilo del team è possibile:

- Aggiungere o rimuovere membri e proprietari.
- Aggiungere o rimuovere canali (non è possibile rimuovere il Canale generale).
- Modificare le impostazioni del team e del gruppo.
 
![Screenshot di esempio di un profilo del team.](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Apportare modifiche ai team

Nella pagina del profilo del team è possibile modificare gli elementi seguenti di un team:

- **Membri**: aggiungere o rimuovere membri e alzare o abbassare di livello i proprietari.
- **Canali**: aggiungere nuovi canali e modificare o rimuovere i canali esistenti. Tenere presente che non è possibile eliminare il canale generale predefinito.
- **Nome del team**
- **Descrizione**
- **Privacy**: impostare il team come pubblico o privato.
- **Classificazione**: è supportata dalle classificazioni dei gruppi di Microsoft 365. Scegliere **Riservato**, **Estremamente riservato** o **Generale**.
- **Impostazioni conversazioni**: con questa opzione viene impostato se i membri possono modificare ed eliminare i messaggi inviati.
- **Impostazioni dei canali**: con questa opzione è possibile impostare se i membri possono creare nuovi canali e modificare quelli esistenti e aggiungere, modificare e rimuovere schede, connettori e app.

Le modifiche apportate a un team vengono registrate. Se si modificano le impostazioni del gruppo (il nome, la descrizione, la foto, la privacy, la classificazione o i membri del team), le modifiche vengono attribuite all'utente tramite la pipeline di controllo. Se si eseguono azioni sulle impostazioni specifiche di Teams, le modifiche vengono rilevate e vengono attribuite all'utente nel canale generale del team.

## <a name="troubleshooting"></a>Risoluzione dei problemi

**Problema: Teams mancante nella griglia di panoramica del team**

Alcuni dei team possono non sono presenti nell'elenco dei team nella griglia di panoramica di Teams.

**Causa**: questo problema si verifica quando il team è stato profilato in modo non corretto oppure non è stato ancora profilato dal sistema e questo comporta il riconoscimento di una proprietà mancante per il team.

**Risoluzione: impostare manualmente la proprietà sul valore corretto tramite MS Graph**

Sostiture **{groupid}** nella query dell'effettivo GroupId, che è possibile ottenere tramite Exchange Online PowerShell, con il cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup)"**, con l'attributo "**ExternalDirectoryObjectId**.

1. Accedere a [Graph explorer](https://developer.microsoft.com/graph/graph-explorer).

2. Accedere a Graph Explorer nel menu a sinistra.

3. Modificare la riga della query in PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.

4. Aggiungere il valore seguente nel corpo della richiesta: {"resourceProvisioningOptions": ["Team"]}.

5. Eseguire la query in alto a destra.

6. Verificare che il team sia visualizzato correttamente nell'Interfaccia di amministrazione di Microsoft Teams - Panoramica del team.

## <a name="learn-more"></a>Ulteriori informazioni

- [Teams cmdlet reference](/powershell/teams/)  
- [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).
- [Pianificare la gestione del ciclo di vita in Teams](plan-teams-lifecycle.md)
