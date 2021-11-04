---
title: Elenco di controllo per l'onboarding - Configurare le funzionalità di base - Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Seguire le attività e le attività principali di questo elenco di controllo quando si configurano Teams per l'organizzazione.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e376033c0e770dcef5bfa454b365d168ed922c5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767244"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurare le Microsoft Teams principali

| No | Attività o attività | Descrizione | Completato? | Informazioni aggiuntive |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Verificare che l'ambiente includa tutti Teams prerequisiti | Teams dipende da altre piattaforme per creare una soluzione di collaborazione end-to-end. Collaborare con i team IT per assicurarsi di aver distribuito e configurato correttamente Exchange, SharePoint Online e OneDrive for Business. | | [Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md) |
| 2  | Verificare che Teams sia abilitato per il tenant | Teams è attivato per impostazione predefinita per tutte le organizzazioni. Controllare la **pagina &** componenti aggiuntivi nel interfaccia di amministrazione di Microsoft 365 per verificare che la Teams sia abilitata per l'organizzazione e abilitarla, se necessario. | | [Configurare Microsoft Teams in Microsoft 365 o Office 365](office-365-set-up.md) |
| 3  | Configurare ruoli e autorizzazioni | Teams due tipi di ruoli: Membro e Proprietario. <br/><br/>Dopo aver aggiunto un membro a un team, un proprietario può anche alzare di livello un membro al ruolo di proprietario. Come procedura consigliata, è consigliabile assegnare almeno due proprietari a ogni team. <br/><br/>Per impostazione predefinita, tutti gli utenti dell'organizzazione che hanno una cassetta postale ospitata Exchange Online creare un team. A un utente che crea un nuovo team viene concesso automaticamente il ruolo di proprietario per il team. <br/><br/>Se necessario, è possibile configurare le impostazioni Microsoft 365 gruppo per consentire solo a utenti specifici di creare nuovi team. | | [Assegnare ruoli e autorizzazioni in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365 gruppi e Microsoft Teams](office-365-groups.md) <br/><br/>[Gestire gli utenti che possono creare Microsoft 365 gruppi](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurare le impostazioni di Teams tenant | È possibile configurare alcune impostazioni Teams a livello di tenant. Gli utenti abilitati per Teams ereditano queste impostazioni dalla configurazione tenant:<ul><li>Generale</li><li>Integrazione di e-mail</li><li>App</li><li>Spazio di archiviazione cloud personalizzato</li><li>Chiamate e riunioni</li><li>Messaggistica</li></ul>| | [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md) |
| 5  | FACOLTATIVO: Configurare l'accesso guest | È possibile usare l'accesso guest in Teams collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali. L'accesso guest è un'impostazione a livello di tenant in Teams. Per impostazione predefinita l'opzione è disattivata. <br/>Abilitare l'accesso guest e configurare le impostazioni guest a livello di tenant, se l'organizzazione prevede di usare questa caratteristica. | | [Accesso guest in Microsoft Teams](guest-access.md) |
| 6  | FACOLTATIVO: Configurare i Teams di denominazione | Teams i criteri di denominazione per Microsoft 365 gruppi quando gli utenti creano o modificano i nomi dei team. <br/><br/>Per impostazione predefinita, non vengono applicate restrizioni di denominazione quando un utente crea un team. <br/><br/>Se è necessario applicare regole per i nomi dei team, configurare Microsoft 365 criteri di denominazione dei gruppi che si applicano all'organizzazione. È possibile impostare prefissi e suffissi obbligatori e specificare parole bloccate. | | [Pianificare Microsoft 365 gruppi quando si creano team in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365 Criteri di denominazione dei gruppi](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurare Exchange per il Teams SMTP | Teams usa Exchange Online per inviare notifiche ai membri del team usando il dominio SMTP, email.teams.microsoft.com, quando sono stati aggiunti o rimossi. <br/><br/>Assicurarsi di aggiungere questo dominio SMTP all'elenco dei domini accettati nell'Exchange aziendale. | | [Creare elenchi di mittenti attendibili in Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurare e gestire l'accesso degli utenti Teams | Anche se è consigliabile abilitare tutti gli utenti per Teams, è possibile consentire o disabilitare l'accesso a Teams in base all'utente assegnando o rimuovendo la licenza Teams prodotto. | | [Gestire l'accesso degli utenti Microsoft Teams](user-access.md) |
| 9  | Assegnare licenze agli utenti | Assegnare licenze agli utenti per funzionalità come audioconferenze, Sistema telefonico e piani per chiamate | | [Assegnare Microsoft Teams licenze per i componenti aggiuntivi](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Facoltativo: usare PowerShell per amministrare Teams | È possibile usare i cmdlet di PowerShell anziché i interfaccia di amministrazione di Microsoft 365 per amministrare e gestire Teams impostazioni. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |