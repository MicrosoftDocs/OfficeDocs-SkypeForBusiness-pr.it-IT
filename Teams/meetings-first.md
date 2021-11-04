---
title: Prima riunione - Microsoft Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: Informazioni su Meetings First, in cui gli utenti possono creare la riunione in Teams, continuando a usare Skype for Business per chat, chiamate e presenza.
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
ms.openlocfilehash: 2aafa115d6da600df17ac18e4b1af66358efb16b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741642"
---
# <a name="meetings-first"></a>Riunioni al primo posto

"Meetings First" è rivolto e ottimizzato per le organizzazioni Skype for Business Server con VoIP aziendale locali che vogliono iniziare a usare le riunioni Teams il più rapidamente possibile. Per queste organizzazioni, Meetings First è  un'alternativa all'uso della modalità Isole che assegna priorità all'esperienza Teams riunioni.

## <a name="what-is-meetings-first"></a>Che cos'è Meetings First?

Meetings First si basa sulla modalità di coesistenza **SfBWithTeamsCollabAndMeetings.** Meetings First non è un prodotto o una funzionalità, ma una configurazione che usa funzionalità e funzionalità di Teams e Skype for Business per offrire un'esperienza di coesistenza personalizzata.

In Riunioni per prime, gli utenti creano la riunione in Teams, continuando a usare Skype for Business per chat, chiamate e presenza. Non ci sono sovrapposizioni di modalità tra Teams e Skype for Business. La chat, le chiamate e la presenza sono Skype for Business e disattivate in Teams. In questo modo vengono abilitati scenari univoci di "migliore collaborazione" tra Skype for Business e Teams che migliorano l'esperienza dell'utente durante la coesistenza, oltre a scenari di interoperabilità con Teams **solo** gli utenti.

