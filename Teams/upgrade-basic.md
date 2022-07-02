---
title: Elenco di controllo per l'aggiornamento| Aggiornamento da Skype Business a Teams | Passaggi di base
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Seguire questo piano d'azione accelerato in dieci passaggi per passare da una configurazione di base Skype for Business alla configurazione di Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aab5ff20ef241b3e80eaf7909fb960eff94bfbe8
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606025"
---
# <a name="upgrade-basic"></a>Aggiornamento di base

<a name="about-upgrade-basic"></a>

Progettato per le organizzazioni più piccole o per quelle che usano Skype for Business Online solo per la messaggistica istantanea (chat) e le riunioni, l'elenco di controllo Aggiorna base è un piano di azione accelerata che include le attività principali consigliate e le risorse associate per implementare correttamente il passaggio da Skype for Business a Teams.

Questi dieci semplici passaggi forniscono tutto il necessario per un aggiornamento riuscito. Sono progettati per essere completati in circa 30-45 giorni, ma è consigliabile modificare le date di completamento delle attività in base all'aggiornamento pianificare dell'organizzazione.

> [!IMPORTANT]
> Skype for Business Online è stato ritirato il 31 luglio 2021. Per massimizzare la realizzazione dei vantaggi e garantire che la tua organizzazione abbia il tempo giusto per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio verso Microsoft Teams.

Cosa succede a Skype for Business dopo l'aggiornamento? Dopo l'aggiornamento degli utenti a Teams (modalità **Solo Teams**):

- Il client Skype for Business è disabilitato e tutte le chat e le chiamate passano a Teams. Tieni presente che il client non verrà disinstallato sul desktop.
- Tutte le riunioni Skype for Business pianificate prima del lavoro di aggiornamento come previsto, ma tutte le nuove riunioni sono pianificate in Teams. Il plug-in Skype for Business non sarà più disponibile in Outlook. 
- Se gli utenti provano ad accedere a Skype for Business, ricevono una notifica dal client che indica che è stato eseguito l'aggiornamento a Teams.
- Gli utenti devono disinstallare manualmente il client Skype for Business nei propri dispositivi mobili.

Vedi le nostre [domande frequenti](./faq-journey.yml) per altre domande sul tuo aggiornamento.

