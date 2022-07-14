---
title: Prima riunione - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Informazioni su Riunioni, in cui gli utenti possono creare la riunione in Teams, continuando a usare Skype for Business per chat, chiamate e presenza.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 149a5a3e22a633ec4c889b68a91ac9c6db8e9f4b
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789781"
---
# <a name="meetings-first"></a>Riunioni al primo posto

"Riunioni prima di tutto" è mirato e ottimizzato per Skype for Business Server organizzazioni con VoIP aziendale locale che vogliono iniziare a usare le riunioni di Teams il più rapidamente possibile. Per queste organizzazioni, Riunioni prima è un'alternativa all'uso della modalità **Isole** che assegna priorità all'esperienza delle riunioni di Teams.

## <a name="what-is-meetings-first"></a>Che cos'è Riunioni per primo?

Riunioni prima di tutto si basa sulla modalità coesistenza **SfBWithTeamsCollabAndMeetings** . Riunioni prima di tutto non è un prodotto o una funzionalità, è una configurazione che usa le funzionalità e le funzionalità di Teams e Skype for Business per offrire un'esperienza di coesistenza personalizzata in modo univoco.

In Riunioni prima di tutto, gli utenti creano la riunione in Teams, continuando comunque a usare Skype for Business per chat, chiamate e presenza. Non vi è sovrapposizione delle modalità tra Teams e Skype for Business. Chat, chiamate e presenza sono attivati in Skype for Business e disattivati in Teams. Ciò consente scenari univoci "migliori insieme" tra Skype for Business e Teams che migliorano l'esperienza dell'utente durante la coesistenza, nonché scenari di interoperabilità con gli utenti **di Teams Only**.

