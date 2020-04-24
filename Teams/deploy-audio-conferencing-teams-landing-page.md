---
title: Configurare le impostazioni di audioconferenza - Microsoft Teams
ms.reviewer: ''
description: Usare queste risorse per la distribuzione per semplificare l'implementazione del servizio di audioconferenza nell'ambito del carico di lavoro delle riunioni in Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c706fdde4f9634cc67b334cf19d0e9d3325f6ec8
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776581"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Scopri come distribuire i servizi di audioconferenza in Microsoft Teams

Audioconferenza consente di partecipare a una riunione di Teams da un normale telefono e di chiamare un numero di telefono dall'interno di una riunione. Verificare di aver esaminato l'articolo sull'[implementazione delle riunioni](deploy-meetings-microsoft-teams-landing-page.md) come parte della distribuzione del servizio di audioconferenza nell'organizzazione.

## <a name="audio-conferencing-deployment-decisions"></a>Decisioni per la distribuzione dell'audioconferenza

Questo articolo è utile per decidere se modificare una o più impostazioni predefinite per l'audioconferenza in base al profilo o ai requisiti dell'organizzazione e illustra la procedura per ogni modifica. Le impostazioni sono state suddivise in due gruppi, a partire dal set di base di [modifiche più probabili](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions) che può essere utile configurare in base alle esigenze dell'organizzazione.

È necessario soltanto configurare l'audioconferenza solo per gli utenti che intendono programmare o condurre riunioni. Le persone che partecipano alla riunione tramite telefono non hanno bisogno di altre impostazioni o che venga loro assegnata una licenza. Accedere alle riunioni tramite telefono è molto utile per gli utenti che sono in viaggio e non possono partecipare a una riunione usando l'app Skype for Business o Teams sul laptop o dispositivo mobile. 


## <a name="audio-conferencing-prerequisites"></a>Prerequisiti per l'audioconferenza 

Prima di implementare l'audioconferenza per Teams, considerare quanto segue:

