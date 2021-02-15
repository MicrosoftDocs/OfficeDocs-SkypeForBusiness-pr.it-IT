---
title: Prima riunione - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Informazioni su Riunioni prima di tutto, in cui gli utenti possono creare le riunioni in Teams, continuando a usare Skype for Business per chat, chiamate e presenza.
localization_priority: Normal
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
ms.openlocfilehash: c4e4eba45e7f6719b1fb3427ebd169b69a1e86c9
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871077"
---
# <a name="meetings-first"></a>Riunioni al primo posto

"Riunioni prima di tutto" è mirato e ottimizzato per le organizzazioni skype for Business Server con VoIP aziendale locale che vogliono iniziare a usare le riunioni di Teams il più rapidamente possibile. Per queste organizzazioni, Meetings First è  un'alternativa all'uso della modalità Isole che dà priorità all'esperienza delle riunioni di Teams.

## <a name="what-is-meetings-first"></a>Che cos'è Meetings First?

Meetings First si basa sulla modalità di coesistenza **di SfBWithTeamsCollabAndMeetings.** Meetings First non è un prodotto o una funzionalità, ma una configurazione che usa funzionalità e funzionalità di Teams e Skype for Business per offrire un'esperienza di coesistenza personalizzata.

In Meetings First gli utenti creano la riunione in Teams, continuando allo stesso tempo a usare Skype for Business per chat, chiamate e presenza. Non ci sono sovrapposizioni tra le modali tra Teams e Skype for Business. Chat, chiamate e presenza sono in skype for Business e disattivate in Teams. Ciò consente scenari univoci di "migliore collaborazione" tra Skype for Business e Teams che migliorano l'esperienza dell'utente durante la coesistenza, nonché scenari di interoperabilità con gli utenti solo di **Teams.**