![Screenshot dello scenario migliore insieme a Teams e Skype for Business.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Riunioni primo è una corrispondenza migliore per le organizzazioni che non hanno o pochi utenti di chat di Teams attivi. Gli utenti di chat di Teams attivi non devono passare alla modalità Prima riunione, in quanto perderebbero la possibilità di chattare in Teams e di accedere alla cronologia chat. Questi utenti devono invece essere non abili nella modalità **Isole** e Riunioni prima concessi solo agli utenti non ancora attivi nella chat in Teams.

## <a name="who-should-consider-meetings-first"></a>Chi deve prendere in considerazione prima Le riunioni?

Riunioni First è stato progettato per le organizzazioni che usano Skype for Business Server con VoIP aziendale che vogliono accelerare il passaggio alle riunioni di Teams, in particolare quelle con una forte disciplina IT che vogliono un percorso di aggiornamento gestito e deterministico a Teams.

Per le organizzazioni complesse o di grandi dimensioni, le migrazioni vocali vengono in genere eseguite su base site-by-site e potrebbero richiedere molto tempo, potenzialmente diversi anni, con conseguente estesa coesistenza di scenari. Se tale coesistenza è in modalità **Isole**, gli utenti avranno sempre la scelta di due soluzioni di riunione (Skype for Business e Teams), che possono causare situazioni poco chiare o non ottimali. A differenza delle migrazioni vocali, le migrazioni delle riunioni in genere possono essere completate in tutta l'azienda in un breve lasso di tempo. Le organizzazioni che vogliono passare completamente alle riunioni di Teams il più rapidamente possibile (e senza attendere il completamento della migrazione vocale) devono prendere in considerazione riunioni prima di tutto.

Riunioni prima di tutto potrebbe non essere utile per le organizzazioni che non hanno VoIP aziendale utenti. Queste organizzazioni dovrebbero essere in grado di eseguire l'aggiornamento a **Solo Teams** non appena sono in grado di adottare le riunioni di Teams. È consigliabile saltare prima le riunioni.

Inoltre, Riunioni prima è utile per le organizzazioni il cui ambito è una soluzione per riunioni pure-play, ad esempio quando viene emesso un elenco di richieste d'offerta "solo riunioni".

## <a name="capabilities-in-meetings-first"></a>Funzionalità prima di tutto in Riunioni

Meeting First riunisce le funzionalità seguenti:

- [Effettuare il provisioning di un utente Skype for Business Server (locale)](./tutorial-audio-conferencing.yml?tutorial-step=3) con [Le audioconferenze di Teams](tutorial-audio-conferencing.yml).
- [Servizio di migrazione delle riunioni](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): le riunioni organizzate dall'utente verranno migrate nel cloud e convertite in riunioni di Teams man mano che l'utente viene promosso a Riunioni (richiede Exchange Online).
- Esperienza utente semplificata in Teams, incentrata sulle riunioni e sui team e i canali di Teams (che facoltativamente possono essere nascosti usando i [criteri Autorizzazioni app](teams-app-permission-policies.md)); [Le chat private, le chiamate e la presenza in autonomia di Teams](teams-client-experience-and-conformance-to-coexistence-modes.md) non vengono esposte prima alle riunioni, consentendo l'impegno per la distribuzione e l'adozione per concentrarsi completamente sulle riunioni.
- [Esperienza di riunione di Teams](tutorial-meetings-in-teams.yml) superiore.
- "Insieme migliore" tra Teams e Skype for Business: 
  - Blocco automatico: durante una riunione in Teams, partecipare a una chiamata in Skype for Business mette la riunione di Teams in attesa e viceversa. In questo modo si impedisce agli utenti di farsi le chiamate private dai partecipanti alla riunione.
    ![Screenshot dello scenario migliore insieme a Teams e Skype for Business.](media/meetings-first-better-together-hold.png)
  - Riconciliazione della presenza: l'attività in Teams si riflette nella presenza dell'utente, che è la presenza Skype for Business dal momento che la chat e le chiamate si trovano in Skype for Business. In particolare, quando gli utenti di Riunioni sono presenti in una riunione di Teams, la loro presenza verrà aggiornata in modo da riflettere questo aspetto. Quando presentano lo schermo, la loro presenza verrà aggiornata in modo da visualizzare Non disturbare (in base alle impostazioni in Skype for Business).
  - Riconciliazione dei controlli HID del dispositivo USB (disponibile anche su Mac): i controlli HID sono rispettati da Teams durante le riunioni di Teams e da Skype for Business in tutte le altre circostanze.
  - Se non diversamente indicato, le funzionalità Better Together richiedono client desktop recenti di Windows in questo momento.

## <a name="prerequisites-for-meetings-first"></a>Prerequisiti per le riunioni

Gli unici requisiti fissi per le riunioni sono gli stessi dei requisiti per Teams con Active Directory locale e una distribuzione locale Skype for Business:

- [Prerequisiti generali per Teams](upgrade-plan-journey-prerequisites.md), tra cui
- [Identità e autenticazione in Teams](identify-models-authentication.md) e
- [Configurare Azure Active Directory per Teams e Skype for Business](/skypeforbusiness/hybrid/configure-azure-ad-connect).

Non è necessaria [una topologia ibrida Skype for Business](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online), ma è consigliabile. Alcune funzionalità, come il servizio di migrazione delle riunioni e l'interoperabilità, si basano su questa topologia.

Riunioni primo è supportato con qualsiasi versione del Skype for Business Server (e noto per funzionare con Lync Server non più supportato). È supportato con qualsiasi client Skype for Business supportato, tuttavia le funzionalità Better Together richiedono un client recente.

Una volta soddisfatti questi requisiti (e non prima), gli utenti possono essere [concessi in licenza per Microsoft 365 o Office 365 e Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Per un'esperienza ottimale con Riunioni per la prima volta, gli utenti devono essere abilitati per [Exchange Online](exchange-teams-interact.md)[, SharePoint Online e OneDrive for Business](sharepoint-onedrive-interact.md) e la creazione di gruppi di Microsoft 365. Riunioni è supportato per gli utenti la cui cassetta postale si trova in Exchange locale o che non hanno SharePoint Online o OneDrive For Business oppure per la creazione di gruppi di Microsoft 365. Tuttavia, la loro esperienza sarà meno completa. In particolare, per le organizzazioni che usano Exchange Server in locale, potrebbero esserci alcune limitazioni (a seconda della versione di Exchange Server) per la creazione e la visualizzazione delle riunioni dal client teams, oltre che per quanto riguarda le funzionalità di conformità.

Come minimo, gli utenti devono avere [una licenza per Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Inoltre, se necessario, possono essere concesse in licenza per le [audioconferenze](set-up-audio-conferencing-in-teams.md).

È consigliabile concedere la modalità [**tenant predefinita SfBOnly** o **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) al momento della licenza degli utenti. In questo modo gli utenti non inizierebbero a usare Teams autonomamente nella modalità **isole** predefinita prima che tu sia pronto per avviare Prima le riunioni.

Riunioni primo è supportato nei client desktop completi (Windows e Mac), nei client del browser e nei client mobili. È compatibile anche con [Microsoft Teams Rooms](/microsoftteams/room-systems/). Better Together richiede il client desktop completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparare prima le riunioni di Teams in Riunioni

Affinché gli utenti abbiano la migliore esperienza possibile nelle riunioni di Teams, è necessario:

- Seguire i passaggi descritti in [Riunioni e conferenze per Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md), in particolare.
- [Valutare l'ambiente](3-envision-evaluate-my-environment.md).
- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md).
- Aggiornare le sale riunioni con [le soluzioni e i dispositivi delle sale riunioni](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) compatibili con Teams oppure usare [Cloud Video Interop per Microsoft Teams per](cloud-video-interop.md) consentire alle sale e ai dispositivi di terze parti esistenti di partecipare alle riunioni di Teams.
- Fornisci agli utenti [dispositivi audio e video USB certificati](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- Prepararsi a [promuovere la consapevolezza e l'adozione per le riunioni di Teams](adopt-microsoft-teams-landing-page.md).
- [Pianificare la gestione dei servizi](4-envision-plan-my-service-management.md).
- Acquisire familiarità con i report avanzati di Call Analytics per [risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).

In questa fase è consigliabile eseguire un progetto pilota di produzione su scala moderata.

## <a name="configure-users-for-meetings-first"></a>Configurare prima gli utenti per le riunioni

Dopo aver concesso la licenza agli utenti e preparato l'organizzazione per le riunioni di Teams, è il momento di abilitare prima gli utenti per le riunioni. Abbiamo reso tutto più semplice: una singola impostazione farà tutto!

Tutte le funzionalità e le esperienze utente in Riunioni, inclusa la configurazione client di Teams e la [conformità automatica](teams-client-experience-and-conformance-to-coexistence-modes.md) dell'esperienza utente, il servizio di migrazione delle riunioni e le funzionalità Better Together, sono configurate concedendo all'utente (o gruppo di utenti, o impostazione predefinita del tenant) la [modalità di coesistenza SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) [nell'interfaccia di amministrazione di Microsoft Teams](manage-teams-in-modern-portal.md) o tramite [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Screenshot delle impostazioni dell'amministratore per abilitare prima Riunioni.](media/teams-meeting-admin-settings.png)

Facoltativamente, se si vuole nascondere l'applicazione Teams e canali dal riquadro di spostamento sinistro del client Teams degli utenti per concentrarsi ulteriormente sulla loro esperienza sulle riunioni, che possono essere raggiunte usando i [criteri di configurazione dell'app](teams-app-setup-policies.md).

## <a name="reporting-and-call-analytics"></a>Creazione di report e Call Analytics

La creazione di report e call analytics per le riunioni di Teams in Riunioni prima di tutto non sono invariati rispetto a ciò che si trovano in altre modalità.

## <a name="related-links"></a>Collegamenti correlati

Dopo aver esaminato questo articolo, è consigliabile consultare [Scegliere il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [le indicazioni sulla migrazione e l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md) e [la coesistenza con Skype for Business](coexistence-chat-calls-presence.md) per altre informazioni.
