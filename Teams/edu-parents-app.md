---
title: Amministrazione configurazione di Genitori in Teams per l'istruzione
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Articolo di Microsoft Teams che documenta i prerequisiti e la configurazione dei genitori in Teams per l'istruzione.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5edde0613c9092a7ed48d57a4a22761e56eee142
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329060"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurare la connessione padre in Microsoft Teams per l'istruzione

La connessione padre in Teams per l'istruzione consente ai docenti di connettersi in modo sicuro e interagire con i genitori e i tutori degli studenti nei loro team di classe usando Teams.

Questo articolo fornisce indicazioni ai professionisti IT del settore didattico sui requisiti e la configurazione della connessione padre.

## <a name="share-guardian-and-educator-resources"></a>Condividere risorse per tutori e docenti

Ecco alcune risorse che gli amministratori IT possono condividere con tutori e docenti su come iniziare a usare la connessione padre.

- Per indicazioni su come configurare i tutori, vedere [Connettersi con i docenti in Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).
- Per indicazioni su come configurare i docenti, vedere [Comunicare con i tutori in Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

## <a name="benefits-of-parent-connection"></a>Vantaggi della connessione padre

La connessione genitori consente a docenti e tutori di chattare, inviare e-mail e chiamare con Teams.

- I docenti possono avviare chat con i tutori.
  - Se il tutore non ha un account per utenti finali di Teams o non si è ancora unito a Teams, riceverà il messaggio dal docente insieme a un invito tramite posta elettronica a passare a Teams. Questo vale solo nei casi in cui non sono stati raggiunti i limiti dell'invito e la chat è una nuova chat o una chat esistente che è stata immessa nuovamente dalla connessione padre.
- Funziona con la chat supervisionata. Per altre informazioni, vedere [Usare le chat supervisionate in Microsoft Teams](supervise-chats-edu.md).
  - Per impostazione predefinita, i tutori hanno autorizzazioni limitate, quindi non possono chattare con gli studenti o rimuovere utenti dalle chat.
  - Questa impostazione può essere modificata dall'amministratore del tenant.
- I docenti possono fare clic sull'indirizzo di posta elettronica di un tutore per inviarlo tramite posta elettronica usando il client di posta elettronica nativo.
- I docenti possono fare clic sul numero di telefono di un tutore per chiamarli all'interno di Teams.

> [!IMPORTANT]
> Per la funzionalità click to call in Teams, il tenant deve:
>
> - Funzionalità PBX (Public Branch Exchange).
> - Connessione alla rete PSTN.
>
> i piani Microsoft 365 A1 e A3 non includono funzionalità PBX né connessioni PSTN. È possibile acquistare [licenze per componenti aggiuntivi per ognuna di queste](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) opzioni.
>
> Microsoft 365 A5 piani includono solo funzionalità PBX che usano Sistema telefonico Teams. Dovrai comunque [acquistare un piano per le chiamate di Teams o usare una soluzione di terze parti](pstn-connectivity.md) per connetterti ai numeri esterni nella rete PSTN.
>
> Per altre informazioni su tutte le opzioni per ottenere la connettività PSTN, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).
>
> Per altre informazioni sulle licenze per le chiamate di Teams, vedere [Opzioni di licenza per i componenti aggiuntivi di Teams](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>Requisiti

È necessario usare Microsoft Graph o School Data Sync (SDS) per popolare le informazioni di contatto relative a genitori e tutori di ogni studente.

### <a name="graph-api"></a>API di Microsoft Graph

Se si usa già [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview) per creare identità degli studenti, è possibile includere facilmente [i tipi di risorsa Contatto correlati](/graph/api/resources/relatedcontact).

### <a name="school-data-sync"></a>School Data Sync

I dati di contatto di Teams guardiani rimangono aggiornati con SIS usando School Data Sync (SDS), quando SDS è configurato per la sincronizzazione regolare.

Se un tutore viene rimosso dai record *di uno studente* , le chat esistenti che le coinvolgono conterranno uno striscione visibile al proprietario della chat. Questo banner renderà il proprietario della chat a conoscenza della modifica, chiedendogli di rimuovere il tutore dalla chat. Microsoft non aggiornerà automaticamente l'appartenenza alla chat per rimuovere il tutore.

- È necessario School Data Sync (SDS) per popolare le informazioni di **contatto relative a** genitori e tutori di ogni studente.
  - [Distribuire SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se hai bisogno di assistenza per configurare SDS e popolare **contatti correlati a** genitori e tutori per gli studenti nel tenant, contatta il team Customer Success di EDU:
  - Completamento del processo RFA in [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Apertura di un ticket al [supporto](https://aka.ms/sdssupport) tecnico.

- Attualmente, SDS supporta solo l'inserimento di dati basati su CSV per i contatti padre; tuttavia, è possibile usare [Sincronizzazione API PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) o [Sincronizzazione API OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) per tutti i dati dell'elenco e aggiungere semplicemente i contatti padre con CSV.
  - Creare un secondo profilo di sincronizzazione usando il [formato di sincronizzazione CSV SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Trascinare i due [file padre](/schooldatasync/parent-contact-sync-file-format) popolati con il resto dei file v1 vuoti (solo le intestazioni).
    - User.csv
    - Guardianrelationship.csv
      - Il valore *Ruolo* deve essere completato per ogni genitore e tutore per indicare se è un *genitore* o un *tutore*.
  - Per visualizzare un set di esempio dei file CSV v1, vedere i [file GitHub degli attributi minimi obbligatori](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Se si vuole automatizzare il estrazione dei file CSV dopo la sincronizzazione iniziale, leggere il [documento di automazione Sincronizzazione file CSV](/schooldatasync/csv-file-sync-automation).
  - Per assistenza con la configurazione della sincronizzazione dei dati di SDS, contatta [il team di successo dei clienti](https://www.microsoft.com/fasttrack?rtc=1) o [apri un ticket di supporto](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Criteri dell'interfaccia di amministrazione di Teams

- I proprietari del team di classe devono avere attivato la chat di Teams.
- I proprietari del team di classe devono avere accesso esterno con **gli account di Teams non gestiti da un'organizzazione** attivata.
  - Questa opzione deve essere attivata a livello di tenant e di utente. L'impostazione a livello di tenant è disponibile in **Utenti > Accesso esterno** nell'interfaccia di amministrazione di Teams. Questa impostazione è accessibile anche tramite PowerShell. I criteri di accesso esterno a livello di utente sono accessibili solo tramite PowerShell. Per altre indicazioni, vedere i comandi di PowerShell seguenti.

#### <a name="parent-and-guardian-restrictions"></a>Restrizioni per genitori e tutori

I genitori e i tutori vengono classificati come *utenti esterni* nella connessione Genitori, il che significa che non hanno diritti completi di tenant. Hanno accesso solo alla chat o alle chat di cui fanno parte e ai file, alle immagini e ad altri contenuti condivisi nella chat.

Per le chat esterne, sia gli utenti interni che gli utenti esterni possono aggiungere utenti alla chat. Per altre informazioni sull'esperienza di chat esterna, vedere [Gestire riunioni esterne e chat in Microsoft Teams](manage-external-access.md).

Inoltre, gli utenti esterni possono vedere la presenza (offline, disponibile, occupato e così via) degli utenti dell'organizzazione, ma questa opzione può essere disattivata usando PowerShell per proteggere la privacy degli utenti. In PowerShell, utilizza [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration) e imposta ``EnablePrivacyMode=true``.

Anche se genitori e tutori sono utenti esterni, il loro contributo alle chat è individuabile. Informazioni su come condurre un'indagine di Teams eDiscovery leggendo [Condurre un'indagine eDiscovery sul contenuto in Microsoft Teams](ediscovery-investigation.md).

> [!IMPORTANT]
> Gli amministratori IT devono informare tutti i proprietari della classe sulle procedure consigliate per condividere le informazioni degli studenti tramite chat, inclusi i rischi per la privacy degli studenti.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>Bloccare un genitore o un tutore in una chat

I docenti possono bloccare un tutore nella chat avviata nella connessione padre.

Il proprietario della classe può:

1. Apri la scheda del profilo del tutore, seleziona i puntini di sospensione e **Blocca utente**.
2. Quindi, rimuovi il tutore dalla chat.

L'utente bloccato non sarà in grado di avviare altre chat con il proprietario della classe.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Consentire l'accesso esterno con account di Teams non gestiti da un'organizzazione

Per consentire ai docenti di comunicare con genitori e tutori in Teams, l'amministratore IT del tenant per l'istruzione deve aggiornare i criteri del tenant per consentire l'accesso esterno per gli account di Teams all'esterno del tenant. Per altre informazioni sulla gestione dell'accesso esterno, vedere [Gestire l'accesso esterno in Microsoft Teams](manage-external-access.md).

Ecco i passaggi per attivare l'accesso esterno per genitori e tutori.

1. Installare l'anteprima del modulo PowerShell più recente di Microsoft Teams.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Usando credenziali con privilegi di amministratore, eseguire i comandi seguenti:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    L'impostazione dei criteri che attiva l'accesso esterno con account di Teams non gestiti da un'organizzazione a livello di utente (`EnableTeamsConsumerAccess`) è attivata per impostazione predefinita per tutti i criteri di accesso esterno a livello utente. Sia l'impostazione a livello di tenant che l'impostazione dei criteri a livello di utente devono essere attivate affinché un utente possa avere accesso esterno con account di Teams non gestiti da un'organizzazione. Se non si vuole che l'accesso sia attivato per tutti gli utenti del tenant, verificare che l'impostazione a livello di tenant sia disattivata, aggiornare i criteri di accesso esterno a livello utente assegnati agli utenti e quindi attivare l'impostazione a livello di tenant.

    Per verificare quali criteri di accesso esterno a livello utente esistono e a chi sono assegnati, è possibile usare la procedura seguente:

3. Verificare che siano presenti criteri di accesso esterno a livello utente.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Per ogni criterio diverso dal criterio "Globale", verificare quali utenti hanno assegnato il criterio.

   > [!NOTE]
   > Tutti gli utenti a cui non è assegnato un criterio specifico torneranno al criterio "Globale". Ai nuovi utenti aggiunti al tenant verrà assegnato il criterio "Globale".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Poiché tutti i criteri di accesso esterno a livello utente sono impostati `EnableTeamsConsumerAccess` su true per impostazione predefinita, se si vuole modificare l'impostazione `EnableTeamsConsumerAccess` per utenti specifici, è possibile creare/modificare criteri di accesso esterno esistenti con impostazioni modificate e/o riassegnare gli utenti a criteri nuovi o esistenti usando i cmdlet di PowerShell seguenti:

- Creare un nuovo criterio di accesso esterno: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizzare un criterio di accesso esterno esistente (incluso il criterio "Globale"): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Non è possibile modificare i criteri predefiniti della sottoscrizione seguenti: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. Il criterio 'FederationAndPICDefault' era assegnato a tutti gli utenti per impostazione predefinita, tuttavia ai nuovi utenti è ora assegnato il criterio "Globale" per impostazione predefinita. Se è necessario modificare le impostazioni dei criteri per gli utenti a cui sono assegnati questi criteri predefiniti dell'abbonamento, assegnare criteri diversi con le impostazioni corrette a questi utenti.

- Assegnare criteri di accesso esterno a un singolo utente: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Assegnare un criterio a un set di utenti: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Dopo aver impostato correttamente i criteri di accesso esterno a livello utente per gli utenti del tenant, è possibile attivare l'impostazione a livello di tenant (`AllowTeamsConsumer`) per il tenant usando il cmdlet seguente:

- Impostare le impostazioni di configurazione della federazione per il tenant: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Attivare l'app Genitori nell'interfaccia di amministrazione di Teams

L'app Genitori è disattivata per impostazione predefinita, quindi i proprietari dei team di classe non la vedranno nei loro team di classe finché non è consentita tramite l'interfaccia di amministrazione di Teams. L'app Genitori è attivata nell'interfaccia di amministrazione di Teams usando [Consenti app bloccate dagli sviluppatori](manage-apps.md#allow-the-apps-that-are-blocked-by-the-developers).

In qualsiasi momento, l'app può essere disattivata a livello di tenant usando [Consenti e blocca le app](manage-apps.md#allow-and-block-apps) nell'interfaccia di amministrazione di Teams. Se è disattivata a livello di tenant, verrà bloccata per tutti gli utenti, anche se sono attivate le autorizzazioni a livello di utente.

L'app Genitori può anche essere disattivata a livello di utente usando [Gestisci criteri di autorizzazione app in Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Altre informazioni

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
