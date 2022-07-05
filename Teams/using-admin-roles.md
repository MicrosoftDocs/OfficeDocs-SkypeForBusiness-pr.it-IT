---
title: Usare i ruoli di amministratore di Microsoft Teams per gestire Teams.
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni su come usare i ruoli amministrativi per designare gli amministratori che devono avere livelli di accesso diversi per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615452"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usare i ruoli di amministratore di Microsoft Teams per gestire Teams.

Con Azure Active Directory (Azure AD), è possibile designare gli amministratori che necessitano di livelli di accesso diversi per la gestione di Microsoft Teams. Gli amministratori possono gestire l'intero carico di lavoro di Teams oppure avere autorizzazioni delegate per risolvere i problemi di qualità delle chiamate o gestire le esigenze di telefonia dell'organizzazione.

## <a name="teams-roles-and-capabilities"></a>Ruoli e funzionalità di Teams

Sono disponibili diversi ruoli di amministratore di Teams: amministratore di Teams, amministratore delle comunicazioni di Teams, specialista del supporto per le comunicazioni di Teams, tecnico del supporto per le comunicazioni di Teams e amministratore del dispositivo di Teams. Esaminare la tabella seguente per comprendere cosa può fare ogni ruolo e quali strumenti può usare l'amministratore nell'interfaccia di amministrazione di Microsoft Teams e in PowerShell.

> [!NOTE]
> Gli amministratori di Skype for Business Online possono gestire **Teams** e i criteri delle app di **Skype for Business Online** tramite PowerShell.

Per seguire questa procedura, è necessario essere un amministratore. Le istruzioni per ottenere le autorizzazioni sono disponibili in questo articolo.

<!-- add Global admin role? -->

| Ruolo                                    | Può eseguire queste attività                                                           | Accesso agli strumenti seguenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Amministratore di Teams             | Gestire il servizio Teams e gestire e creare Gruppi di Microsoft 365.        | Tutto nell'interfaccia di amministrazione di Microsoft Teams e nei controlli di PowerShell associati, tra cui:<ul><li> Consente di gestire riunioni, inclusi criteri di riunione, configurazioni e bridge delle conferenze. <sup>1,2</sup></li><li>Gestisci i comandi vocali, inclusi i criteri per le chiamate e l'inventario e l'assegnazione dei numeri di telefono. <sup>1,3</sup></li><li>Gestire la messaggistica, inclusi i criteri di messaggistica. <sup>1,2</sup></li><li>Gestire tutte le impostazioni a livello di organizzazione, incluse la federazione, l'aggiornamento dei team e le impostazioni del client dei team. <sup>1,2</sup></li><li>Gestire i team nell'organizzazione e le impostazioni associate, inclusa l'appartenenza (gestione dei gruppi supportata tramite PowerShell, gestione del team nell'interfaccia di amministrazione di Teams). <sup>1,2</sup></li><li>Gestire i dispositivi certificati per Teams e configurare e assegnare criteri di configurazione. <sup>1</sup></li><li>Visualizza la pagina del profilo utente e risolvi i problemi relativi alla qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> </li><li>Accedere a tutti i report nell'interfaccia di amministrazione di Microsoft Teams</li><li> Accesso, monitoraggio e risoluzione dei problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti interessati dalla scarsa qualità delle chiamate. Creare nuovi rapporti sulla qualità delle chiamate, aggiornare e rimuovere i rapporti sulla qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio di Call Quality Dashboard.</li><li> [Pubblicare app nel catalogo app tenant nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)</li></ul> |
| Amministratore comunicazioni Teams      | Gestire le funzionalità di chiamata e riunione all'interno del servizio Teams.               | Consente di gestire riunioni, inclusi criteri di riunione, configurazioni e bridge delle conferenze. <sup>1,2</sup><br><br> Gestisci i comandi vocali, inclusi i criteri per le chiamate e l'inventario e l'assegnazione dei numeri di telefono. <sup>1,3</sup><br><br> Visualizza la pagina del profilo utente e risolvi i problemi relativi alla qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> <br><br> Accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti interessati dalla scarsa qualità delle chiamate. Creare nuovi rapporti sulla qualità delle chiamate, aggiornare e rimuovere i rapporti sulla qualità delle chiamate in base alle esigenze. Caricare e aggiornare i dati dell'edificio di Call Quality Dashboard.|
| Tecnico supporto comunicazioni Teams   | Risolvere i problemi di comunicazione all'interno di Teams usando strumenti **avanzati** . | Visualizza la pagina del profilo utente e risolvi i problemi relativi alla qualità delle chiamate degli utenti utilizzando il set di strumenti avanzati per la risoluzione dei problemi. <sup>2</sup> <br><br> Accedere, monitorare e risolvere i problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD) fino agli utenti interessati dalla scarsa qualità delle chiamate. |
| Specialista del supporto tecnico per le comunicazioni di Teams | Risolvere i problemi di comunicazione all'interno di Teams usando gli strumenti **di base** .    | Accedi alla pagina del profilo utente per risolvere i problemi relativi alle chiamate in Call Analytics. Può visualizzare solo le informazioni utente per l'utente specifico cercato. <sup>2</sup> <br><br> Accesso, monitoraggio e risoluzione dei problemi relativi alla qualità e all'affidabilità delle chiamate del tenant usando i dati esposti in Call Quality Dashboard (CQD). |
| Amministratore del dispositivo di Teams              | Gestire i dispositivi configurati per l'uso con il servizio Teams.                    | Gestisci la configurazione e gli aggiornamenti dei dispositivi, verifica l'integrità e lo stato delle periferiche connesse, configura e applica i profili di configurazione e riavvia i dispositivi.<p>Il ruolo Amministratore dispositivo di Teams non consente l'accesso ai dati di qualità delle chiamate o all'analisi delle chiamate. Per visualizzare i dati relativi alla qualità delle chiamate o l'analisi delle chiamate, è necessario avere il ruolo di amministratore delle comunicazioni di Teams. |

<sup>1</sup> [PowerShell - Modulo di Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) (la versione pubblica 1.1.6 o successiva è integrata con Skype for Business Online Connector).<br>
<sup>2</sup> [L'interfaccia di amministrazione di](./manage-teams-skypeforbusiness-admin-center.md)
 Microsoft Teams<sup>3</sup> L'account amministratore di Teams deve avere una licenza di Teams valida.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Per altre informazioni sugli strumenti di amministrazione disponibili per la gestione di Microsoft Teams, vedere [Gestione di Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Per altre informazioni su limiti, specifiche e altri requisiti che si applicano a Teams, vedere [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Assegnare utenti a ogni ruolo

È possibile assegnare utenti a questi ruoli in Azure AD. Per informazioni su come assegnare ruoli amministrativi a un utente in Azure AD, vedere [Assegnare un utente a ruoli di amministratore in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlet disponibili per ogni ruolo

La maggior parte degli strumenti di PowerShell per questi ruoli di amministratore risiede nel modulo di PowerShell di Teams ed è importante notare che alcuni dei cmdlet che questi ruoli di amministratore hanno accesso per controllare le impostazioni condivise usate anche per Skype for Business Online. 

Per visualizzare l'elenco completo dei cmdlet:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Articoli correlati

- [Panoramica di PowerShell di Microsoft Teams](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Assegnare proprietari e membri del team in Microsoft Teams](./assign-roles-permissions.md)