![Screenshot dello scenario migliore insieme con Teams e Skype for Business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Riunioni per prima cosa è la corrispondenza migliore per le organizzazioni che non hanno o pochi utenti di chat attivi di Teams. Gli utenti di chat di Active Teams non devono passare alla modalità Riunioni prima, perché perderebbero la possibilità di chattare in Teams e di accedere alla loro cronologia chat. Questi utenti dovrebbero invece essere selezionati **in** modalità Isole e le riunioni concesse per la prima volta solo agli utenti non ancora attivi nella chat in Teams.

## <a name="who-should-consider-meetings-first"></a>Chi deve considerare prima le riunioni?

Meetings First è stato progettato per le organizzazioni che usano Skype for Business Server con VoIP aziendale che vogliono accelerare il passaggio alle riunioni di Teams, soprattutto quelle con una forte disciplina IT che vogliono un percorso di aggiornamento a Teams gestito e deterministico.

Per le organizzazioni complesse o di grandi dimensioni, le migrazioni vocali vengono in genere eseguite su base sito e potrebbero richiedere molto tempo, potenzialmente diversi anni, causando scenari di coesistenza estesi. Se tale coesistenza si trova **in** modalità Isole, gli utenti avranno sempre la scelta di due soluzioni per le riunioni (Skype for Business e Teams), il che può confondere o creare situazioni poco efficaci. A differenza delle migrazioni vocali, le migrazioni delle riunioni in genere possono essere completate nell'intera azienda in un breve periodo di tempo. Le organizzazioni che vogliono passare completamente alle riunioni di Teams il più rapidamente possibile (e senza attendere che la migrazione vocale sia completata) dovrebbero prendere in considerazione Le riunioni prima di tutto.

Riunioni per prima cosa potrebbe non essere utile per le organizzazioni che non hanno VoIP aziendale utenti. Queste organizzazioni dovrebbero essere in grado di eseguire l'aggiornamento a **Teams** solo non appena saranno in grado di adottare le riunioni di Teams. È consigliabile saltare prima le riunioni.

Inoltre, Meetings First è utile per le organizzazioni il cui ambito è una soluzione di riunione esclusivamente play, ad esempio quando viene rilasciata una RDP "solo per le riunioni".

## <a name="capabilities-in-meetings-first"></a>Funzionalità in Prima riunione

Meeting First riunisce le seguenti funzionalità:

- [Effettuare il provisioning di un utente Skype for Business Server (locale)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) con [Le audioconferenze di Teams.](tutorial-audio-conferencing.yml)
- [Servizio di migrazione delle](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)riunioni: le riunioni organizzate dall'utente verranno migrate nel cloud e convertite in riunioni di Teams quando l'utente viene promosso in Riunioni per la prima volta (richiede Exchange Online).
- Esperienza utente semplificata in Teams, centrata sulle riunioni e sui team e i canali di Teams (che, facoltativamente, può essere nascosta usando il criterio [Autorizzazioni app);](teams-app-permission-policies.md) [Le chat private, le chiamate e l'auto-presenza](teams-client-experience-and-conformance-to-coexistence-modes.md) di Teams non vengono prima esposti nelle riunioni, consentendo di distribuzione e adozione di concentrarsi completamente sulle riunioni.
- Esperienza di [riunione di Teams superiore.](tutorial-meetings-in-teams.yml)
- "Better Together" tra Teams e Skype for Business: 
  - Blocco automatico: durante una riunione in Teams, una chiamata in Skype for Business mette in attesa la riunione di Teams e viceversa. In questo modo si evita che gli utenti si sorrisino le chiamate private dai partecipanti alla riunione.
    ![Screenshot dello scenario migliore insieme con Teams e Skype for Business](media/meetings-first-better-together-hold.png)
  - Riconciliazione della presenza: l'attività in Teams si riflette nella presenza dell'utente, che è la presenza di Skype for Business perché chat e chiamate sono in Skype for Business. In particolare, quando gli utenti di Meetings First sono in una riunione di Teams, la loro presenza verrà aggiornata per riflettere questo fatto. Quando presenta lo schermo, la loro presenza viene aggiornata in modo da mostrare Non disturbare (in base alle impostazioni in Skype for Business).
  - Riconciliazione dei controlli HID dei dispositivi USB (disponibile anche su Mac): i controlli HID vengono rispettati da Teams durante le riunioni di Teams e da Skype for Business in tutti gli altri casi.
  - Se non diversamente specificato, al momento le funzionalità Better Together richiedono client desktop di Windows recenti.

## <a name="prerequisites-for-meetings-first"></a>Prerequisiti per le riunioni per la prima volta

Gli unici requisiti rigidi per Meetings First sono gli stessi di Teams con Active Directory locale e una distribuzione locale di Skype for Business:

- [Prerequisiti generali per Teams,](upgrade-plan-journey-prerequisites.md)inclusi
- [Identità e autenticazione in Teams](identify-models-authentication.md) e
- [Configurare Azure Active Directory per Teams e Skype for Business.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

Non è richiesta una topologia ibrida di [Skype for Business,](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ma è consigliabile. Alcune funzionalità, come il servizio di migrazione delle riunioni e l'interoperabilità, si basano su questa topologia.

Meetings First è supportato con qualsiasi versione di Skype for Business Server (e noto per funzionare con Lync Server non più supportato). È supportato con qualsiasi client Skype for Business supportato, tuttavia le funzionalità Insieme migliore richiedono un client recente.

Una volta soddisfatti questi requisiti (e non prima), gli utenti possono essere concessi in licenza [per Microsoft 365 o Office 365 e Teams.](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)

Per un'esperienza ottimale con Riunioni prima, gli utenti devono essere abilitati per [Exchange Online,](exchange-teams-interact.md) [SharePoint Online, OneDrive for Business](sharepoint-onedrive-interact.md)e per la creazione di gruppi di Microsoft 365. Riunioni per prima cosa è supportato per gli utenti la cui cassetta postale si trova in Exchange locale o che non hanno SharePoint Online o OneDrive For Business o la creazione di gruppi di Microsoft 365. Tuttavia, l'esperienza sarà meno completa. In particolare, per le organizzazioni che usano Exchange Server locale, potrebbero esserci (a seconda della versione di Exchange Server) alcune limitazioni alla creazione e visualizzazione delle riunioni dal client Teams, oltre che per quanto riguarda le funzionalità di conformità.

È necessario che gli utenti siano almeno [concessi in licenza per Teams.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) Inoltre, possono essere concesse in licenza per [i servizi di audioconferenza,](set-up-audio-conferencing-in-teams.md)se necessario.

È consigliabile concedere come predefinita la modalità [ **SfBOnly** o **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) come tenant quando si concede la licenza agli utenti. In questo modo gli utenti non inizieranno  a usare Teams da soli nella modalità isole predefinita prima che tu sia pronto per il lancio di Meetings First.

Meetings First è supportato nei client desktop completi (Windows e Mac), nei client browser e nei client mobili. È anche compatibile con [Microsoft Teams Rooms.](https://docs.microsoft.com/microsoftteams/room-systems/) Better Together richiede il client desktop completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparare prima le riunioni di Teams in Riunioni

Per consentire agli utenti di avere la migliore esperienza possibile nelle riunioni di Teams, è necessario:

- Segui i passaggi nelle [riunioni e nelle conferenze per Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)in particolare.
- [Valutare l'ambiente.](3-envision-evaluate-my-environment.md)
- [Preparare la rete dell'organizzazione per Microsoft Teams.](prepare-network.md)
- Aggiornare le sale riunioni [](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)con soluzioni e dispositivi della sala riunioni compatibili con Teams oppure usare [Cloud Video Interoperabilità](cloud-video-interop.md) per Microsoft Teams per consentire alle sale e ai dispositivi di terze parti esistenti di partecipare alle riunioni di Teams.
- Fornire agli utenti [dispositivi audio e video USB certificati .](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Prepararsi a [guidare la consapevolezza e l'adozione per le riunioni di Teams.](adopt-microsoft-teams-landing-page.md)
- [Pianificare la gestione dei servizi.](4-envision-plan-my-service-management.md)
- Familiarizzare con i report di Call Analytics per risolvere [i problemi di bassa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

In questa fase è consigliabile eseguire un progetto pilota di produzione su scala moderata.

## <a name="configure-users-for-meetings-first"></a>Configurare prima gli utenti per Riunioni

Dopo aver concesso la licenza agli utenti e preparato l'organizzazione per le riunioni di Teams, è il momento di abilitare prima gli utenti alle riunioni. Abbiamo reso più semplice questa operazione: un'unica impostazione farà tutto il possibile.

Tutte le funzionalità e le esperienze utente in [](teams-client-experience-and-conformance-to-coexistence-modes.md) Meetings First, incluse la configurazione del client Teams e la conformità automatica dell'esperienza utente, il servizio di migrazione delle riunioni e le funzionalità di Better Together, vengono configurate concedendo all'utente (o gruppo di utenti o impostazione predefinita del tenant) la modalità di coesistenza [sfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) nell'interfaccia di amministrazione di [Microsoft Teams](manage-teams-in-modern-portal.md) o tramite [PowerShell.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

![Screenshot delle impostazioni dell'amministratore per abilitare Prima riunione](media/teams-meeting-admin-settings.png)

Facoltativamente, è consigliabile nascondere l'applicazione Teams e canali dal riquadro di spostamento sinistro del client Teams degli utenti per concentrare ulteriormente l'esperienza sulle riunioni, che possono essere ottenute utilizzando i criteri di autorizzazione [app.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>Creazione di report e Call Analytics

Segnalazione e Call Analytics per le riunioni di Teams in Riunioni Prima di tutto rimangono invariate rispetto alle altre modalità.

## <a name="related-links"></a>Collegamenti correlati

Dopo aver rivisto questo articolo, consultare Scegliere il percorso di [aggiornamento,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)le indicazioni per la migrazione e l'interoperabilità [e](migration-interop-guidance-for-teams-with-skype.md)la coesistenza con [Skype for Business](coexistence-chat-calls-presence.md) per ulteriori informazioni.