|Chiedersi|Azione |
|------------|-------|
|Il servizio di audioconferenza è disponibile per il paese/area geografica?|Per sapere se l'audioconferenza è disponibile nel paese/area geografica di interesse, vedere [Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|Gli utenti hanno la licenza appropriata per l'audioconferenza di Teams?|Le licenze per Audioconferenza sono disponibili come parte di un abbonamento a Office 365 E5 o come componente aggiuntivo per un abbonamento a Microsoft 365 Business Standard, E1 o E3. <ul><li>Per ottenere e assegnare licenze, vedere [Provare o acquistare le audioconferenze in Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) e [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Per altre informazioni, vedere [Gestione delle licenze per i componenti aggiuntivi di Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). </li><li>Per informazioni sulle funzionalità cloud incluse in ogni piano di Office 365, vedere gli articoli sulle [Opzioni di licenza basate sul tuo piano](teams-add-on-licensing/office-365-business-premium.md).</li></ul>|
|È necessario acquistare credito per la comunicazione per gli utenti a cui sono state assegnate licenze per Audioconferenza?|Per altre informazioni, vedere [Che cos'è Credito per la comunicazione?](what-are-communications-credits.md) e quindi leggere la sezione [Credito per la comunicazione](#communications-credits) più avanti.|
|||


## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Quando i prerequisiti di Audioconferenza sono soddisfatti, completare le attività seguenti per configurare l'audioconferenza per gli utenti.


### <a name="teams-administrators"></a>Amministratori di Teams

Teams include un set di ruoli di amministratore personalizzati che è possibile usare per gestire la soluzione per l'organizzazione. I ruoli forniscono varie funzionalità agli amministratori. 

| Chiedersi | Azione |
|--------------|--------|
|A chi sarà assegnato il ruolo di amministratore delle comunicazioni di Teams?|Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).|
|A chi sarà assegnato il ruolo di tecnico del supporto delle comunicazioni di Teams?|Per assegnare i ruoli amministrativi, vedere [Assegnazione di ruoli di amministratore e senza privilegi di amministratore agli utenti con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A chi sarà assegnato il ruolo di specialista del supporto delle comunicazioni di Teams?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Bridge di conferenza e numeri di telefono

I bridge di conferenza consentono agli utenti di comporre accedere alle riunioni tramite un telefono. È possibile usare le impostazioni predefinite per un bridge di conferenza o modificare i numeri di telefono (numeri verdi e a pagamento) e altre impostazioni, come il PIN o le lingue usate.

Per altre informazioni, vedere [Audioconferenza in Office 365](audio-conferencing-in-office-365.md).

|Chiedersi|Azione |
|------------|-------|
|È necessario aggiungere nuovi numeri per il bridge di conferenza?| Per aggiungere nuovi numeri, vedere [Recuperare numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).|
|È necessario modificare le impostazioni del bridge?|Per modificare le impostazioni del bridge, vedere [Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).|
|È necessario trasferire i numeri di telefono per usarli con il servizio di audioconferenza?|Per informazioni sulla portabilità dei numeri di telefono, vedere [Trasferire numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||


### <a name="default-and-alternate-languages"></a>Lingue predefinite e alternative

Il servizio di audioconferenza di Teams consente di configurare le lingue predefinite e alternative per un bridge di conferenza.

|Chiedersi|Azione |
|------------|-------|
| Quali lingue scegliere per i messaggi di saluto dell'operatore automatico? | Per scegliere le lingue, vedere [Impostare le lingue degli operatori automatici per le audioconferenze](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="conferencing-bridge-settings"></a>Impostazioni del bridge di conferenza 

Dopo aver impostato il bridge di conferenza, incluse le lingue predefinite e alternative, verificare che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN, siano quelle desiderate. Se non lo sono, è possibile modificarle. 

|Chiedersi|Azione |
|------------|-------|
| I partecipanti sentiranno una notifica quando un utente accede o esce da una riunione? | Per modificare queste impostazioni, vedere [Modificare le impostazioni per un bridge per audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Quanto deve essere lungo il PIN usato dall'organizzatore di una riunione per avviare la riunione?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Impostazioni dei numeri di telefono per l'accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato il bridge del servizio di audioconferenza, è necessario impostare i numeri verdi o a pagamento che verranno usati dagli utenti che conducono le riunioni.

|Chiedersi|Azione |
|------------|-------|
| Quali numeri del bridge di conferenza verranno assegnati a ogni utente che conduce riunioni? | Per assegnare un numero di telefono per l'accesso esterno a un utente, vedere [Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Credito per la comunicazione

Per fornire numeri verdi per il bridge di conferenza e per supportare le chiamate in uscita verso numeri di telefono internazionali, è necessario configurare Credito per la comunicazione per l'organizzazione. Per altre informazioni, vedere [Che cos'è Credito per la comunicazione?](what-are-communications-credits.md).

|Chiedersi|Azione |
|------------|-------|
|Credito per la comunicazione è necessario per l'implementazione del servizio di audioconferenza? |Per determinare se è necessario configurare Credito per la comunicazione, vedere [Configurare Credito per la comunicazione per l'organizzazione](set-up-communications-credits-for-your-organization.md).|
|In caso affermativo, quanto credito occorre acquistare?|Per determinare la quantità di credito da acquistare, vedere [Importo consigliato per i fondi](what-are-communications-credits.md#recommended-funding-amounts).|
|Si vuole configurare un importo per l'autoricarica?|Per configurare un importo per l'autoricarica, vedere [Configurare Credito per la comunicazione per la propria organizzazione](set-up-communications-credits-for-your-organization.md).|
|||



## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Può essere utile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="outbound-calling-restriction-policies"></a>Criteri di restrizione delle chiamata in uscita 

Gli amministratori possono usare i controlli per le chiamate in uscita per limitare il tipo di audioconferenze e di chiamate PSTN che possono essere eseguite dagli utenti nell'organizzazione.

|Chiedersi|Azione |
|------------|-------|
| Si limiterà il tipo di chiamate in uscita consentite? | Per limitare le chiamate in uscita, vedere [Criteri di restrizione delle chiamate in uscita per audioconferenze e chiamate PSTN utente](outbound-calling-restriction-policies.md).|
|||


### <a name="dial-plans"></a>Dial plan

Un dial plan nell'ambito del Sistema telefonico di Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E.164) per l'autorizzazione delle chiamate e l'instradamento delle chiamate.

Per altre informazioni sui dial plan, vedere [Che cosa sono i dial plan?](what-are-dial-plans.md)

|Chiedersi|Azione |
|------------|-------|
|L'organizzazione ha bisogno di un dial plan personalizzato?|Per determinare se è necessario un dial plan personalizzato, vedere [Pianificazione dei dial plan del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|Quali utenti devono avere un dial plan personalizzato e quale dial plan del tenant occorre assegnare a ogni utente?|Per aggiungere utenti a un dial plan personalizzato con PowerShell, vedere [Creare e gestire i dial plan](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Risoluzione dei problemi di qualità per riunioni e chiamate 

Teams offre due modi per monitorare e risolvere i problemi di qualità delle chiamate: Analisi delle chiamate e Dashboard Qualità della chiamata. Analisi delle chiamate mostra informazioni dettagliate sui dispositivi, le reti e la connettività relativamente alle specifiche chiamate e riunioni di ciascun utente. Analisi delle chiamate è progettato per aiutare amministratori e agenti dell'help desk a risolvere i problemi di qualità per specifiche chiamate, mentre Dashboard Qualità della chiamata è progettato per aiutare gli amministratori e i tecnici di rete a ottimizzare una rete. Dashboard Qualità della chiamata non è focalizzato sui singoli utenti, bensì sulle informazioni aggregate di un'intera organizzazione di Teams. 

|Chiedersi|Azione |
|------------|-------|
| Chi sarà responsabile per il monitoraggio e la risoluzione dei problemi di qualità delle chiamate? | Per informazioni sui livelli di autorizzazione necessari per risolvere i problemi di qualità delle chiamate, vedere [Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).|
|||


## <a name="next-steps"></a>Passaggi successivi
- [Favorire l'adozione](adopt-microsoft-teams-landing-page.md) dell'audioconferenza nell'organizzazione.
- [Implementare Cloud Voice](cloud-voice-landing-page.md)
- Includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungere ulteriori [app, bot e connettori](deploy-apps-microsoft-teams-landing-page.md) per incentivare l'adozione di Teams.
