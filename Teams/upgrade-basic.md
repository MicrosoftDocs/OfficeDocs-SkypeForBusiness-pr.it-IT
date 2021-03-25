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
ms.openlocfilehash: d9453ad770b7ca21b5300b193cbafb932ea7645a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120527"
---
# <a name="upgrade-basic"></a>Aggiornamento di base

<a name="about-upgrade-basic"></a>

Progettato per le organizzazioni più piccole o per quelle che usano Skype for Business online solo per messaggistica istantanea (chat) e riunioni, l'elenco di controllo Di base per l'aggiornamento è un piano d'azione accelerato che include le attività di base, le attività consigliate e le risorse associate per l'implementazione di un passaggio di successo da Skype for Business a Teams.

Questi dieci semplici passaggi forniscono tutto il necessario per un aggiornamento efficace. Sono progettati per essere completati in circa 30-45 giorni, ma è consigliabile modificare le date di completamento delle attività in base alla programmazione dell'aggiornamento dell'organizzazione.

> [!IMPORTANT]
> Skype for Business online verrà ritirato il 31 luglio 2021. Dopo tale periodo, il servizio Skype for Business Online non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti consigliamo di iniziare il tuo viaggio verso Microsoft Teams oggi stesso.

Cosa succede a Skype for Business dopo l'aggiornamento? Dopo l'aggiornamento degli utenti a Teams (modalità **Solo Teams**):

- Il client Skype for Business è disabilitato e tutte le chat e le chiamate vengono effettuate in Teams. Tenere presente che non verrà disinstallato il client sul desktop.
- Tutte le riunioni Skype for Business pianificate prima dell'aggiornamento funzionano come previsto, ma tutte le nuove riunioni sono pianificate in Teams. Il plug-in skype for business non sarà più disponibile in Outlook. 
- Se gli utenti provano ad accedere a Skype for Business, ottengono una notifica dal loro client che è stato eseguito l'aggiornamento a Teams.
- Gli utenti devono disinstallare manualmente il client Skype for Business nei propri dispositivi mobili.

Consulta le nostre [domande](./faq-journey.yml) frequenti per altre domande sull'aggiornamento.

