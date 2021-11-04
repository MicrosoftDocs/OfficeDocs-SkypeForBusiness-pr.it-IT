---
title: Configurazione dell'amministratore per l'app Microsoft Parents EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams prerequisiti del documento dell'articolo EDU e configurazione di PowerShell per l'app Genitori.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785149"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Distribuzione dell'app padre in Microsoft Teams

L'app Per genitori aiuta i docenti Teams connettersi e interagire in modo sicuro con i genitori e i tutori degli studenti delle loro classi usando una chat Teams, che verrà scalata in tutta l'organizzazione dei docenti. Il provisioning di tutti i dati dei genitori e dei tutori viene eseguito School Data Sync, consentendo ai docenti e al personale IT di configurare le attività senza problemi.

## <a name="requirements"></a>Requisiti

### <a name="school-data-sync"></a>School Data Sync

- È necessario School Data Sync (SDS) per popolare le informazioni di contatto correlate **a ogni** studente.
  - [Distribuire SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Per assistenza nella configurazione di SDS e nell'abilitazione dei contatti padre nel tenant, contattare il team EDU Customer Success per:
  - Completamento del processo RFA in [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Apertura di un ticket su [Supporto](https://aka.ms/sdssupport).

### <a name="teams-admins-center---policies"></a>Teams Interfaccia di amministrazione - Criteri

- Il proprietario della classe deve avere la chat abilitata
- Il proprietario della classe deve avere accesso **esterno con Teams account non gestiti da un'organizzazione** abilitata. 
  - Questa impostazione è disponibile in Utenti > Accesso esterno per il livello di tenant oppure, se si desidera abilitare un determinato set di utenti, vedere powershell di seguito.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Abilitazione della chat federata per singolo utente

1. Installare l'anteprima del Microsoft Teams di PowerShell più recente.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Usando credenziali con privilegi di amministratore, eseguire il comando seguente in una finestra di comando:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

L'impostazione dei criteri che Teams l'accesso esterno a livello di utente (EnableTeamsConsumerAccess) è abilitata per impostazione predefinita per tutti i criteri di accesso esterno a livello di utente. Sia l'impostazione a livello di tenant (AllowTeamsConsumer) che l'impostazione dei criteri a livello di utente devono essere abilitate per consentire a un utente Teams accesso esterno consumer. Se non si vuole che tutti gli utenti del tenant attivino l'accesso esterno Teams un utente, è consigliabile aggiornare i criteri di accesso esterno Teams livello utente assegnati agli utenti prima di abilitare l'impostazione a livello di tenant.

Se è necessario verificare quali criteri di accesso esterno a livello di utente esistono e a chi sono assegnati, è possibile eseguire la procedura seguente:
    
3. Verificare quali criteri di accesso esterno a livello di utente esistono.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Per ogni criterio diverso da quello "Globale", verificare a quali utenti è assegnato il criterio. Nota: tutti gli utenti a cui non è assegnato un criterio specifico verranno rientrati nel criterio "Globale"

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Altre opzioni di PowerShell

Poiché tutti i criteri di accesso esterno a livello di utente hanno EnableTeamsConsumerAccess impostato su true per impostazione predefinita, se si vuole aggiornare uno di questi criteri per modificare l'impostazione EnableTeamsConsumerAccess, è possibile creare nuovi criteri di accesso esterno con le impostazioni modificate oppure riassegnare gli utenti ai criteri nuovi o esistenti tramite la powershell seguente:

- Creare un nuovo criterio di accesso esterno, che crea un nuovo criterio di accesso esterno e definisce le impostazioni: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Personalizzare un criterio di accesso esterno esistente (modifica le impostazioni di un criterio di accesso esterno esistente, incluso il criterio [globale):Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Non è possibile modificare le impostazioni predefinite della sottoscrizione seguenti: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Se è necessario modificare le impostazioni dei criteri per gli utenti a cui sono assegnati questi criteri, assegnare a questi utenti criteri diversi con le impostazioni corrette.

- Assegnare criteri di accesso esterno a un singolo utente: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Assegnare un criterio a un set di utenti: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Quando si è certi che i criteri di accesso esterno Teams livello utente siano impostati correttamente per tutti gli utenti, è possibile abilitare l'impostazione a livello di tenant che controlla l'accesso esterno consumer Teams per il tenant usando il cmdlet seguente:

- Impostare le impostazioni di configurazione della federazione per il tenant (Impostazione di AllowTeamsConsumer su true): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Disabilitazione dell'app Genitori

L'app Genitori è abilitata per impostazione predefinita, quindi tutti i proprietari della classe potranno vedere l'app nel team di classe. L'app può essere disabilitata a livello di tenant usando Consenti e blocca [le app](manage-apps.md#allow-and-block-apps) nell'Microsoft Teams di amministrazione. Se questa opzione è disabilitata a livello di tenant, verrà bloccata per tutti gli utenti, anche se l'autorizzazione a livello di utente è abilitata.

Questa opzione può essere disabilitata anche a livello di utente usando [Gestire i criteri di autorizzazione delle app in Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Altre informazioni

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Assegnazione dei criteri a un utente](/powershell/module/skype/grant-csexternalaccesspolicy)
