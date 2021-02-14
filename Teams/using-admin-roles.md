---
title: Usare i ruoli di amministratore di Microsoft Teams per gestire Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: Informazioni su come usare i ruoli amministrativi per designare gli amministratori che hanno bisogno di diversi livelli di accesso per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 637d6e63b0eabdc9517e8d5cd5986ae7661ad118
ms.sourcegitcommit: 032a22c8b61456dcbd798ec390f0ae1ca7d8eda0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357614"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usare i ruoli di amministratore di Microsoft Teams per gestire Teams

Con Azure Active Directory (Azure AD), è possibile designare amministratori che necessitano di livelli di accesso diversi per la gestione di Microsoft Teams. Gli amministratori possono gestire l'intero carico di lavoro di Teams oppure avere autorizzazioni delegate per risolvere i problemi di qualità delle chiamate o gestire le esigenze di telefonia dell'organizzazione.

## <a name="teams-roles-and-capabilities"></a>Ruoli e funzionalità di Teams

Sono disponibili diversi ruoli di amministratore di Teams: Amministratore del servizio Teams, Amministratore delle comunicazioni di Teams, Esperto del supporto per le comunicazioni di Teams, Tecnico del supporto per le comunicazioni di Teams e Amministratore dei dispositivi di Teams. Esaminare la tabella seguente per comprendere le operazioni che ogni ruolo può eseguire e gli strumenti che l'amministratore può usare nell'interfaccia di amministrazione di Microsoft Teams e in PowerShell.

Per seguire la procedura, è necessario essere un amministratore. Le istruzioni per ottenere le autorizzazioni sono riportate in questo articolo.

<!-- add Global admin role? -->

| Ruolo                                    | È possibile eseguire queste attività                                                           | Accesso agli strumenti seguenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amministratore del servizio Teams             | Gestire il servizio Teams, gestire e creare gruppi di Microsoft 365.        | Tutti gli elementi dell'interfaccia di amministrazione di Microsoft Teams e i controlli powerShell associati, tra cui:<ul><li> Gestire le riunioni, inclusi i criteri, le configurazioni e i bridge di conferenza. <sup>1,3</sup></li><li>Gestisci i comandi vocali, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup></li><li>Gestire la messaggistica, inclusi i criteri di messaggistica. <sup>1,3</sup></li><li>Gestire tutte le impostazioni a livello di organizzazione, incluse le impostazioni di federazione, aggiornamento dei team e client dei team. <sup>1,3</sup></li><li>Gestisci i team nell'organizzazione e le impostazioni associate, compresa l'appartenenza (la gestione dei gruppi supportata tramite PowerShell, la gestione dei team nell'interfaccia di amministrazione di Teams). <sup>2,3</sup></li><li>Gestire i dispositivi certificati da Teams e configurare e assegnare criteri di configurazione. <sup>2</sup></li><li>Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> </li><li>Accedere a tutti i report nell'interfaccia di amministrazione di Microsoft Teams</li><li> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti a cui la qualità delle chiamate è scarsa. Crea nuovi rapporti sulla qualità delle chiamate, aggiorna e rimuovi i rapporti di qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio CQD.</li><li> [Pubblicare app nel catalogo app tenant nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)</li></ul> |
| Amministratore comunicazioni Teams      | Gestire le funzionalità di chiamata e riunione all'interno del servizio Teams.               | Gestire le riunioni, inclusi i criteri, le configurazioni e i bridge di conferenza. <sup>1,3</sup><br><br> Gestisci i comandi vocali, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup><br><br> Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> <br><br> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti nel Call Quality Dashboard (CQD) fino agli utenti che sono intasati da una bassa qualità delle chiamate. Crea nuovi rapporti sulla qualità delle chiamate, aggiorna e rimuovi i rapporti di qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio CQD.|
| Tecnico supporto comunicazioni Teams   | Risolvere i problemi di comunicazione all'interno di Teams usando **strumenti** avanzati. | Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> <br><br> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti nel Call Quality Dashboard (CQD) fino agli utenti che sono intasati da una bassa qualità delle chiamate. |
| Teams Communications Support Specialist | Risolvere i problemi di comunicazione all'interno di Teams usando **strumenti di** base.    | Accedi alla pagina del profilo utente per la risoluzione dei problemi di chiamata in Call Analytics. Può vedere solo le informazioni relative allo specifico utente cercato.<sup>3</sup> <br><br> Accedi, monitora e risolvi i problemi di qualità delle chiamate e affidabilità del tenant utilizzando i dati esposti in Call Quality Dashboard (CQD). |
| Amministratore dei dispositivi di Teams              | Gestire i dispositivi configurati per l'uso con il servizio Teams.                    | Consente di gestire la configurazione e gli aggiornamenti dei dispositivi, controllare l'integrità e lo stato delle periferiche connesse, configurare e applicare i profili di configurazione e riavviare i dispositivi.<p>Il ruolo di amministratore dei dispositivi di Teams non fornisce l'accesso ai dati di qualità delle chiamate o all'analisi delle chiamate. Per visualizzare i dati sulla qualità delle chiamate o l'analisi delle chiamate, è necessario disporre del ruolo di amministratore delle comunicazioni di Teams. |

<sup>1</sup> [PowerShell - Modulo Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Modulo di Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Interfaccia</sup> [di amministrazione di Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Per altre informazioni sugli strumenti di amministrazione disponibili per la gestione di Microsoft Teams, vedere [Gestione di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Per altre informazioni su limiti, specifiche e altri requisiti che si applicano a Teams, vedere [Limiti e specifiche per Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Assegnare utenti a ogni ruolo

È possibile assegnare utenti a questi ruoli in Azure AD. Per informazioni su come assegnare ruoli amministrativi a un utente in Azure AD, vedere Assegnare un utente a ruoli [di amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlet disponibili per ogni ruolo

La maggior parte degli strumenti di PowerShell per questi ruoli di amministratore si modificano nel modulo PowerShell di Skype for Business ed è importante notare che alcuni dei cmdlet a cui questi ruoli di amministratore hanno accesso per controllare le impostazioni condivise usate anche per Skype for Business online. Il ruolo di amministratore di Skype for Business ha anche accesso a tutti i cmdlet nel modulo PowerShell di Skype for Business.

Per visualizzare l'elenco completo dei cmdlet attualmente disponibili per un determinato ruolo nel modulo PowerShell di Skype for Business, seguire questa procedura:

1. Assegnare il ruolo a un utente (e assicurarsi che non abbia altri ruoli).
2. Connettersi al modulo PowerShell di Skype for Business:<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. Usare **Get-Module** per identificare il nome della sessione importata, che sarà un nome generato casualmente.<br>
3. Usare **il nome Get-Command -Module**  < *indicato sopra*> identificare tutti i cmdlet disponibili

### <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Assegnare proprietari e membri dei team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

