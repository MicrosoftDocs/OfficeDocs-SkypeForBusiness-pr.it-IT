---
title: Elenco di controllo per l'aggiornamento| Aggiornamento da Skype Business a Teams | Passaggi di base
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Segui questo piano d'azione accelerato in dieci passaggi per passare da una configurazione di base di Skype for Business alla configurazione di Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 37cc9f3940eb08a4df092042c016b194b01c64e6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809086"
---
# <a name="upgrade-basic"></a>Aggiornamento di base

<a name="about-upgrade-basic"></a>

Progettato per le organizzazioni più piccole o per gli utenti che usano Skype for Business online solo per messaggistica istantanea (chat) e riunioni, l'elenco di controllo di base per l'aggiornamento è un piano d'azione accelerato che include attività di base e consigliate e risorse associate per implementare con successo un passaggio da Skype for Business a Teams.

Questi dieci semplici passaggi forniscono tutto il necessario per eseguire correttamente l'aggiornamento. Sono progettati per essere completati in circa 30-45 giorni, ma è consigliabile modificare le date di completamento delle attività in base alla programmazione di aggiornamento dell'organizzazione.

> [!IMPORTANT]
> Skype for Business online verrà ritirato il 31 luglio 2021. Successivamente, il servizio Skype for Business online non sarà più accessibile o supportato. Per ottimizzare la realizzazione dei vantaggi e garantire alla tua organizzazione il tempo necessario per implementare il tuo aggiornamento, ti consigliamo di iniziare oggi stesso il tuo percorso verso Microsoft Teams.

Cosa succede a Skype for Business dopo l'aggiornamento? Dopo l'aggiornamento degli utenti a Teams (modalità **Solo Teams**):

- Il client Skype for Business viene disabilitato e tutte le chat e le chiamate vengono effettuate in Teams. Tieni presente che questa operazione non disinstallerà il client sui loro desktop.
- Tutte le riunioni di Skype for Business pianificate prima dell'aggiornamento funzionano come previsto, ma tutte le nuove riunioni sono pianificate in Teams. Il plug-in di Skype for Business non sarà più disponibile in Outlook. 
- Se gli utenti provano ad accedere a Skype for Business, ottengono una notifica dal loro client che è stato aggiornato a Teams.
- Gli utenti devono disinstallare manualmente il client Skype for Business sui propri dispositivi mobili.