Non si ha familiarità con Teams? [Informazioni su](https://products.office.com/microsoft-teams/group-chat-software) come Teams riunisce conversazioni, riunioni, file, app di Office e integrazioni di terze parti, fornendo un unico hub per il lavoro in team in Microsoft 365 e Office 365.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>Passaggio 1. Informare i principali stakeholder

*(Da quattro a sei settimane prima dell'aggiornamento)*

I dirigenti senior sono responsabili del successo aziendale; assicurarsi di tenerli a conoscere le modifiche tecnologiche. Poiché è possibile che non tutti gli utenti hanno ricevuto o letto la notifica dell'idoneità all'aggiornamento, è necessario informare gli stakeholder (ad esempio, CEO, professionisti IT, marketing e clienti potenziali dell'helpdesk) prima di iniziare a pianificare l'aggiornamento.

**Risorse:**

- [Messaggio di posta elettronica di esempio: comunicazione con gli stakeholder](upgrade-emails-surveys.md#step-1-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>Passaggio 2. Preparare l'organizzazione per Teams

*(Da quattro a sei settimane prima dell'aggiornamento)*

Teams offre funzionalità skype for business compatibili, ad esempio messaggistica istantanea (chat) e riunioni, ma può anche fare molto di più. Come vero hub per il lavoro in team, Teams consente ai gruppi di lavoro di gestire progetti, file, conversazioni e app in un'unica posizione. Per impostazione predefinita, Teams è attivato per tutte le organizzazioni. Decidere in che modo l'organizzazione userà Teams e configurare l'ambiente per il successo. 

> [!Note]
> Come cliente skype for business esistente, è probabile che l'attuale infrastruttura di rete sia già configurata per Teams. Per confermarlo, è possibile seguire la guida "Pianificazione tecnica completa" collegata di seguito (facoltativo).

**Risorse:**

- [Panoramica di Teams](Teams-overview.md)
- [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>Passaggio 3. Conoscere gli utenti di Skype for Business

*(Circa quattro settimane prima dell'aggiornamento)*

Gli utenti che sono stati profondamente adottati su Skype for Business potrebbero avere bisogno di un po' più di tempo o assistenza per passare a Teams. Prenditi del tempo per rivedere l'attuale utilizzo di Skype for Business per identificare i tuoi utenti più bisognosi di ulteriore supporto e per stabilire una linea di base di utilizzo che puoi tenere traccia rispetto ai tuoi numeri post-aggiornamento.

**Risorse:**

- [Report di Microsoft 365 nell'interfaccia di amministrazione](/microsoft-365/admin/activity-reports/activity-reports)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 4. Informare gli utenti che verranno esercitino l'aggiornamento da Skype for Business a Teams

*(Circa due o tre settimane prima dell'aggiornamento)*

Fornendo agli utenti un ampio preavviso, avranno il tempo di familiarizzare con Teams senza influire negativamente sulla loro produttività, con conseguente esperienza utente più positiva. Invia una comunicazione per comunicare loro cosa sta cambiando, perché sta cambiando e come possono prepararsi.

> [!Note]
> Se necessario, è possibile abilitare Teams per gli utenti tramite l'interfaccia di amministrazione di Microsoft 365 in questo momento.

**Risorse:**

- [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md)
- [Esempio di messaggio di posta elettronica: annuncio agli utenti su Skype for Business](upgrade-emails-surveys.md#step-4-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>Passaggio 5. Attivare la notifica di aggiornamento dell'utente

*(Circa una settimana prima dell'aggiornamento)*

Mantenere il momento dell'aggiornamento abilitando la notifica di aggiornamento degli utenti tramite il portale di amministrazione, fornendo un avviso visivo nel client Skype for Business che indica che gli utenti vengono aggiornati da Skype for Business a Teams.

**Risorse:**

- [Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>Passaggio 6. Ricorda agli utenti che verranno esercitino l'aggiornamento da Skype for Business a Teams

*(Circa cinque giorni prima dell'aggiornamento)*

Gli utenti sono occupati con le loro responsabilità quotidiane. Ricordando loro l'aggiornamento in sospeso, si assicureranno di eseguire i passaggi necessari per prepararsi per Teams. Questo è il momento perfetto per ricordare agli utenti la formazione disponibile e come iniziare a usare Teams.

**Risorse:**

- [Messaggio di posta elettronica di esempio: ricordare agli utenti di iniziare a usare Teams](upgrade-emails-surveys.md#step-6-email)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>Passaggio 7. Aggiornare gli utenti a Teams!

*(Giorno dell'aggiornamento)*

Oggi è il giorno in cui l'organizzazione esegue ufficialmente l'aggiornamento a Teams come soluzione di comunicazione e collaborazione. Nell'interfaccia di amministrazione di Microsoft Teams attivare l'opzione di aggiornamento impostando la modalità di coesistenza su **Solo Teams.** Nell'interfaccia di amministrazione passare a **Impostazioni a livello di organizzazione**  >  **Aggiornamento di Teams**.) Gli utenti riceveranno una notifica nel client Skype for Business che indica che sono stati aggiornati a Teams.

Dopo l'aggiornamento, è consigliabile inviare un messaggio di posta elettronica di benvenuto a Teams.

**Risorse:**

- [Configurare le impostazioni di aggiornamento e coesistenza](setting-your-coexistence-and-upgrade-settings.md)
- [Messaggio di posta elettronica di esempio: benvenuto degli utenti in Teams](upgrade-emails-surveys.md#step-7-email)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>Passaggio 8. Monitorare l'utilizzo di Teams rispetto alla previsione

*(Circa una o due settimane dopo l'aggiornamento)*

L'adattamento a una nuova tecnologia può richiedere del tempo. Controlla l'utilizzo per verificare che gli utenti utilizzino Teams allo stesso livello o superiore di Skype for Business. Archivia con gli utenti che non usano Teams ai livelli previsti.

**Risorse:**

- [Visualizzare i dati di utilizzo](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[Torna all'inizio](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>Passaggio 9. Misurare la soddisfazione degli utenti

*(Circa una o due settimane dopo l'aggiornamento)*

La soddisfazione dei dipendenti può influire sulla produttività, sulla conservazione e, in ultima analisi, sui risultati aziendali. Contatta i tuoi utenti per valutare il clima di soddisfazione degli utenti per l'aggiornamento e la loro soddisfazione per Teams.

**Risorse:**

- [Esempio di messaggio di posta elettronica: archiviare con gli utenti](upgrade-emails-surveys.md#step-9-email), oltre [ai sondaggi degli utenti](upgrade-emails-surveys.md#step-9-surveys)

[Torna all'inizio](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>Passaggio 10. Massimizzare il ROI con Teams

*(In corso)*

Dopo che gli utenti hanno familiarità con la messaggistica istantanea (chat) e le riunioni in Teams, incoraggiarli a estendere il loro caso d'uso usando la collaborazione e l'integrazione delle app di Teams, ottimizzando realmente la nuova soluzione e massimizzando il ritorno sull'investimento.

**Risorse:**

- [Messaggio di posta elettronica di esempio: incoraggiare gli utenti a esplorare ulteriormente Teams](upgrade-emails-surveys.md#step-10-email)

[Torna all'inizio](#about-upgrade-basic)