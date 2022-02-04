---
title: Configurazione dell'amministratore per l'app Genitori EDU Microsoft in Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams per l'EDU che documenta i prerequisiti e la configurazione per l'app Genitori.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f35d4f3037735f2122d26a2b9b24cf3a38f3bc99
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363232"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Distribuzione dell'app Genitori in Microsoft Teams

L'app Genitori aiuta i docenti Teams connettersi e interagire in modo sicuro con i genitori e i tutori degli studenti nei team di classe usando una chat Teams, che verrà scalata in tutta l'organizzazione dei docenti. Il provisioning di tutti i dati dei genitori e dei tutori viene eseguito School Data Sync, consentendo al personale IT di configurare le attività senza problemi.

## <a name="requirements"></a>Requisiti

### <a name="school-data-sync"></a>School Data Sync

- È necessario School Data Sync (SDS) per popolare le informazioni di contatto correlate al genitore e al **tutore di ogni** studente.
  - [Distribuire SDS](/schooldatasync/parents-and-guardians-in-sds)

- Se è necessaria assistenza nella configurazione di SDS e nella compilazione dei contatti correlati a genitori **e tutori** per gli studenti del tenant, contattare il team customer success di EDU per:
  - Completamento del processo RFA in [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Apertura di un ticket presso [il supporto](https://aka.ms/sdssupport).

### <a name="teams-admin-center---policies"></a>Teams di amministrazione - Criteri

- I proprietari del team di classe devono avere Teams chat abilitata.
- I proprietari dei team di classe devono avere accesso **esterno con Teams account non gestiti da un'organizzazione** abilitata.
  - Questa opzione deve essere abilitata a livello di tenant e di utente. L'impostazione a livello di tenant è disponibile in **Utenti > accesso esterno** nell'Teams di amministrazione. Questa impostazione è accessibile anche tramite PowerShell. I criteri di accesso esterno a livello utente sono accessibili solo tramite PowerShell. Per altre indicazioni, vedere i comandi di PowerShell seguenti.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Abilitazione dell'accesso esterno con Teams account non gestiti da un'organizzazione

1. Installare l'anteprima del Microsoft Teams di PowerShell più recente.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Usando credenziali con privilegi di amministratore, eseguire i comandi seguenti:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

L'impostazione dei criteri che abilita l'accesso esterno con account Teams non gestiti da un'organizzazione a livello di utente (`EnableTeamsConsumerAccess`) è abilitata per impostazione predefinita per tutti i criteri di accesso esterno a livello di utente. Sia l'impostazione a livello di tenant che l'impostazione dei criteri a livello di utente devono essere abilitate perché un utente abbia accesso esterno con account Teams non gestiti da un'organizzazione abilitata. Se non si vuole che questo accesso sia abilitato per tutti gli utenti del tenant, è necessario assicurarsi che l'impostazione a livello di tenant sia disabilitata, aggiornare i criteri di accesso esterno a livello di utente assegnati agli utenti e quindi abilitare l'impostazione a livello di tenant.

Per verificare quali criteri di accesso esterno a livello utente esistono e a chi sono assegnati, è possibile usare la procedura seguente:
    
3. Verificare quali criteri di accesso esterno a livello di utente esistono.

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

- Assegnare un criterio a un set di utenti: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

Dopo aver impostato correttamente i criteri di accesso esterno a livello utente per gli utenti del tenant, è possibile abilitare l'impostazione a livello di tenant (`AllowTeamsConsumer`) per il tenant usando il cmdlet seguente:

- Impostare le impostazioni di configurazione della federazione per il tenant: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="enabling-the-parents-app"></a>Abilitazione dell'app Genitori

L'app Genitori è disabilitata per impostazione predefinita, quindi i proprietari dei team di classe non potranno vedere l'app nei team di classe finché l'app non è consentita tramite l'interfaccia di amministrazione Teams di amministrazione. L'app può essere consentita tramite l'Teams di amministrazione usando [Consenti app bloccate dagli editori](manage-apps.md#apps-blocked-by-publishers).

In qualsiasi momento, l'app può essere disabilitata a livello di tenant usando Consenti e blocca [le app](manage-apps.md#allow-and-block-apps) nell'Teams di amministrazione. Se l'app è disabilitata a livello di tenant, verrà bloccata per tutti gli utenti, anche se sono abilitate le autorizzazioni a livello di utente.

L'app può essere disabilitata anche a livello di utente usando [Gestisci criteri di autorizzazione dell'app in Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Altre informazioni

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