Per altre [domande sull'aggiornamento,](https://aka.ms/SkypeToTeams-FAQ) vedere le domande frequenti.

Non si ha familiarità con Teams? [Scopri](https://products.office.com/microsoft-teams/group-chat-software) come Teams riunisce conversazioni, riunioni, file, app di Office e integrazioni di terze parti, fornendo un unico hub per il lavoro in team in Microsoft 365 e Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Passaggio 1. Inviare una notifica alle principali parti interessate

*(da quattro a sei settimane prima dell'aggiornamento)*

I responsabili senior sono responsabili per il successo dell'azienda; assicurati di mantenerle sempre a conoscere i cambiamenti della tecnologia. Poiché è possibile che non tutti gli utenti hanno ricevuto o letto la notifica sull'idoneità all'aggiornamento, è necessario informare gli stakeholder (ad esempio CEO, professionisti IT, marketing e lead helpdesk) prima di iniziare a pianificare l'aggiornamento.

**Risorse:**

- [Esempio di messaggio di posta elettronica: comunicazione con gli stakeholder](upgrade-emails-surveys.md#step-1-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Passaggio 2. Preparare l'organizzazione per Teams

*(da quattro a sei settimane prima dell'aggiornamento)*

Teams offre funzionalità compatibili con Skype for Business, come la messaggistica istantanea (chat) e le riunioni, ma può anche fare molto di più. Come vero hub per il lavoro in team, Teams consente ai gruppi di lavoro di gestire progetti, file, conversazioni e app in un'unica posizione. Per impostazione predefinita, Teams è attivato per tutte le organizzazioni. Decidi in che modo la tua organizzazione userà Teams e configura il tuo ambiente per il successo. 

> [!Note]
> Come cliente esistente di Skype for Business, l'attuale infrastruttura di rete è probabilmente già configurata per Teams. Per confermare, è possibile seguire le istruzioni di "Pianificazione tecnica completa" collegate di seguito (facoltativo).

**Risorse:**

- [Panoramica di Teams](Teams-overview.md)
- [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Passaggio 3. Conoscere gli utenti di Skype for Business

*(circa quattro settimane prima dell'aggiornamento)*

Gli utenti che sono stati adottato in modo approfondito in Skype for Business potrebbero richiedere più tempo o assistenza per passare a Teams. Prenditi del tempo per esaminare l'utilizzo corrente di Skype for Business per identificare i tuoi principali utenti che hanno bisogno di ulteriore supporto e per stabilire una linea di base di utilizzo di cui tenere traccia rispetto ai numeri dopo l'aggiornamento.

**Risorse:**

- [Report di Microsoft 365 nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 4. Informare gli utenti dell'aggiornamento da Skype for Business a Teams

*(da due a tre settimane prima dell'aggiornamento)*

Se si fornisce un ampio preavviso agli utenti, si avrà il tempo di acquisire familiarità con Teams senza influire negativamente sulla loro produttività, con conseguente un'esperienza utente più positiva. Invia una comunicazione per comunicare loro cosa sta cambiando, perché sta cambiando e come possono prepararsi.

> [!Note]
> Se necessario, al momento è possibile abilitare Teams per gli utenti tramite l'interfaccia di amministrazione di Microsoft 365.

**Risorse:**

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Esempio di messaggio di posta elettronica: annuncio agli utenti su Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Passaggio 5. Attivare la notifica sull'aggiornamento dell'utente

*(circa una settimana prima dell'aggiornamento)*

Mantenere l'interesse per l'aggiornamento abilitando la notifica sull'aggiornamento degli utenti tramite il portale di amministrazione, inviando un avviso visivo nel client Skype for Business che indica che è in corso l'aggiornamento degli utenti da Skype for Business a Teams.

**Risorse:**

- [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 6. Ricorda ai tuoi utenti che eserciteranno l'aggiornamento da Skype for Business a Teams

*(circa cinque giorni prima dell'aggiornamento)*

Gli utenti sono impegnati con le loro responsabilità quotidiane. Ricordando loro l'aggiornamento in sospeso ci si assicura che esercitino i passaggi necessari per prepararsi per Teams. Questo è il momento ideale per ricordare agli utenti la formazione disponibile e come iniziare a usare Teams.

**Risorse:**

- [Messaggio di posta elettronica di esempio: ricordare agli utenti di iniziare a usare Teams](upgrade-emails-surveys.md#step-6-email)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Passaggio 7. Aggiorna gli utenti a Teams!

*(Giorno aggiornamento)*

Oggi è il giorno in cui la tua organizzazione esegue ufficialmente l'aggiornamento a Teams come soluzione di comunicazione e collaborazione. Nell'interfaccia di amministrazione di Microsoft Teams attivare l'opzione di aggiornamento impostando la modalità di coesistenza su **Solo Teams.** Nell'interfaccia di amministrazione passare a **Impostazioni a livello di organizzazione**  >  **Aggiornamento di Teams.** Gli utenti riceveranno una notifica nel client Skype for Business che indica che sono stati aggiornati a Teams.

Dopo l'aggiornamento di tutti gli utenti, è consigliabile inviare un messaggio di posta elettronica di benvenuto a Teams.

**Risorse:**

- [Configurare le impostazioni di aggiornamento e coesistenza](setting-your-coexistence-and-upgrade-settings.md)
- [Messaggio di posta elettronica di esempio: utenti di benvenuto in Teams](upgrade-emails-surveys.md#step-7-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Passaggio 8. Monitorare l'utilizzo di Teams rispetto alla previsione

*(circa una o due settimane dopo l'aggiornamento)*

L'adattamento a una nuova tecnologia può richiedere del tempo. Controlla l'utilizzo per verificare che gli utenti utilizzino Teams allo stesso livello o in più, come facevano con Skype for Business. Consulta gli utenti che non usano Teams ai livelli previsti.

**Risorse:**

- [Visualizzare i dati di utilizzo](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Passaggio 9. Misurare la soddisfazione degli utenti

*(circa una o due settimane dopo l'aggiornamento)*

La soddisfazione dei dipendenti può influire sulla produttività, sulla conservazione e, in ultima analisi, sui risultati di business. Contatta i tuoi utenti per valutare il livello di soddisfazione degli utenti riguardo all'aggiornamento e la loro soddisfazione per Teams.

**Risorse:**

- [Messaggio di posta elettronica di esempio: archiviazione con utenti](upgrade-emails-surveys.md#step-9-email)e [sondaggi utente](upgrade-emails-surveys.md#step-9-surveys)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Passaggio 10. Massimizzare il ROI con Teams

*(In corso)*

Dopo che gli utenti hanno familiarità con la messaggistica istantanea (chat) e le riunioni in Teams, incoraggiali a estendere il loro caso di utilizzo utilizzando la collaborazione di Teams e l'integrazione delle app, ottimizzando effettivamente la nuova soluzione e ottimizzando al massimo il ritorno sull'investimento.

**Risorse:**

- [Esempio di messaggio di posta elettronica: incoraggiare gli utenti a esplorare ulteriormente Teams](upgrade-emails-surveys.md#step-10-email)

[Torna all'inizio](#about-upgrade-basic)
