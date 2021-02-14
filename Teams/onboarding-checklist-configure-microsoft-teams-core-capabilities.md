---
title: Elenco di controllo per l'onboarding - Configurare le funzionalità di base - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Seguire le attività principali e le attività da completare in questo elenco di controllo quando si configura Teams per l'organizzazione.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2987b507b9fa149ad874b1035a753586c05b23d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802306"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurare le funzionalità di base di Microsoft Teams

| No | Attività o attività | Descrizione | Completato? | Informazioni aggiuntive |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Verificare che l'ambiente includa tutti i prerequisiti di Teams | Teams dipende da altre piattaforme per creare una soluzione di collaborazione end-to-end. Collaborare con i team IT per assicurarsi di aver distribuito e configurato correttamente Exchange, SharePoint Online e OneDrive for Business. | | [Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interazione tra Exchange e Microsoft Teams](exchange-teams-interact.md) |
| 2  | Verificare che Teams sia abilitato per il tenant | Teams è attivato per impostazione predefinita per tutte le organizzazioni. Controllare la **pagina &** componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365 per verificare che Teams sia abilitato per l'organizzazione e abilitarlo, se necessario. | | [Configurare Microsoft Teams in Microsoft 365 o Office 365](office-365-set-up.md) |
| 3  | Configurare ruoli e autorizzazioni | Teams supporta due tipi di ruoli: Membro e Proprietario. <br/><br/>Dopo aver aggiunto un membro a un team, un proprietario può anche alzare di livello un membro al ruolo Proprietario. Come procedura consigliata, è consigliabile assegnare almeno due proprietari a ogni team. <br/><br/>Per impostazione predefinita, tutti gli utenti dell'organizzazione che hanno una cassetta postale ospitata in Exchange Online possono creare un team. A un utente che crea un nuovo team viene automaticamente concesso il ruolo Proprietario del team. <br/><br/>Se necessario, è possibile configurare le impostazioni dei gruppi di Microsoft 365 in modo da consentire solo a utenti specifici di creare nuovi team. | | [Assegnare ruoli e autorizzazioni in Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Gruppi di Microsoft 365 e Microsoft Teams](office-365-groups.md) <br/><br/>[Gestire chi può creare gruppi di Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurare le impostazioni di Teams a livello di tenant | Alcune impostazioni di Teams possono essere configurate a livello di tenant. Gli utenti abilitati per Teams ereditano queste impostazioni dalla configurazione del tenant:<ul><li>Generale</li><li>Integrazione di e-mail</li><li>App</li><li>Archiviazione cloud personalizzata</li><li>Chiamate e riunioni</li><li>Messaggistica</li></ul>| | [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md) |
| 5  | FACOLTATIVO: Configurare l'accesso guest | L'accesso guest in Teams viene utilizzato per collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali. L'accesso guest è un'impostazione a livello di tenant in Teams. Per impostazione predefinita l'opzione è disattivata. <br/>Abilitare l'accesso guest e configurare le impostazioni guest a livello di tenant, se l'organizzazione prevede di usare questa caratteristica. | | [Accesso guest in Microsoft Teams](guest-access.md) |
| 6  | FACOLTATIVO: Configurare i criteri di denominazione di Teams | Teams sfrutta i criteri di denominazione per Gruppi di Microsoft 365 quando gli utenti creano o modificano i nomi dei team. <br/><br/>Per impostazione predefinita, non vengono applicate restrizioni di denominazione quando un utente crea un team. <br/><br/>Se è necessario applicare regole per i nomi dei team, configurare i criteri di denominazione dei gruppi di Microsoft 365 applicabili all'organizzazione. È possibile impostare prefissi e suffissi obbligatori e specificare le parole bloccate. | | [Pianificare i gruppi di Microsoft 365 durante la creazione di team in Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Criteri di denominazione dei gruppi di Microsoft 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurare Exchange per il dominio SMTP di Teams | Teams usa Exchange Online per inviare notifiche ai membri del team usando il dominio SMTP (email.teams.microsoft.com) quando vengono aggiunti o rimossi. <br/><br/>Aggiungere il dominio SMTP all'elenco dei domini accettati nell'infrastruttura di Exchange. | | [Creare elenchi di mittenti attendibili in Exchange](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurare e gestire l'accesso degli utenti a Teams | Sebbene sia altamente consigliabile abilitare tutti gli utenti per Teams, è possibile consentire o disabilitare l'accesso a Teams per singoli utenti assegnando o rimuovendo la licenza del prodotto Teams. | | [Gestire l'accesso degli utenti a Microsoft Teams](user-access.md) |
| 9  | Assegnare licenze agli utenti | Assegnare licenze agli utenti per funzionalità come Audioconferenza, Sistema telefonico e Piani per chiamate | | [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Facoltativo: Usare PowerShell per amministrare Teams | È possibile usare i cmdlet di PowerShell invece dell'interfaccia di amministrazione di Microsoft 365 per amministrare e gestire le impostazioni di Teams. | | [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