![Screenshot dello scenario migliore insieme a Teams e Skype for Business.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> Meetings First è una soluzione migliore per le organizzazioni che non hanno o pochi utenti di chat Teams attivi. Le Teams chat attive non devono essere passate alla modalità Riunioni prima, perché perderebbero la possibilità di chattare in Teams e di accedere alla cronologia chat. Questi utenti dovrebbero essere  invece in modalità Isole e Riunioni prima concesse solo agli utenti non ancora attivi nella chat in Teams.

## <a name="who-should-consider-meetings-first"></a>Who prendere in considerazione Riunioni per prime?

Meetings First è stato progettato per le organizzazioni che usano Skype for Business Server con VoIP aziendale che vogliono accelerare il passaggio alle riunioni di Teams, in particolare quelle con una forte disciplina IT che vogliono un percorso di aggiornamento deterministico gestito a Teams.

Per le organizzazioni complesse o di grandi dimensioni, le migrazioni vocali vengono in genere eseguite in base al sito e potrebbero richiedere molto tempo, potenzialmente diversi anni, con scenari di coesistenza estesa. Se la coesistenza è **in** modalità Isole, gli utenti avranno sempre la possibilità di scegliere due soluzioni per le riunioni (Skype for Business e Teams), che possono generare situazioni confusa o non ottimale. A differenza delle migrazioni vocali, le migrazioni delle riunioni in genere possono essere completate nell'intera azienda in un breve periodo di tempo. Le organizzazioni che vogliono passare completamente a Teams riunioni il più rapidamente possibile (e senza attendere il completamento della migrazione vocale) devono prendere in considerazione Riunioni prima di tutto.

Riunioni prima potrebbe non essere utile per le organizzazioni che non hanno VoIP aziendale utenti. Queste organizzazioni dovrebbero essere in grado di eseguire l'aggiornamento **a Teams** solo non appena saranno in grado di adottare Teams riunioni. È consigliabile ignorare prima le riunioni.

Inoltre, Meetings First è utile per le organizzazioni il cui ambito è una soluzione di riunione di puro gioco, ad esempio quando viene emesso un rfP "solo riunioni".

## <a name="capabilities-in-meetings-first"></a>Funzionalità nelle riunioni per prime

Meeting First riunisce le funzionalità seguenti:

- [Eseguire il provisioning Skype for Business Server utente (locale)](./tutorial-audio-conferencing.yml?tutorial-step=3) con audioconferenza [Teams audio.](tutorial-audio-conferencing.yml)
- [Servizio di migrazione riunioni:](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)le riunioni organizzate dall'utente verranno migrate nel cloud e convertite in riunioni Teams quando l'utente viene alzato di livello a Riunioni prima (richiede Exchange Online).
- Esperienza utente semplificata in Teams, centrata su riunioni Teams, team e canali (che facoltativamente possono essere nascosti usando il criterio [Autorizzazioni app](teams-app-permission-policies.md)); Teams le [chat private,](teams-client-experience-and-conformance-to-coexistence-modes.md) le chiamate e l'auto-presenza non vengono esposte in Meetings First, consentendo agli sforzi di distribuzione e adozione di concentrarsi completamente sulle riunioni.
- Esperienza [Teams riunione.](tutorial-meetings-in-teams.yml)
- "Meglio insieme" tra Teams e Skype for Business: 
  - Blocco automatico: quando si è in una riunione in Teams, quando si riceve una chiamata in Skype for Business la riunione Teams viene in attesa e viceversa. In questo modo gli utenti non potranno vedere le chiamate private dei partecipanti alle riunioni.
    ![Screenshot dello scenario migliore insieme a Teams e Skype for Business.](media/meetings-first-better-together-hold.png)
  - Riconciliazione della presenza: l'attività in Teams si riflette nella presenza dell'utente, che è la presenza Skype for Business dal momento che chat e chiamate sono in Skype for Business. In particolare, quando gli utenti di Meetings First sono in una riunione Teams, la loro presenza verrà aggiornata in modo da rispecchiare questo. Quando presentano lo schermo, la loro presenza verrà aggiornata in modo da mostrare Non disturbare (in base alle impostazioni in Skype for Business).
  - Riconciliazione del controllo HID del dispositivo USB (disponibile anche per Mac): i controlli HID sono rispettati da Teams durante le riunioni Teams e Skype for Business in tutte le altre circostanze.
  - Se non diversamente specificato, le funzionalità di Better Together richiedono Windows client desktop recenti al momento.

## <a name="prerequisites-for-meetings-first"></a>Prerequisiti per le riunioni

Gli unici requisiti rigidi per Meetings First sono gli stessi di Teams con Active Directory locale e una distribuzione Skype for Business locale:

- [Prerequisiti generali per l'Teams](upgrade-plan-journey-prerequisites.md), tra cui
- [Identità e autenticazione in Teams](identify-models-authentication.md) e
- [Configurare Azure Active Directory per Teams e Skype for Business](/skypeforbusiness/hybrid/configure-azure-ad-connect).

Non [Skype for Business una topologia ibrida,](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) ma è consigliabile. Alcune funzionalità, ad esempio servizio di migrazione riunioni e interoperabilità, si basano su tale topologia.

Meetings First è supportato con qualsiasi versione del Skype for Business Server (e noto per funzionare con Lync Server non più supportato). È supportato con qualsiasi client Skype for Business, tuttavia le funzionalità Better Together richiedono un client recente.

Una volta soddisfatti questi requisiti (e non prima), gli utenti possono essere concessi in licenza per Microsoft 365 [o Office 365 e Teams](/office365/enterprise/assign-licenses-to-user-accounts).

Per un'esperienza ottimale di Meetings First, gli utenti devono essere abilitati per [Exchange Online,](exchange-teams-interact.md) [SharePoint Online](sharepoint-onedrive-interact.md)e OneDrive for Business e Microsoft 365 creazione di gruppi. Meetings First è supportato per gli utenti la cui cassetta postale si trova Exchange locale o che non hanno SharePoint Online o OneDrive For Business o la creazione Microsoft 365 gruppo. Tuttavia, la loro esperienza sarà meno completa. In particolare, per le organizzazioni che usano Exchange Server locale, potrebbero esserci (a seconda della versione di Exchange Server) alcune limitazioni alla creazione e alla visualizzazione di riunioni dal client Teams, oltre che per quanto riguarda le funzionalità di conformità.

Gli utenti devono avere almeno una [licenza per Teams](/microsoft-365/admin/manage/assign-licenses-to-users). Inoltre, possono essere concessi in licenza per le [audioconferenze,](set-up-audio-conferencing-in-teams.md)se necessario.

È consigliabile [concedere la modalità **SfBOnly** o **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) come impostazione predefinita del tenant al momento della licenza per gli utenti. In questo modo, gli utenti non inizieranno a  Teams da soli nella modalità isole predefinita prima di essere pronti per avviare Riunioni per prime.

Meetings First è supportato nei client desktop completi (Windows e Mac), nei client browser e nei client mobili. È anche compatibile con [Microsoft Teams Rooms](/microsoftteams/room-systems/). Better Together richiede il client desktop completo.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>Prepararsi per Teams riunioni in Meetings First

Per consentire agli utenti di avere la migliore esperienza possibile nelle riunioni Teams, è consigliabile:

- Seguire i passaggi descritti in Riunioni e conferenze per [Microsoft Teams,](deploy-meetings-microsoft-teams-landing-page.md)in particolare.
- [Valutare l'ambiente](3-envision-evaluate-my-environment.md).
- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md).
- Aggiornare le sale riunioni con [](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)Teams dispositivi e soluzioni per le sale riunioni o usare [Cloud Video Interop](cloud-video-interop.md) per Microsoft Teams per consentire alle sale e ai dispositivi di terze parti esistenti di partecipare Teams riunioni.
- Dotare gli utenti di [dispositivi audio e video USB certificati.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Prepararsi a [guidare la consapevolezza e l'adozione per Teams riunioni.](adopt-microsoft-teams-landing-page.md)
- [Pianificare la gestione dei servizi](4-envision-plan-my-service-management.md).
- Acquisire familiarità con i report di Call Analytics per risolvere [i problemi relativi alla scarsa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

In questa fase è consigliabile eseguire un progetto pilota pronto per la produzione su scala moderata.

## <a name="configure-users-for-meetings-first"></a>Configurare prima gli utenti per le riunioni

Dopo aver concesso in licenza gli utenti e preparato l'organizzazione Teams riunioni, è il momento di abilitare prima gli utenti per Riunioni. Abbiamo reso tutto facile: un'unica impostazione farà tutto!

Tutte le funzionalità e le esperienze utente in Meetings [](teams-client-experience-and-conformance-to-coexistence-modes.md) First, tra cui la configurazione del client Teams e la conformità automatica dell'esperienza utente, il servizio di migrazione riunioni e le funzionalità better together, vengono configurate concedendo all'utente (o al gruppo di utenti o al tenant predefinito) la modalità di coesistenza [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) nell'interfaccia di amministrazione di [Microsoft Teams](manage-teams-in-modern-portal.md) o usando [PowerShel l](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).

![Screenshot delle impostazioni di amministrazione per abilitare Riunioni per prime.](media/teams-meeting-admin-settings.png)

Facoltativamente, è consigliabile nascondere l'applicazione Teams e canali dal riquadro di spostamento sinistro del client Teams degli utenti per concentrare ulteriormente la propria esperienza sulle riunioni, che possono essere ottenute usando il criterio Configurazione [app.](teams-app-setup-policies.md)

## <a name="reporting-and-call-analytics"></a>Creazione di report e analisi delle chiamate

Report e Call Analytics per Teams riunioni in Riunioni First rimangono invariate rispetto alle altre modalità.

## <a name="related-links"></a>Collegamenti correlati

Dopo aver esaminato questo articolo, è consigliabile [](migration-interop-guidance-for-teams-with-skype.md)consultare Scegliere il percorso di [aggiornamento,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)le indicazioni per la migrazione e l'interoperabilità [e](coexistence-chat-calls-presence.md) la coesistenza con Skype for Business per altri dettagli.
