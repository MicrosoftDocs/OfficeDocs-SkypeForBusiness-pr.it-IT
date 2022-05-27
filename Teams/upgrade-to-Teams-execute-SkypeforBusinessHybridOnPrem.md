---
title: Aggiornare Skype for Business locale a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione locale Skype for Business.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681367"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Eseguire l'aggiornamento da Skype for Business locale a Teams

![Diagramma percorso di aggiornamento, enfatizzando la distribuzione e l'implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)
- [Coesistenza e interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Scelta del percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Se è stato distribuito Skype for Business Server o Microsoft Lync Server locale e l'organizzazione vuole eseguire l'aggiornamento a Teams, seguire le indicazioni in questo articolo. È necessario configurare la connettività ibrida con l'organizzazione Microsoft 365 come descritto in [Pianificare la connettività ibrida tra Skype for Business Server e Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Prima di iniziare, vedere anche [Considerazioni importanti per le organizzazioni con Skype for Business Server locale](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) più avanti in questo articolo.

> [!IMPORTANT]
> Skype for Business Online è stato ritirato il 31 luglio 2021. Per massimizzare la realizzazione dei vantaggi e garantire che la tua organizzazione abbia il tempo giusto per implementare il tuo aggiornamento, ti invitiamo a iniziare il tuo viaggio verso Microsoft Teams oggi stesso. Ricorda che un aggiornamento riuscito allinea la preparazione tecnica e dell'utente, quindi assicurati di sfruttare queste indicazioni mentre ti sposti nel tuo percorso verso Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Passaggio 1: Configurare la connettività ibrida

Il prerequisito fondamentale per aggiornare gli utenti locali a Teams è configurare la connettività ibrida per la distribuzione locale Skype for Business Server.

Per iniziare, leggere [Pianificare la connettività ibrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) e quindi seguire le attività descritte in [Configurare la connettività ibrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Passaggio 2: Impostare la modalità di coesistenza transitoria (facoltativo)

La coesistenza e l'interoperabilità tra client e utenti Skype for Business e Teams sono definite dalle [modalità di coesistenza](migration-interop-guidance-for-teams-with-skype.md). Le organizzazioni ibride sono per impostazione predefinita in modalità Isole. La modalità Isole consente agli utenti di usare client Teams e Skype for Business affiancati. Facoltativamente, le organizzazioni possono usare altre modalità di coesistenza per offrire agli utenti finali un'esperienza prevedibile durante la transizione da Skype for Business a Teams. Indipendentemente dalla modalità usata da un'organizzazione per gli utenti locali, quando questi vengono spostati dall'ambiente locale al cloud, diventano TeamsOnly (e non possono avere altre modalità).  Se gli utenti usano ancora Skype for Business Server, è possibile assegnarsi una qualsiasi modalità diversa da TeamsOnly. Se necessario, TeamsOnly gli utenti possono essere spostati di nuovo in locale, con conseguente ricezione dei criteri globali del tenant di TeamsUpgradePolicy.

Quando un utente usa una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono indirizzate al client Skype for Business dell'utente. Per evitare confusione con l'utente finale e garantire la corretta funzionalità di routing, chiamata e chat nel client Teams sia disabilitata *per un utente a cui è assegnata una delle modalità Skype for Business*. La pianificazione delle riunioni in Teams viene disabilitata quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e *abilitati* quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere [Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) e [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md).

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Passaggio 3: Spostare gli utenti da Skype for Business locale a Solo Teams

Microsoft ha recentemente semplificato il processo per spostare gli utenti in TeamsOnly. Questo processo è ora un unico passaggio, indipendentemente dalla versione di Skype for Business Server o Lync Server 2013 in uso. Per altre informazioni, vedere [Spostare gli utenti tra la distribuzione locale e il cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [Spostare gli utenti dalla distribuzione locale a Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Passaggio 4: Completare la migrazione al cloud disabilitando la distribuzione ibrida e disattivando Skype for Business

Dopo aver spostato tutti gli utenti dall'ambiente locale al cloud, è possibile rimuovere la distribuzione di Skype for Business locale. Per altre informazioni, vedere [Rimuovere l'ambiente di Skype for Business locale](/skypeforbusiness/hybrid/decommission-on-prem-overview).

## <a name="phone-system-and-pstn-connectivity-options"></a>Opzioni di connettività Sistema telefonico e PSTN

Sistema telefonico con Teams è supportata dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business.

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due possibili scenari quando si passa da Skype for Business locale alla modalità TeamsOnly:

- Un utente in Skype for Business locale con VoIP aziendale, che passa online e usa un piano per le chiamate Microsoft. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) l'assegnazione di un nuovo numero di abbonato dalle aree geografiche disponibili.  Per ulteriori informazioni, vedi [Da Skype for Business Server locale, con VoIP aziendale, a Piano per chiamate Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utente in Skype for Business locale con VoIP aziendale, che si sposterà online e manterrà la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. Per altre informazioni, vedere [Da Skype for Business Server locale, con VoIP aziendale, a Routing diretto](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerazioni importanti per le organizzazioni con Skype for Business Server locale

- La configurazione di Skype for Business ibrida è un prerequisito per la migrazione alla modalità TeamsOnly. Gli utenti di Skype for Business Server locali possono usare Teams in modalità Isole senza ibridi. Tuttavia, la transizione alla modalità TeamsOnly non può essere eseguita senza spostare l'utente nel cloud tramite [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), per il quale è necessaria la connettività ibrida. Per altre informazioni, vedere [Configurare la connettività ibrida](/skypeforbusiness/hybrid/configure-hybrid-connectivity). Il prossimo ritiro di Skype for Business Online non cambierà questo requisito. Per passare da Skype for Business Server a Teams, le organizzazioni devono comunque configurare e configurare la distribuzione ibrida usando lo stesso set di strumenti, *esattamente come prima del ritiro*.

- Per spostare un utente locale nel cloud, usare `Move-CsUser` gli strumenti di amministrazione locale. Non è più necessario specificare il `-MoveToTeams` passaggio per spostare gli utenti direttamente da locale a TeamsOnly. Agli utenti viene assegnata automaticamente la modalità TeamsOnly e le riunioni locali vengono convertite automaticamente in riunioni Teams, indipendentemente dal fatto che l'opzione `-MoveToTeams` sia specificata.

- Se l'organizzazione ha Skype for Business Server e la connettività ibrida non è stata configurata, ma si vuole comunque usare Teams, per amministrare Teams funzionalità è necessario usare un account amministrativo con dominio .onmicrosoft.com. Senza connettività ibrida, gli strumenti di amministrazione non riconosceranno i domini locali.

- Teams gli utenti che hanno un account di Skype for Business locale (ovvero non sono ancora stati spostati nel cloud tramite Move-CsUser) non possono interagire con Skype for Business utenti, né possono eseguire la federazione con utenti esterni. Questa funzionalità è disponibile solo quando gli utenti vengono spostati nel cloud e sono solo utenti di Teams.

- Se si hanno utenti con account di Skype for Business in locale o se si ha ancora un record DNS di lyncdiscover per una distribuzione locale, non è possibile assegnare la modalità TeamsOnly a livello di tenant. È necessario spostare tutti gli utenti con account di Skype for Business locali nel cloud usando `Move-CsUser`. Seguire quindi i passaggi descritti in [Disabilitare la migrazione ibrida al cloud](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid), che include la rimozione delle voci DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`non funziona a livello di tenant se viene rilevato un record DNS di lyncdiscover che punta a una posizione diversa da Office 365.

- È necessario assicurarsi che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi di Skype for Business corretti. Questi attributi sono tutti prefissi con "msRTCSIP-". Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in Teams non saranno in grado di gestirli. Ad esempio, non sarà possibile assegnare criteri di Teams agli utenti locali, a meno che non si stia sincronizzando correttamente questi attributi. Per altre informazioni, vedere [Configurare Azure AD Connessione per Teams e Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Per creare un nuovo TeamsOnly in un'organizzazione ibrida, *è necessario prima abilitare l'utente in Skype for Business Server locale*, quindi spostare l'utente dall'ambiente locale al cloud tramite Move-CsUser.  La creazione dell'utente in locale assicura innanzitutto che tutti gli altri utenti locali rimanenti Skype for Business possano essere indirizzati all'utente appena creato. Una volta spostati *tutti* gli utenti online, non è più necessario abilitare prima gli utenti in locale.

- Se si vogliono visualizzare le notifiche nel client Skype for Business per gli utenti locali, è necessario usare TeamsUpgradePolicy nel set di strumenti locale. Solo il parametro NotifySfbUsers è rilevante per gli utenti locali.  Gli utenti locali ricevono la modalità dalle istanze online di TeamsUpgradePolicy. Vedi le note in [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

> [!NOTE]
> I nuovi tenant creati dopo il 3 settembre 2019 vengono creati come tenant TeamsOnly a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server. Microsoft usa i record DNS per identificare le organizzazioni Skype for Business Server locali. Per altre informazioni, vedere [Implicazioni relative al DNS per le organizzazioni locali che diventano ibride](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid).

- Gli articoli seguenti descrivono importanti concetti di aggiornamento e comportamenti di coesistenza:
  - [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
  - [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Uso del servizio MMS (Meeting Migration Service)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
