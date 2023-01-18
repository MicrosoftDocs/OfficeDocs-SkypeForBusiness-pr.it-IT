---
title: Autenticazione basata su applicazioni nel modulo di Teams PowerShell
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sull'autenticazione basata su applicazioni nel modulo PowerShell di Teams, usato per l'amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60d9bf64233db3f5e615c0904c6eb376f187266c
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812843"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Autenticazione basata su applicazioni nel modulo di Teams PowerShell

L'autenticazione basata su applicazioni è ora supportata nel modulo di PowerShell di Teams con la versione 4.7.1-preview o successiva. Attualmente questa modalità di autenticazione è supportata solo negli ambienti commerciali.


## <a name="cmdlets-supported"></a>Cmdlet supportati

Tutti i cmdlet sono ora supportati, ad eccezione dei cmdlet indicati di seguito. 

  - New-Team
  - [Ottieni| Imposta| Novità| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>Esempi

Gli esempi seguenti illustrano come usare il modulo PowerShell di Teams con l'autenticazione basata sull'app Azure AD: 

- Connettersi usando un'identificazione personale del certificato:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Quando si usa il parametro CertificateThumbprint, il certificato deve essere installato nel computer in cui si esegue il comando. Il certificato deve essere installato nell'archivio certificati utente.
  
- Connettersi usando un oggetto certificato:

  ```powershell
  Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Quando si usa il parametro Certificate, non è necessario installare il certificato nel computer in cui si esegue il comando. Il certificato può essere archiviato in remoto & recuperato durante l'esecuzione dello script. Il parametro Certificato è disponibile nel modulo di Teams PowerShell versione 4.9.2-preview o successiva.
  
- Connettersi usando i token di accesso:
  
  I token di accesso possono essere recuperati tramite l'endpoint login.microsoftonline.com. Richiede due token di accesso: risorse "MS Graph" e "Skype and Teams Tenant Amministrazione API".

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>Come funziona?

Il modulo PowerShell di Teams recupera il token basato sull'app usando l'ID applicazione, l'ID tenant e l'identificazione personale del certificato. All'oggetto applicazione di cui è stato eseguito il provisioning all'interno di Azure AD è assegnato un ruolo di directory, che viene restituito nel token di accesso. Il controllo degli accessi basato sui ruoli (RBAC) della sessione viene configurato usando le informazioni sul ruolo di directory disponibili nel token.


## <a name="setup-application-based-authentication"></a>Configurare l'autenticazione basata sull'applicazione

Per l'autenticazione tramite oggetti applicazione è necessario un onboarding iniziale. L'entità applicazione e l'entità servizio vengono usate in modo intercambiabile, ma un'applicazione è simile a un oggetto di classe mentre un'entità servizio è come un'istanza della classe. Per altre informazioni su questi oggetti, vedere [Oggetti entità applicazione e servizio in Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Di seguito sono indicati i passaggi di esempio per la creazione di applicazioni in Azure Ad, per i passaggi dettagliati fare riferimento a questo [articolo](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Registrare l'applicazione in Azure AD
2. Assegnare autorizzazioni API all'applicazione
   - Per \*i cmdlet -Cs - l'autorizzazione di API Graph Microsoft necessaria è `Organization.Read.All`.
   - Per i cmdlet non \*Cs- le autorizzazioni di Microsoft API Graph necessarie sono `Organization.Read.All`, , `User.Read.All`, `AppCatalog.ReadWrite.All``Group.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All`, `ChannelMember.ReadWrite.All`.  
3. Generare un certificato autofirma
4. Allegare il certificato all'applicazione Azure AD
5. Assegnare [ruoli di Azure AD](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) all'applicazione

All'applicazione devono essere assegnati i ruoli RBAC appropriati. Poiché il provisioning delle app viene eseguito in Azure AD, è possibile usare uno qualsiasi dei ruoli predefiniti supportati.
 
