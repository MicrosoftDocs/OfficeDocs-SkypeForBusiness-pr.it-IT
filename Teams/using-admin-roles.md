---
title: Usare i ruoli di amministratore di Microsoft Teams per gestire Teams.
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
ms.openlocfilehash: feccaa2662189016c721a2bf11629598d90f0501
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558395"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usare i ruoli di amministratore di Microsoft Teams per gestire Teams.

Con Azure Active Directory (Azure AD), è possibile designare amministratori che necessitano di livelli di accesso diversi per la gestione di Microsoft Teams. Gli amministratori possono gestire l'intero carico di lavoro di Teams oppure avere autorizzazioni delegate per risolvere i problemi di qualità delle chiamate o gestire le esigenze di telefonia dell'organizzazione.

## <a name="teams-roles-and-capabilities"></a>Ruoli e funzionalità di Teams

Sono disponibili diversi ruoli di amministratore di Teams: Amministratore dei servizi di Teams, Amministratore delle comunicazioni di Teams, Esperto del supporto per le comunicazioni di Teams, Tecnico del supporto per le comunicazioni di Teams e Amministratore dei dispositivi di Teams. Esaminare la tabella seguente per comprendere le operazioni che ogni ruolo può eseguire e gli strumenti che l'amministratore può usare nell'interfaccia di amministrazione di Microsoft Teams e in PowerShell.

Per seguire la procedura, è necessario essere un amministratore. Le istruzioni per ottenere le autorizzazioni sono riportate in questo articolo.

<!-- add Global admin role? -->

| Ruolo                                    | È possibile eseguire queste attività                                                           | Accesso agli strumenti seguenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amministratore del servizio Teams             | Gestire il servizio Teams e gestire e creare gruppi di Microsoft 365.        | Tutto nell'interfaccia di amministrazione di Microsoft Teams e i controlli powerShell associati, tra cui:<ul><li> Gestire le riunioni, inclusi i criteri, le configurazioni e i bridge di conferenza. <sup>1,3</sup></li><li>Gestisci i comandi vocali, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup></li><li>Gestire la messaggistica, inclusi i criteri di messaggistica. <sup>1,3</sup></li><li>Gestire tutte le impostazioni a livello di organizzazione, incluse le impostazioni di federazione, aggiornamento dei team e client dei team. <sup>1,3</sup></li><li>Gestisci i team nell'organizzazione e le impostazioni associate, compresa l'appartenenza (gestione dei gruppi supportata tramite PowerShell, gestione team nell'interfaccia di amministrazione di Teams). <sup>2,3</sup></li><li>Gestire i dispositivi certificati da Teams e configurare e assegnare criteri di configurazione. <sup>2</sup></li><li>Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate dell'utente utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> </li><li>Accedere a tutti i report nell'interfaccia di amministrazione di Microsoft Teams</li><li> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti a cui la qualità delle chiamate è scarsa. Crea nuovi rapporti sulla qualità delle chiamate, aggiorna e rimuovi i rapporti di qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati di creazione di CQD.</li><li> [Pubblicare app nel catalogo app tenant nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)</li></ul> |
| Amministratore comunicazioni Teams      | Gestire le funzionalità di chiamata e riunione all'interno del servizio Teams.               | Gestire le riunioni, inclusi i criteri, le configurazioni e i bridge di conferenza. <sup>1,3</sup><br><br> Gestisci i comandi vocali, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup><br><br> Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> <br><br> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti nel Call Quality Dashboard (CQD) fino agli utenti che sono intasati da una bassa qualità delle chiamate. Crea nuovi rapporti sulla qualità delle chiamate, aggiorna e rimuovi i rapporti di qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati di creazione di CQD.|
| Tecnico supporto comunicazioni Teams   | Risolvere i problemi di comunicazione all'interno di Teams usando **strumenti** avanzati. | Visualizza la pagina del profilo utente e risolvi i problemi di qualità delle chiamate dell'utente utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>3</sup> <br><br> Accedi, monitora e risolvi i problemi di qualità e affidabilità delle chiamate del tenant utilizzando i dati esposti nel Call Quality Dashboard (CQD) fino agli utenti che sono intasati da una bassa qualità delle chiamate. |
| Teams Communications Support Specialist | Risolvere i problemi di comunicazione all'interno di Teams usando **strumenti di** base.    | Accedi alla pagina del profilo utente per la risoluzione dei problemi di chiamata in Call Analytics. Può vedere solo le informazioni relative allo specifico utente cercato.<sup>3</sup> <br><br> Accedi, monitora e risolvi la qualità delle chiamate e l'affidabilità del tenant utilizzando i dati esposti in Call Quality Dashboard (CQD). |
| Amministratore dei dispositivi di Teams              | Gestire i dispositivi configurati per l'uso con il servizio Teams.                    | Consente di gestire la configurazione e gli aggiornamenti dei dispositivi, controllare l'integrità e lo stato delle periferiche connesse, configurare e applicare i profili di configurazione e riavviare i dispositivi.<p>Il ruolo di amministratore dei dispositivi di Teams non fornisce l'accesso ai dati di qualità delle chiamate o all'analisi delle chiamate. Per visualizzare i dati sulla qualità delle chiamate o l'analisi delle chiamate, è necessario avere il ruolo di amministratore di Teams Communications. |

<sup>1</sup> [PowerShell - Modulo Skype for Business](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Modulo di Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Interfaccia</sup> [di amministrazione di Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Per altre informazioni sugli strumenti di amministrazione disponibili per la gestione di Microsoft Teams, vedere [Gestione di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Per altre informazioni sui limiti, le specifiche e altri requisiti che si applicano a Teams, vedere [Limiti e specifiche per Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Assegnare utenti a ogni ruolo

È possibile assegnare utenti a questi ruoli in Azure AD. Per informazioni su come assegnare ruoli amministrativi a un utente in Azure AD, vedere Assegnare un utente a ruoli di [amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlet disponibili per ogni ruolo

La maggior parte degli strumenti di PowerShell per questi ruoli di amministratore si vivere nel modulo PowerShell di Teams, ed è importante notare che alcuni dei cmdlet a cui questi ruoli di amministratore hanno accesso per controllare le impostazioni condivise usate anche per Skype for Business online. 

Per visualizzare l'elenco completo dei cmdlet:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Assegnare proprietari e membri del team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)
