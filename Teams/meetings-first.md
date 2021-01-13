---
title: Prima riunione-Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: Informazioni sulle riunioni prima, in cui gli utenti possono creare la riunione in teams, continuando a usare Skype for business per la chat, le chiamate e la presenza.
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
ms.openlocfilehash: 34b32a1d421941e4e9c3bd743c5db1026d88a2ac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809506"
---
# <a name="meetings-first"></a>Riunioni al primo posto

"Meetings First" è mirato e ottimizzato per le organizzazioni di Skype for Business Server con VoIP aziendale nei locali che vogliono iniziare a usare le riunioni teams il più rapidamente possibile. Per queste organizzazioni, la prima riunione è un'alternativa all'uso della modalità **isole** che privilegia l'esperienza delle riunioni di teams.

## <a name="what-is-meetings-first"></a>Cos'è la prima riunione?

Riunioni prima si basa sulla modalità di coesistenza **SfBWithTeamsCollabAndMeetings** . Meetings First non è un prodotto o una funzionalità, ma è una configurazione che sfrutta le funzionalità e le funzionalità di teams e Skype for business per creare un'esperienza di coesistenza personalizzata.

Nelle riunioni prima gli utenti creano la loro riunione in teams, continuando a usare Skype for business per la chat, le chiamate e la presenza. Non esistono sovrapposizioni di modalità tra team e Skype for business. La chat, le chiamate e la presenza sono attivate in Skype for business e disattivato in teams. In questo modo, è possibile usare scenari univoci "migliori" tra Skype for business e teams che migliorano l'esperienza dell'utente durante la coesistenza e scenari di interoperabilità con solo gli utenti di **Teams** .

