---
title: Usare i ruoli di amministratore di Microsoft teams per gestire Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: Informazioni su come usare i diversi ruoli amministrativi per gestire i team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8a37857a31220cf04bfe121db8e5d60e2ad58f6
ms.sourcegitcommit: 494e5956619084ff8f0a4f42efb5081c4530488a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "42551023"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usare i ruoli di amministratore di Microsoft teams per gestire Teams

Usando Azure Active Directory (Azure AD), è possibile designare gli amministratori che necessitano di livelli di accesso diversi per la gestione di Microsoft teams. Gli amministratori possono gestire il carico di lavoro di teams intero oppure possono avere autorizzazioni delegate per la risoluzione dei problemi di qualità delle chiamate o per gestire le esigenze di telefonia dell'organizzazione. 

## <a name="teams-roles-and-capabilities"></a>Ruoli e funzionalità di Teams

Sono disponibili quattro ruoli di amministratore di teams: amministratore del servizio teams, amministratore delle comunicazioni di teams, specialista delle comunicazioni di teams e ingegnere del supporto per Communications teams. Esaminare la tabella seguente per capire cosa può fare ogni ruolo e quali strumenti possono essere usati dall'amministratore nell'interfaccia di amministrazione di Microsoft teams e in PowerShell.



<!-- add Global admin role? -->

| Ruolo                                    | Possono eseguire queste attività                                                           | Può accedere agli strumenti seguenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amministratore del servizio Teams             | Gestire il servizio teams e gestire e creare gruppi di Office 365            | Tutto nell'interfaccia di amministrazione di Microsoft teams e nei controlli di PowerShell associati, tra cui:<ul><li> Gestire le riunioni, inclusi criteri di riunione, configurazioni e Bridge di conferenza. <sup>1, 3</sup></li><li>Gestire la voce, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup></li><li>Gestire la messaggistica, inclusi i criteri di messaggistica. <sup>1, 3</sup></li><li>Gestisci tutte le impostazioni a livello di organizzazione, inclusi Federazione, aggiornamento teams e impostazioni client teams. <sup>1, 3</sup></li><li>Gestisci i team dell'organizzazione e le impostazioni associate, inclusa l'appartenenza (gestione dei gruppi supportata tramite PowerShell, gestione del team nell'interfaccia di amministrazione di Teams). <sup>2, 3</sup></li><li>Gestire i dispositivi certificati in team e configurare e assegnare criteri di configurazione. <sup>2</sup></li><li>Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate utente con il set di strumenti di risoluzione dei problemi <sup>3</sup> </li><li> Consente di accedere, monitorare e risolvere i problemi di qualità e affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (Call Quality Dashboard) verso il basso per gli utenti interessati dalla scarsa qualità delle chiamate. Creare nuovi report, aggiornare e rimuovere report in base alle esigenze. Caricare e aggiornare i dati di Call Quality dashboard Building.</li><li> [Pubblicare app nel catalogo dell'app tenant nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)</li></ul> |
| Amministratore comunicazioni Teams      | Gestire le caratteristiche delle chiamate e delle riunioni all'interno del servizio teams.               | Gestire le riunioni, inclusi criteri di riunione, configurazioni e Bridge di conferenza. <sup>1, 3</sup><br><br> Gestire la voce, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup><br><br> Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate utente tramite il set di strumenti di risoluzione dei problemi avanzati. <sup>3</sup> <br><br> Consente di accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (Call Quality Dashboard) verso il basso per gli utenti interessati dalla scarsa qualità delle chiamate. Creare nuovi report, aggiornare e rimuovere report in base alle esigenze. Caricare e aggiornare i dati di Call Quality dashboard Building.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Tecnico supporto comunicazioni Teams   | Risolvere i problemi di comunicazione all'interno di teams usando strumenti **avanzati** . | Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate utente con il set di strumenti di risoluzione dei problemi <sup>3</sup> <br><br> Consente di accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (Call Quality Dashboard) verso il basso per gli utenti interessati dalla scarsa qualità delle chiamate.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Specialista supporto comunicazioni Teams | Risolvere i problemi di comunicazione in teams usando gli strumenti di **base** .    | Pagina del profilo utente di Access per la risoluzione dei problemi delle chiamate nell'analisi delle chiamate. Può vedere solo le informazioni relative allo specifico utente cercato.<sup>3</sup> <br><br> Accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (Call Quality Dashboard).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

<sup>1</sup> [PowerShell-modulo Skype for business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell-modulo Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> interfaccia di [amministrazione di Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to O365 Group management>> 
-->
Per altre informazioni sugli strumenti di amministrazione disponibili per la gestione di Microsoft teams, vedere [gestione di Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Per altre informazioni sui limiti, le specifiche e altri requisiti applicabili ai team, vedere [limiti e specifiche per Microsoft teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Assegnare utenti a ogni ruolo

Puoi assegnare gli utenti a questi ruoli in Azure AD. Per informazioni su come assegnare ruoli amministrativi a un utente in Azure AD, vedere [assegnare un utente ai ruoli di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlet disponibili per ogni ruolo

La maggior parte degli strumenti di PowerShell per questi ruoli di amministratore vive nel modulo di PowerShell per Skype for business ed è importante notare che alcuni dei cmdlet che questi ruoli di amministratore hanno accesso per controllare le impostazioni condivise usate anche per Skype for business online. Il ruolo di amministratore di Skype for business può anche accedere a tutti i cmdlet nel modulo di PowerShell per Skype for business.

Per visualizzare l'elenco completo dei cmdlet attualmente disponibili per un ruolo specifico nel modulo di PowerShell per Skype for business, eseguire le operazioni seguenti:

1. Assegna il ruolo a un utente (e assicurati che l'utente non abbia altri ruoli).
2. Connettersi al modulo di PowerShell per Skype for business:<br>
   un. $session = New-csonlinesession<br>
   b. $Session Import-PSSession<br>
   c. USA **Get-Module** per identificare il nome della sessione importata (si tratta di un nome generato in modo casuale).<br>
3. Usare il nome **Get-Command-module** <*da sopra*> per identificare tutti i cmdlet disponibili

### <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft teams PowerShell](teams-powershell-overview.md)
- [PowerShell per Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Assegnare proprietari e membri del team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

