---
title: Elenco di controllo onboarding per la configurazione delle funzionalità principali di Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Quando si configurano teams, seguire le attività e le operazioni principali in questo elenco di controllo.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6f0f3482258af46b049f22af73e0efe4bc463a6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573344"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurare le funzionalità di base di Microsoft Teams

| No | Attività o attività | Descrizione | Completato? | Altre informazioni |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Verificare che l'ambiente includa tutti i prerequisiti di Teams | Teams dipende da altre piattaforme per creare una soluzione di collaborazione end-to-end. Collaborare con i team IT per verificare che sia stata distribuita e configurata correttamente Exchange, SharePoint Online e OneDrive for business. | | [Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md) |
| 2  | Verificare che i team siano abilitati per il tenant | Teams è attivato per impostazione predefinita per tutte le organizzazioni. Selezionare la pagina **servizi & componenti** aggiuntivi nell'interfaccia di amministrazione di Microsoft 365 per verificare che il team sia abilitato per il tenant e abilitarlo, se necessario. | | [Configurare Microsoft teams nell'organizzazione di Office 365](office-365-set-up.md) |
| 3  | Configurare ruoli e autorizzazioni | I team supportano due tipi di ruoli: Member e Owner. <br/><br/>Dopo aver aggiunto un membro a un team, un proprietario può anche promuovere un membro per il ruolo del proprietario. Come procedura consigliata, ti consigliamo di avere almeno due proprietari assegnati a ogni team. <br/><br/>Per impostazione predefinita, tutti gli utenti dell'organizzazione che hanno una cassetta postale ospitata in Exchange Online possono creare un team. Un utente che crea un nuovo team viene automaticamente concesso il ruolo di proprietario per il team. <br/><br/>Se necessario, è possibile configurare le impostazioni di gruppo di Office 365 solo per consentire agli utenti specifici di creare nuovi team. | | [Assegnare ruoli e autorizzazioni in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Gruppi di Office 365 e Microsoft Teams](office-365-groups.md) <br/><br/>[Gestire chi può creare gruppi di Office 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurare le impostazioni di team a livello di tenant | È possibile configurare alcune impostazioni del team a livello di tenant. Gli utenti abilitati per i team ereditano queste impostazioni dalla configurazione del tenant:<ul><li>Generale</li><li>Integrazione della posta elettronica</li><li>Applicazioni</li><li>Archiviazione cloud personalizzata</li><li>Chiamate e riunioni</li><li>Messaggistica</li></ul>| | [Gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md) |
| 5  | FACOLTATIVO: configurare l'accesso Guest | Si usa l'accesso guest in teams per collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali. Guest Access è un'impostazione a livello di tenant in teams. È disattivata per impostazione predefinita. <br/>Abilitare l'accesso guest e configurare le impostazioni Guest a livello di tenant, se l'organizzazione prevede di usare tale funzionalità. | | [Accesso guest in Microsoft Teams](guest-access.md) |
| 6  | FACOLTATIVO: configurare i criteri di denominazione dei team | Teams sfrutta i criteri di denominazione per i gruppi di Office 365 quando gli utenti creano o modificano i nomi del team. <br/><br/>Per impostazione predefinita, non vengono applicate restrizioni di denominazione quando un utente crea un team. <br/><br/>Se è necessario applicare regole per i nomi dei team, configurare i criteri di denominazione per i gruppi di Office 365 applicabili all'organizzazione. Puoi impostare i prefissi e i suffissi obbligatori e specificare le parole bloccate. | | [Pianificare i gruppi di Office 365 durante la creazione di team in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Criteri di denominazione dei gruppi di Office 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurare Exchange per il dominio SMTP Teams | Teams USA Exchange Online per inviare notifiche ai membri del team usando il dominio SMTP, email.teams.microsoft.com, quando è stato aggiunto o rimosso. <br/><br/>Assicurati di aggiungere il dominio SMTP all'elenco dei domini accettati nell'infrastruttura di Exchange. | | [Aggiungere il dominio SMTP di Microsoft teams come dominio accettato in Exchange Online](smtp-accepted-domain.md) |
| 8  | Configurare e gestire l'accesso degli utenti ai team | Anche se ti consigliamo vivamente di abilitare tutti gli utenti per i team, puoi consentire o impedire l'accesso ai team per ogni singolo utente assegnando o rimuovendo la licenza del prodotto teams. | | [Gestire l'accesso degli utenti a Microsoft Teams](user-access.md) |
| 9  | Assegnare licenze agli utenti | Assegnare licenze agli utenti per funzionalità come l'audioconferenza, il sistema telefonico e i piani per le chiamate | | [Assegnare le licenze Skyper for Business e Microsoft Teams](assign-teams-licenses.md)|
| 10 | Facoltativo: usare PowerShell per amministrare Teams | È possibile usare i cmdlet di PowerShell anziché l'interfaccia di amministrazione di Microsoft 365 per amministrare e gestire le impostazioni dei team. | | [PowerShell per Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