![Screenshot dello scenario migliore insieme con teams e Skype for business](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Riunioni prima è una corrispondenza migliore per le organizzazioni che non hanno o pochi utenti di chat di team attivi. Gli utenti di chat di team attivi non devono essere passati alla prima modalità riunioni, perché perderebbero la possibilità di chattare in teams e di accedere alla cronologia delle chat. Questi utenti dovrebbero essere prenotati in modalità **isole** e le riunioni concesse prima solo agli utenti non ancora attivi in chat in teams.

## <a name="who-should-consider-meetings-first"></a>Chi dovrebbe prendere in considerazione prima le riunioni?

Meetings First è stato progettato per le organizzazioni che usano Skype for Business Server con VoIP aziendale che vuole accelerare il passaggio alle riunioni di teams, in particolare quelle con una disciplina IT forte che vuole un percorso di aggiornamento deterministico gestito e di teams.

Per le organizzazioni complesse o di grandi dimensioni, le migrazioni vocali vengono in genere eseguite su base sito per sito e potrebbero richiedere molto tempo, potenzialmente diversi anni, con conseguente scenari di coesistenza estese. Se la coesistenza è in modalità **isole** , gli utenti avranno sempre la possibilità di scegliere tra due soluzioni per le riunioni (Skype for business e teams), che può causare situazioni confuse o subottimali. A differenza delle migrazioni vocali, le migrazioni delle riunioni possono essere in genere completate in tutta la società in un breve lasso di tempo. Le organizzazioni che vogliono passare completamente alle riunioni del team il più rapidamente possibile (e senza aspettare che la migrazione vocale sia completa) dovrebbero prendere in considerazione le riunioni prima.

Le riunioni prima potrebbero non essere utili per le organizzazioni che non hanno utenti di VoIP aziendale. Queste organizzazioni devono essere in grado di eseguire l'aggiornamento a **Teams solo** non appena sono in grado di adottare riunioni di teams. Dovrebbero considerare prima di tutto il salto delle riunioni.

Inoltre, le riunioni sono prima di tutto utili per le organizzazioni il cui ambito è una soluzione di riunione di pura riproduzione, ad esempio quando viene emessa una RDP "solo per riunioni".

## <a name="capabilities-in-meetings-first"></a>Funzionalità delle riunioni prima

La riunione per prima cosa raggruppa le funzionalità seguenti:

- Eseguire [il provisioning di un utente di Skype for Business Server (locale)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) con i servizi di [audioconferenza di teams](tutorial-audio-conferencing.yml).
- [Servizio di migrazione riunioni](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): le riunioni organizzate dall'utente verranno migrate nel cloud e convertite in riunioni di teams quando l'utente viene promosso prima alle riunioni (richiede Exchange Online).
- Esperienza utente semplificata in teams, centrata su riunioni e team e canali di Teams (che possono essere nascosti facoltativamente usando i [criteri delle autorizzazioni dell'app](teams-app-permission-policies.md)); Le [chat private di teams, le chiamate e la presenza personale](teams-client-experience-and-conformance-to-coexistence-modes.md) non vengono esposte nelle riunioni prima, consentendo lo sforzo di distribuzione e adozione per concentrarsi completamente sulle riunioni.
- [Esperienza di riunione di Team](tutorial-meetings-in-teams.yml)superiori.
- "Better Together" tra teams e Skype for business: 
  - Blocco automatico: quando si partecipa a una riunione in teams, quando si riceve una chiamata in Skype for business si terrà la riunione delle squadre in attesa e viceversa. In questo modo gli utenti possono evitare che le chiamate private vengano ascoltate dai partecipanti alle riunioni.
    ![Screenshot dello scenario migliore insieme con teams e Skype for business](media/meetings-first-better-together-hold.png)
  - Riconciliazione presenza: l'attività in teams viene applicata alla presenza dell'utente, che è la presenza di Skype for business poiché la chat e la chiamata sono in Skype for business. In particolare, quando le riunioni per primo gli utenti partecipano a una riunione di teams, la loro presenza verrà aggiornata per riflettere. Quando presentano il loro schermo, la loro presenza verrà aggiornata per mostrare non disturbare (in base alle impostazioni di Skype for business).
  - Riconciliazione del controllo HID per dispositivi USB (disponibile anche su Mac): i controlli HID sono onorati da teams durante le riunioni di teams e da Skype for business in tutte le altre circostanze.
  - A meno che non sia diversamente menzionato, le funzionalità più efficienti richiedono i client desktop di Windows recenti in questo momento.

## <a name="prerequisites-for-meetings-first"></a>Prerequisiti per le riunioni prima

Gli unici requisiti rigidi per le riunioni sono gli stessi dei requisiti per i team con Active Directory locale e una distribuzione locale di Skype for business:

- [Requisiti generali per i team](upgrade-plan-journey-prerequisites.md), incluso
- [Identità e autenticazione in teams](identify-models-authentication.md) e
- [Configurare Azure Active Directory per Teams e Skype for business](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect).

Non è necessaria una [topologia ibrida di Skype for business](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) , ma è consigliabile. Alcune funzionalità come il servizio di migrazione delle riunioni e l'interoperabilità si basano su tale topologia.

Riunioni prima è supportato con qualsiasi versione di Skype for Business Server (e noto per l'utilizzo con il server Lync non più supportato). È supportata da qualsiasi client Skype for business supportato, ma le funzionalità più efficaci richiedono un client recente.

Una volta soddisfatti questi requisiti (e non prima), gli utenti possono essere [concessi in licenza per Microsoft 365 o Office 365 e teams](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts).

Per la prima esperienza delle riunioni migliori, gli utenti devono essere abilitati per la creazione di gruppi di [Exchange Online](exchange-teams-interact.md), [SharePoint Online e OneDrive for Business](sharepoint-onedrive-interact.md)e Microsoft 365. Riunioni prima è supportato per gli utenti la cui cassetta postale si trova in Exchange locale o che non dispongono di SharePoint Online o OneDrive for business o creazione di gruppi di Microsoft 365. Tuttavia, la loro esperienza sarà meno completa. In particolare, per le organizzazioni che usano Exchange Server locale, potrebbe essere possibile (a seconda della versione di Exchange Server) alcune limitazioni per la creazione e la visualizzazione di riunioni dal client teams, nonché per quanto riguarda le funzionalità di conformità.

Almeno gli utenti devono essere [concessi in licenza per i team](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users). Possono inoltre essere concessi in licenza per i servizi di [audioconferenza](set-up-audio-conferencing-in-teams.md), se necessario.

Ti consigliamo di [concedere la modalità **SfBOnly** o **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) come predefinito del tenant al momento della licenza per gli utenti. In questo modo gli utenti non inizieranno a usare i team da soli nella modalità **isole** predefinite prima di essere pronti per avviare prima le riunioni.

Riunioni per primo è supportato nei client desktop completi (Windows e Mac), nei client del browser e nei client mobili. È anche compatibile con [le sale di Microsoft teams](https://docs.microsoft.com/microsoftteams/room-systems/). Meglio insieme richiede il client desktop completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Preparare per le riunioni di teams nelle riunioni prima

Per consentire agli utenti di avere la migliore esperienza possibile in riunioni teams, è consigliabile:

- Seguire i passaggi descritti in [riunioni e conferenze per Microsoft teams](deploy-meetings-microsoft-teams-landing-page.md), in particolare.
- [Valutare l'ambiente](3-envision-evaluate-my-environment.md).
- [Preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md).
- Aggiornare le sale riunioni con Team [che supportano dispositivi e soluzioni per la sala riunioni](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)oppure usare il [cloud video Interop per Microsoft teams](cloud-video-interop.md) per consentire alle riunioni e ai dispositivi di terze parti esistenti di partecipare alla riunione di teams.
- Dotare gli utenti di [dispositivi audio e video USB certificati](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).
- Prepararsi a [promuovere la sensibilizzazione e l'adozione per le riunioni di teams](adopt-microsoft-teams-landing-page.md).
- [Pianificare la gestione dei servizi](4-envision-plan-my-service-management.md).
- Acquisire familiarità con i report di analisi delle chiamate avanzate per [risolvere i problemi di qualità delle chiamate scadenti](use-call-analytics-to-troubleshoot-poor-call-quality.md).

In questa fase potresti considerare l'uso di un pilota pronto per la produzione in scala moderata.

## <a name="configure-users-for-meetings-first"></a>Configurare prima gli utenti per le riunioni

Dopo aver concesso la licenza agli utenti e aver preparato l'organizzazione per le riunioni di teams, è il momento di abilitare prima gli utenti per le riunioni. È stato semplificato: un'unica impostazione consente di eseguire tutte le operazioni seguenti.

Tutte le funzionalità e le esperienze degli utenti nelle riunioni prima, inclusa la configurazione del client teams e la [conformità automatica](teams-client-experience-and-conformance-to-coexistence-modes.md) dell'esperienza utente, del servizio di migrazione delle riunioni e delle migliori funzionalità insieme, vengono configurate concedendo all'utente (o al gruppo di utenti o al tenant) la [modalità di coesistenza di SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) nell'interfaccia di [amministrazione di Microsoft teams](manage-teams-in-modern-portal.md) oppure usando [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Screenshot delle impostazioni di amministrazione per abilitare prima le riunioni](media/teams-meeting-admin-settings.png)

Facoltativamente, se si vuole nascondere l'applicazione Teams and Channels dalla barra di spostamento sinistra del client teams degli utenti, per concentrarsi ulteriormente sulle proprie esperienze sulle riunioni, che è possibile ottenere usando i [criteri di autorizzazione dell'app](teams-app-permission-policies.md).

## <a name="reporting-and-call-analytics"></a>Analisi delle segnalazioni e delle chiamate

I report e le analisi delle chiamate per le riunioni di team in riunioni prima sono invariati rispetto alle altre modalità.

## <a name="related-links"></a>Collegamenti correlati

Dopo aver esaminato questo articolo, è consigliabile consultare [scegliere il percorso di aggiornamento, le](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)indicazioni per la [migrazione e l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)e la [coesistenza con Skype for business](coexistence-chat-calls-presence.md) per ulteriori dettagli.