Non si ha familiarità con Teams? [Informazioni su come Teams](https://products.office.com/microsoft-teams/group-chat-software) riunisce conversazioni, riunioni, file, app di Office e integrazioni di terze parti, fornendo un unico hub per il lavoro in team in Microsoft 365 e Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Passaggio 1. Informare gli stakeholder principali

*(da quattro a sei settimane prima dell'aggiornamento)*

I leader senior sono responsabili del successo dell'azienda; essere sicuri di tenerli a conoscenza dei cambiamenti tecnologici. Poiché è possibile che non tutti gli utenti hanno ricevuto o letto la notifica sull'idoneità dell'aggiornamento, è necessario informare gli stakeholder (ad esempio CEO, professionisti IT, marketing e lead helpdesk) prima di iniziare a pianificare l'aggiornamento.

**Risorse:**

- [Messaggio di posta elettronica di esempio: comunicazione con gli stakeholder](upgrade-emails-surveys.md#step-1-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Passaggio 2. Preparare l'organizzazione per Teams

*(da quattro a sei settimane prima dell'aggiornamento)*

Teams offre funzionalità di Skype for Business compatibili, come messaggistica istantanea (chat) e riunioni, ma può anche fare molto di più. Come vero hub per il lavoro in team, Teams consente ai gruppi di lavoro di gestire progetti, file, conversazioni e app in un'unica posizione. Per impostazione predefinita, Teams è attivato per tutte le organizzazioni. Decidere in che modo l'organizzazione userà Teams e configurare l'ambiente per il successo. 

> [!Note]
> In quanto cliente Skype for Business esistente, è probabile che l'infrastruttura di rete corrente sia già configurata per Teams. A questo scopo, è possibile seguire le indicazioni "Pianificazione tecnica completa" riportate di seguito (facoltativo).

**Risorse:**

- [Panoramica di Teams](Teams-overview.md)
- [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Passaggio 3. Conoscere gli utenti Skype for Business

*(circa quattro settimane prima dell'aggiornamento)*

Gli utenti profondamente adottati su Skype for Business potrebbero richiedere più tempo o assistenza per passare a Teams. Prenditi del tempo per rivedere l'attuale utilizzo di Skype for Business per identificare i tuoi principali utenti che hanno bisogno di ulteriore supporto e per stabilire una linea di base per l'utilizzo di cui puoi tenere traccia rispetto ai numeri dopo l'aggiornamento.

**Risorse:**

- [Report di Microsoft 365 nell'interfaccia di amministrazione](/microsoft-365/admin/activity-reports/activity-reports)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 4. Avvisare gli utenti che eseguono l'aggiornamento da Skype for Business a Teams

*(circa due o tre settimane prima dell'aggiornamento)*

Fornire un ampio preavviso agli utenti darà loro il tempo di familiarizzare con Teams senza influire negativamente sulla loro produttività, ottenendo un'esperienza utente più positiva. Inviare una comunicazione per comunicare cosa cambia, perché cambia e come prepararsi.

> [!Note]
> Se necessario, al momento è possibile abilitare Teams per gli utenti tramite il interfaccia di amministrazione di Microsoft 365.

**Risorse:**

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Messaggio di posta elettronica di esempio: annuncio agli utenti su Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Passaggio 5. Attivare la notifica di aggiornamento dell'utente

*(circa una settimana prima dell'aggiornamento)*

Mantieni la spinta all'aggiornamento abilitando la notifica di aggiornamento dell'utente tramite il portale di amministrazione, fornendo un avviso visivo nel client Skype for Business che indica che gli utenti vengono aggiornati da Skype for Business a Teams.

**Risorse:**

- [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 6. Ricordare agli utenti che effettueranno l'aggiornamento da Skype for Business a Teams

*(circa cinque giorni prima dell'aggiornamento)*

Gli utenti sono impegnati con le loro responsabilità quotidiane. Ricordare loro l'aggiornamento in sospeso aiuta a ricordare di eseguire i passaggi necessari per prepararsi per Teams. Questo è il momento perfetto per ricordare agli utenti la formazione disponibile e come iniziare a usare Teams.

**Risorse:**

- [E-mail di esempio: ricordare agli utenti di iniziare a usare Teams](upgrade-emails-surveys.md#step-6-email)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Passaggio 7. Aggiorna gli utenti a Teams!

*(Giorno aggiornamento)*

Oggi la tua organizzazione esegue ufficialmente l'aggiornamento a Teams come soluzione di comunicazione e collaborazione. Nell'interfaccia di amministrazione di Microsoft Teams attivare l'aggiornamento impostando la modalità di coesistenza **su Solo Teams**. Nell'interfaccia di amministrazione passare a **Teams** >  **Impostazioni di aggiornamento di Teams**. Gli utenti riceveranno una notifica nel client Skype for Business che indica che sono stati aggiornati a Teams.

Si consiglia di inviare un messaggio di posta elettronica di benvenuto a Teams dopo aver aggiornato tutti gli utenti.

**Risorse:**

- [Configurare le impostazioni di aggiornamento e coesistenza](setting-your-coexistence-and-upgrade-settings.md)
- [E-mail di esempio: benvenuto in Teams per gli utenti](upgrade-emails-surveys.md#step-7-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Passaggio 8. Monitorare l'utilizzo di Teams rispetto alla previsione

*(circa una o due settimane dopo l'aggiornamento)*

L'adattamento a una nuova tecnologia può richiedere del tempo. Controllare l'utilizzo per verificare che gli utenti usino Teams allo stesso livello, o superiore, di Skype for Business. Controlla con gli utenti che non usano Teams ai livelli previsti.

**Risorse:**

- [Visualizzare i dati di utilizzo](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Passaggio 9. Misurare la soddisfazione degli utenti

*(circa una o due settimane dopo l'aggiornamento)*

La soddisfazione dei dipendenti può influenzare la produttività, la conservazione e, in ultima analisi, i risultati aziendali. Contattare gli utenti per valutare il sentiment degli utenti in merito all'aggiornamento e alla loro soddisfazione per Teams.

**Risorse:**

- [E-mail di esempio: archiviare con gli utenti](upgrade-emails-surveys.md#step-9-email), oltre ai [sondaggi degli utenti](upgrade-emails-surveys.md#step-9-surveys)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Passaggio 10. Ottimizzare il ROI con Teams

*(In corso)*

Dopo che gli utenti hanno familiarità con la messaggistica istantanea (chat) e le riunioni in Teams, incoraggiali a estendere il loro caso d'uso usando la collaborazione di Teams e l'integrazione delle app, ottimizzando veramente la loro nuova soluzione e massimizzando il ritorno sul tuo investimento.

**Risorse:**

- [E-mail di esempio: incoraggia gli utenti a esplorare ulteriormente Teams](upgrade-emails-surveys.md#step-10-email)

[Torna all'inizio](#about-upgrade-basic)
