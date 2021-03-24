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
description: Informazioni su come usare i ruoli amministrativi per designare amministratori che hanno bisogno di diversi livelli di accesso per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 201cc1d73166825d729b4581d183ea58cfda64af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093736"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usare i ruoli di amministratore di Microsoft Teams per gestire Teams.

Usando Azure Active Directory (Azure AD), è possibile designare amministratori che hanno bisogno di diversi livelli di accesso per la gestione di Microsoft Teams. Gli amministratori possono gestire l'intero carico di lavoro di Teams oppure avere autorizzazioni delegate per la risoluzione dei problemi di qualità delle chiamate o per la gestione delle esigenze di telefonia dell'organizzazione.

## <a name="teams-roles-and-capabilities"></a>Ruoli e funzionalità di Teams

Sono disponibili diversi ruoli di amministratore di Teams: amministratore del servizio Teams, amministratore delle comunicazioni di Teams, specialista del supporto per le comunicazioni di Teams, tecnico del supporto per le comunicazioni di Teams e amministratore dei dispositivi di Teams. Esaminare la tabella seguente per comprendere le operazioni che ogni ruolo può eseguire e gli strumenti che l'amministratore può usare nell'interfaccia di amministrazione di Microsoft Teams e in PowerShell.

Per seguire questa procedura, è necessario essere un amministratore. Le istruzioni per ottenere le autorizzazioni sono disponibili in questo articolo.

<!-- add Global admin role? -->

| Ruolo                                    | È possibile eseguire queste attività                                                           | Può accedere agli strumenti seguenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amministratore del servizio Teams             | Gestire il servizio Teams e gestire e creare gruppi di Microsoft 365.        | Tutti gli elementi dell'interfaccia di amministrazione di Microsoft Teams e i controlli di PowerShell associati, tra cui:<ul><li> Gestire le riunioni, inclusi i criteri, le configurazioni e i ponti delle conferenze. <sup>1,2</sup></li><li>Gestire la voce, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup></li><li>Gestire la messaggistica, inclusi i criteri di messaggistica. <sup>1,2</sup></li><li>Gestire tutte le impostazioni a livello di organizzazione, tra cui la federazione, l'aggiornamento dei team e le impostazioni dei client di Teams. <sup>1,2</sup></li><li>Gestire i team dell'organizzazione e le impostazioni associate, tra cui l'appartenenza (gestione dei gruppi supportata tramite PowerShell, gestione del team nell'interfaccia di amministrazione di Teams). <sup>1,2</sup></li><li>Gestire i dispositivi certificati di Teams e configurare e assegnare criteri di configurazione. <sup>1</sup></li><li>Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate degli utenti con set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> </li><li>Accedere a tutti i report nell'interfaccia di amministrazione di Microsoft Teams</li><li> Accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti che sono stati influenzati dalla scarsa qualità delle chiamate. Creare nuovi report sulla qualità delle chiamate, aggiornare e rimuovere i report sulla qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio CQD.</li><li> [Pubblicare app nel catalogo app tenant nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)</li></ul> |
| Amministratore comunicazioni Teams      | Gestire le funzionalità per chiamate e riunioni all'interno del servizio Teams.               | Gestire le riunioni, inclusi i criteri, le configurazioni e i ponti delle conferenze. <sup>1,2</sup><br><br> Gestire la voce, inclusi i criteri di chiamata e l'inventario e l'assegnazione dei numeri di telefono. <sup>1</sup><br><br> Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate degli utenti usando il set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> <br><br> Accedere, monitorare e risolvere i problemi di qualità e affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti che sono influenzati dalla scarsa qualità delle chiamate. Creare nuovi report sulla qualità delle chiamate, aggiornare e rimuovere i report sulla qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio CQD.|
| Tecnico supporto comunicazioni Teams   | Risolvere i problemi di comunicazione all'interno di Teams usando **strumenti** avanzati. | Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate degli utenti con set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> <br><br> Accedere, monitorare e risolvere i problemi di qualità e affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti che sono influenzati dalla scarsa qualità delle chiamate. |
| Specialista del supporto tecnico di Teams Communications | Risolvere i problemi di comunicazione all'interno di Teams usando **gli strumenti di** base.    | Accedere alla pagina del profilo utente per la risoluzione dei problemi relativi alle chiamate in Call Analytics. Può visualizzare solo le informazioni utente per l'utente specifico cercato. <sup>2</sup> <br><br> Accedere, monitorare e risolvere i problemi di qualità e affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD). |
| Amministratore dei dispositivi di Teams              | Gestire i dispositivi configurati per l'uso con il servizio Teams.                    | Gestire la configurazione e gli aggiornamenti dei dispositivi, esaminare l'integrità e lo stato delle periferiche connesse, configurare e applicare profili di configurazione e riavviare i dispositivi.<p>Il ruolo di amministratore dei dispositivi di Teams non fornisce l'accesso ai dati sulla qualità delle chiamate o all'analisi delle chiamate. Per visualizzare i dati sulla qualità delle chiamate o l'analisi delle chiamate, è necessario avere il ruolo di amministratore di Teams Communications. |

<sup>1</sup> [PowerShell - Modulo Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) (la versione pubblica 1.1.6 o successiva è integrata con Skype for Business Online Connector).<br>
<sup>2 Interfaccia</sup> [di amministrazione di Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md)
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Per altre informazioni sugli strumenti di amministrazione disponibili per la gestione di Microsoft Teams, vedere [Gestione di Microsoft Teams.](./manage-teams-skypeforbusiness-admin-center.md)

Per altre informazioni sui limiti, le specifiche e altri requisiti applicabili a Teams, vedere [Limiti e specifiche per Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Assegnare utenti a ogni ruolo

È possibile assegnare utenti a questi ruoli in Azure AD. Per informazioni su come assegnare ruoli amministrativi a un utente in Azure AD, vedere Assegnare un utente ai ruoli [di amministratore in Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlet disponibili per ogni ruolo

La maggior parte degli strumenti di PowerShell per questi ruoli di amministratore è disponibile nel modulo di PowerShell di Teams ed è importante tenere presente che alcuni dei cmdlet a cui questi ruoli di amministratore hanno accesso per controllare le impostazioni condivise usate anche per Skype for Business Online. 

Per visualizzare l'elenco completo dei cmdlet:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)
- [Assegnare proprietari e membri del team in Microsoft Teams](./assign-roles-permissions.md)