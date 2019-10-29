---
title: Usare PowerShell per controllare l'accesso guest a un team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Usare PowerShell per consentire o bloccare l'accesso Guest ai team in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90ca96b6a28b1a94c375af0b4b4166da5bbee9e9
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753331"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Usare PowerShell per controllare l'accesso guest a un team
================================================

Oltre a usare l'interfaccia di amministrazione di Microsoft 365 e il portale di Azure Active Directory (Azure AD), è possibile usare Windows PowerShell per controllare l'accesso guest. Con PowerShell è possibile eseguire le operazioni seguenti:
  
- Consentire o bloccare l'accesso Guest a tutti i team e gruppi di Office 365

- Consentire l'aggiunta di Guest a tutti i team e gruppi di Office 365

- Consentire o bloccare gli utenti Guest da un team specifico o da un gruppo di Office 365

Per informazioni dettagliate, vedere "usare PowerShell per controllare l'accesso guest" in [gestire l'accesso guest nei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).

  
È anche possibile usare PowerShell per consentire o bloccare un utente guest in base al proprio dominio. Ad esempio, supponiamo che la tua azienda (contoso) abbia una partnership con un'altra azienda (Fabrikam). È possibile aggiungere Fabrikam all'elenco consentiti in modo che gli utenti possano aggiungere tali Guest ai rispettivi gruppi. Per altre informazioni, vedere [consentire/bloccare l'accesso Guest ai gruppi di Office 365](https://go.microsoft.com/fwlink/?linkid=854001).
  
Se si vuole bloccare gli ospiti in teams e si vuole comunque consentire loro di accedere ai siti di SharePoint, è possibile usare i cmdlet di Azure AD PowerShell per disabilitare il parametro AllowGuestsToAccessGroups nell'oggetto società, presupponendo che la condivisione esterna sia attivata per i siti di SharePoint .

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usare PowerShell per attivare o disattivare l'accesso Guest

1.  Scaricare il modulo di PowerShell per Skype for business online dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Connettere una sessione di PowerShell all'endpoint di Skype for business online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Controlla la configurazione e, `AllowGuestUser` se `$False`lo è, usa il cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) per impostarlo su `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
È ora possibile avere utenti guest in teams per l'organizzazione.


## <a name="guest-access-vs-external-access"></a>Accesso guest e accesso esterno

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
