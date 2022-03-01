---
title: Configurazione dell'amministratore dei genitori in Teams per l'istruzione
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams articolo che documenta i prerequisiti e la configurazione dei genitori in Teams per l'istruzione.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af6433cb3e5ca0e1849322bdd128915e826e219b
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "63040064"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Configurare la connessione padre in Microsoft Teams per l'istruzione

Parent Connection in Teams per l'istruzione aiuta i docenti a connettersi e interagire in modo sicuro con i genitori e i tutori degli studenti nei team di classe usando una chat Teams, che verrà scalata in tutta l'organizzazione dell'educatore. Il provisioning di tutti i dati dei genitori e dei tutori viene eseguito School Data Sync, consentendo al personale IT di configurare le attività senza problemi.

Dopo aver configurato genitori e tutori, possono chattare con i docenti dei loro studenti usando Teams chat. Per indicazioni su come collegare genitori e tutori agli educatori, vedere Connessione [con i docenti in Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

I genitori collaborano anche con la chat supervisionata. Genitori e tutori non hanno le autorizzazioni Teams, il che significa che non possono avviare conversazioni con gli studenti o rimuovere utenti con autorizzazioni complete (ad esempio docenti) dalle chat. Per altre informazioni sulla chat supervisionata, vedere [Usare chat supervisionate in Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>Requisiti

### <a name="school-data-sync"></a>School Data Sync

- È necessario School Data Sync (SDS) per popolare le informazioni di contatto correlate al genitore e al **tutore di ogni** studente.
  - [Distribuire SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se è necessaria assistenza nella configurazione di SDS e nella compilazione dei contatti correlati a genitori **e tutori** per gli studenti del tenant, contattare il team customer success di EDU per:
  - Completamento del processo RFA in [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Apertura di un ticket presso [il supporto](https://aka.ms/sdssupport).

- Attualmente, SDS supporta solo l'inserimento di dati basati su CSV per i contatti padre. Tuttavia, è possibile usare [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) o [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) per tutti i dati dell'elenco e aggiungere semplicemente i contatti padre usando CSV.
  - Creare un secondo profilo di sincronizzazione usando il [formato di sincronizzazione CSV SDS v1](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Estrarre i due file [padre popolati](/schooldatasync/parent-contact-sync-file-format) con il resto dei file v1 vuoti (solo le intestazioni).
    - User.csv
    - Guardianrelationship.csv
  - Per visualizzare un set di esempio dei file CSV v1, vedere la sezione Attributi [obbligatori minimi GitHub file](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Se si vuole automatizzare il pull dei file CSV dopo la sincronizzazione iniziale, leggere il documento [CSV File Sync Automation](/schooldatasync/csv-file-sync-automation).
  - Per assistenza con la configurazione della sincronizzazione dei dati SDS, contatta il [nostro team](https://www.microsoft.com/fasttrack?rtc=1) di successo del cliente o [apri un ticket di supporto](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams di amministrazione - Criteri

- I proprietari del team di classe devono avere Teams chat attivata.
- I proprietari dei team di classe devono avere **accesso esterno con Teams account non gestiti da un'organizzazione** attivata.
  - Questa opzione deve essere attivata a livello di tenant e di utente. L'impostazione a livello di tenant è disponibile in **Utenti > accesso esterno** nell'Teams di amministrazione. Questa impostazione è accessibile anche tramite PowerShell. I criteri di accesso esterno a livello utente sono accessibili solo tramite PowerShell. Per altre indicazioni, vedere i comandi di PowerShell seguenti.

> [!NOTE]
>I genitori e i tutori sono classificati come utenti esterni nella caratteristica Genitori, il che significa che non hanno diritti di tenant completi. Hanno accesso solo alla chat o alle chat a cui vengono aggiunti, oltre a file, immagini e altri contenuti condivisi nella chat.
>
>Inoltre, gli utenti esterni possono vedere la presenza (offline, disponibile, occupato e così via) degli utenti dell'organizzazione, ma questa opzione può essere disattivata usando PowerShell per proteggere la privacy degli utenti. In PowerShell usare [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration?view=skype-ps) e impostare ``EnablePrivacyMode=true``.
>
>Anche se genitori e tutori sono utenti esterni, i loro contributi alle chat sono individuabili. Per informazioni su come condurre un'Teams eDiscovery, vedere Condurre [un'indagine di eDiscovery sui contenuti in Microsoft Teams](ediscovery-investigation.md).

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Consentire l'accesso esterno con Teams account non gestiti da un'organizzazione

Per consentire ai docenti di comunicare con genitori e tutori in Teams, l'amministratore IT del tenant dell'istruzione deve aggiornare i criteri del tenant per consentire l'accesso esterno per gli account Teams esterni al tenant. Per altre informazioni sulla gestione dell'accesso esterno, vedere [Gestire l'accesso esterno in Microsoft Teams](manage-external-access.md).

Ecco i passaggi per attivare l'accesso esterno per genitori e tutori.

1. Installare l'anteprima Microsoft Teams modulo di PowerShell più recente.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Usando credenziali con privilegi di amministratore, eseguire i comandi seguenti:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    L'impostazione dei criteri che attiva l'accesso esterno con account Teams non gestiti da un'organizzazione a livello di utente (`EnableTeamsConsumerAccess`) è attivata per impostazione predefinita per tutti i criteri di accesso esterno a livello di utente. Sia l'impostazione a livello di tenant che l'impostazione dei criteri a livello di utente devono essere attivate perché un utente abbia accesso esterno con account Teams non gestiti da un'organizzazione. Se non si vuole che questo accesso sia attivato per tutti gli utenti del tenant, è necessario assicurarsi che l'impostazione a livello di tenant sia disattivata, aggiornare i criteri di accesso esterno a livello di utente assegnati agli utenti e quindi attivare l'impostazione a livello di tenant.

    Per verificare quali criteri di accesso esterno a livello di utente esistono e a chi sono assegnati, è possibile usare la procedura seguente:

3. Verificare che esistano criteri di accesso esterno a livello di utente.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Per ogni criterio diverso da quello "Globale", verificare a quali utenti è assegnato il criterio.

   > [!NOTE]
   > Tutti gli utenti a cui non è assegnato un criterio specifico verranno rientrati nel criterio "Globale". A tutti i nuovi utenti aggiunti al tenant verrà assegnato il criterio "Globale".

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Poiché tutti i criteri di accesso esterno a livello di utente sono impostati su true per impostazione predefinita, `EnableTeamsConsumerAccess` se si vuole modificare l'impostazione per utenti specifici, è possibile creare/modificare i criteri di accesso esterno esistenti con le impostazioni modificate e/o riassegnare gli utenti ai criteri nuovi o esistenti usando i cmdlet di PowerShell seguenti:

- Creare un nuovo criterio di accesso esterno: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizzare un criterio di accesso esterno esistente (incluso il criterio "Globale ["): Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Non è possibile modificare i criteri predefiniti della sottoscrizione seguenti: 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'. Il criterio 'FederationAndPICDefault' è stato assegnato a tutti gli utenti per impostazione predefinita, tuttavia ai nuovi utenti viene assegnato il criterio "Globale" per impostazione predefinita. Se è necessario modificare le impostazioni dei criteri per gli utenti a cui sono assegnati questi criteri predefiniti per l'abbonamento, assegnare a questi utenti criteri diversi con le impostazioni corrette.

- Assegnare criteri di accesso esterno a un singolo utente: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Assegnare un criterio a un set di utenti: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

Dopo aver impostato correttamente i criteri di accesso esterno a livello utente per gli utenti del tenant, è possibile attivare l'impostazione a livello di tenant (`AllowTeamsConsumer`) per il tenant usando il cmdlet seguente:

- Impostare le impostazioni di configurazione della federazione per il tenant: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Attivare l'app Genitori nell'interfaccia Teams di amministrazione

L'app Genitori è disattivata per impostazione predefinita, quindi i proprietari dei team di classe non la visualizzano nei team di classe finché non viene consentita tramite l'interfaccia Teams di amministrazione. L'app Genitori è attivata nell'Teams di amministrazione usando [Consenti app bloccate dagli editori](manage-apps.md#apps-blocked-by-publishers).

In qualsiasi momento, l'app può essere disattivata a livello di tenant usando Consenti e blocca [le app](manage-apps.md#allow-and-block-apps) nell'Teams di amministrazione. Se è disattivata a livello di tenant, verrà bloccata per tutti gli utenti, anche se le autorizzazioni a livello di utente sono attivate.

L'app Genitori può essere disattivata anche a livello di utente usando Gestisci criteri di [autorizzazione app in Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Altre informazioni

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
