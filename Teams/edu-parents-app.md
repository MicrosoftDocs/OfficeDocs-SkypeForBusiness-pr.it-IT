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
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475909"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Distribuzione dell'app padre in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L'abilitazione dell'app genitori in Microsoft Teams è un processo semplice per gli amministratori, che offre un metodo sicuro per consentire ai docenti di comunicare agli studenti e ai loro contatti che rimangono in tenant e che verranno scalati in tutta l'organizzazione dei docenti.

## <a name="requirements"></a>Requisiti

- SDS (School data sync) - È necessario caricare i contatti correlati associati agli studenti in SDS usando l'opzione CSV. Per altre informazioni, vedere [](/graph/api/relatedcontact-update) Configurare [CSV per SDS](/schooldatasync/set-up-your-sds-flow) e Aggiornare i contatti correlati.
- Nell Teams di amministrazione, il proprietario  della classe deve avere la chat abilitata e la **chat** federata con Teams account non gestiti **da un'organizzazione.**

Se è necessario abilitare la chat federata per singolo utente, la procedura è la seguente.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Abilitazione della chat federata per singolo utente

1. Installare l'anteprima del Microsoft Teams di PowerShell più recente.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Eseguire in una finestra di comando usando credenziali con privilegi di amministratore.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Disattivare e attivare la configurazione a livello di gruppo/utente globale o a livello di tenant.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > Quando si esegue questo PowerShell, il completamento delle modifiche può richiedere un'ora o più.
    
## <a name="more-information"></a>Altre informazioni

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Assegnazione dei criteri a un utente](/powershell/module/skype/grant-csexternalaccesspolicy)
