---
title: Condurre un progetto pilota per l'utente per valutare e testare il funzionamento di Microsoft Teams nell'organizzazione
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Indicazioni per avviare una Microsoft Teams pilota per esplorare tutte le Teams in grado di offrire all'organizzazione, mentre si continua a usare Skype for Business
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823225"
---
# <a name="conduct-a-user-pilot"></a>Condurre un progetto pilota per gli utenti

![Diagramma percorso di aggiornamento, con l'evidenziazione di distribuzione e implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento e condivide informazioni dettagliate per l'esecuzione di un progetto pilota efficace. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)
- [Coesistenza e interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Scelta del percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)

Distribuendo nuove tecnologie, l'organizzazione può realizzare vantaggi aziendali come il risparmio sui costi, la conformità alla sicurezza, la soddisfazione dei dipendenti e l'efficienza operativa, ma può anche influire sulla produttività e sull'infrastruttura organizzativa degli utenti (la rete). Prima di abilitare le nuove tecnologie in tutta l'organizzazione, eseguire un progetto pilota per utenti formali. Proprio come si dipinge una piccola macchia di colore su una parete prima di dipingere l'intera stanza, è necessario testare un'implementazione su scala più piccola conducendo un progetto pilota per convalidare la conformità tecnica e dell'utente, identificare e mitigare i problemi e contribuire a garantire un'implementazione a livello di organizzazione di successo.

Per ottenere i risultati più realistici, il progetto pilota dovrebbe coinvolgere gli utenti effettivi, simulare il modo in cui comunicano e collaborano e verificare sia le esperienze tecniche che quelle degli utenti. Se l'organizzazione prevede di eseguire Skype for Business e Teams affiancati, eseguire l'aggiornamento a Teams in futuro o distribuire nuove funzionalità, ad esempio chiamate o conferenze, un progetto pilota può aiutare a identificare il percorso giusto per l'organizzazione. A volte considerata la fase 1 di un'implementazione, la distribuzione pilota ideale sfrutta la preparazione già avviata e implementa il piano definito con un gruppo di utenti mirato.

|&nbsp; | &nbsp;|
|---|---|
| ![Icona che descrive un punto decisionale.](media/audio_conferencing_image7.png) <br/>Punto di decisione|<ul><li>Come si userà un progetto pilota per informare la direzione del progetto?</li></ul> |
| ![Icona che descrive il passaggio successivo.](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Usare le indicazioni seguenti per progettare ed eseguire il progetto pilota formale.</li></ul>|

> [!Tip]
> Usare le [risorse pilota](https://aka.ms/UpgradeSuccessKit) di esempio per progettare le comunicazioni, il piano di test e il sondaggio sul feedback.

## <a name="1-outline-pilot-logistics"></a>1. Delineare la logistica del pilota

Un progetto pilota di successo ha definito le date di inizio e di fine e [ha definito chiaramente gli obiettivi](upgrade-define-project-scope.md#project-goals) per misurare il successo. Questi obiettivi dovrebbero essere allineati all'ambito del progetto più ampio, come documentato al momento della [definizione dell'ambito del progetto](upgrade-define-project-scope.md), e verranno usati per informare il percorso futuro al raggiungimento della fine del progetto pilota. È anche consigliabile assicurarsi di aver incluso gli stakeholder giusti per la durata del progetto. È consigliabile concedere un tempo sufficiente per eseguire il progetto pilota e valutarne l'impatto: è consigliabile impostare un minimo di 30 giorni.

Iniziare in piccolo e aggiungere al progetto pilota in base alle esigenze, aggiungendo carichi di lavoro, funzionalità o altri utenti, consentendo di valutare i risultati e modificare il progetto pilota durante l'iterazione. È anche possibile scegliere di eseguire le distribuzioni pilota successive quando vengono rilasciate nuove funzionalità di Teams in base alla roadmap.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Selezionare i partecipanti pilota e scenari di test

Una delle attività più importanti della pianificazione pilota è la selezione accurata dei partecipanti. Tenere presente che Teams è ottimizzata per il lavoro in team, quindi assicurarsi di selezionare i partecipanti pilota non solo in base ai ruoli o ai personaggi, ma anche in base al progetto e al lavoro tra team. Un ottimo punto di partenza è chiedere agli stakeholder e ai responsabili di reparto progetti reali che è possibile convalidare in Teams. Un esempio di progetto basato sui ruoli potrebbe essere l'uso di Teams con l'organizzazione di vendita per garantire che i rappresentanti di campo possano accedere facilmente alle risorse necessarie e condividere informazioni con altri membri del campo. Un esempio di lavoro basato su progetto potrebbe essere il coordinamento di un evento di lancio di un prodotto con i team di marketing, formazione, relazioni pubbliche e pianificazione eventi. Indipendentemente dagli scenari selezionati, il progetto pilota dovrebbe essere esteso alle persone chiave dell'IT, della formazione e del supporto tecnico, in modo da poter convalidare completamente la soluzione ottimizzando al contempo le risorse di gestione dei progetti.

> [!Tip]
> Quando si seleziona il Teams partecipanti al gruppo pilota, assicurarsi di includere i principali utenti di Skype for Business. Contattare gli utenti per sapere come usano Skype for Business oggi stesso, quindi creare un piano di test per verificare che Teams in grado di soddisfare le esigenze attuali.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Progettare il piano di test e il sondaggio di feedback

Per un'esperienza pilota di successo, offrire ai partecipanti attività chiaramente definite da completare insieme a un modo per condividere il proprio feedback. Raggruppare le attività per offrire scenari reali agli utenti, dimostrando pertinenza alle loro attività quotidiane. Consentire ai casi d'uso definiti in [Valutare la conformità alle modifiche dell'organizzazione](./upgrade-org-change-readiness.md) di guidare il piano di test.

È possibile che l'organizzazione scelga di eseguire una distribuzione pilota di tutte le funzionalità contemporaneamente o di usare un approccio graduale, ad esempio prima la collaborazione pilota, poi le riunioni, quindi la chat e le chiamate. Assicurarsi di avere un canale di feedback aperto per tenere traccia dello stato di avanzamento e misurare i risultati. Utilizzare un sondaggio predefinito come modo semplice per acquisire e valutare i risultati pilota; la progettazione del sondaggio deve essere basata sugli scenari e sulle funzionalità del piano di test.

## <a name="4-create-your-communications-plan"></a>4. Creare il piano di comunicazione

È fondamentale per il successo del progetto pilota educare i partecipanti pilota su ciò che accade, quando, perché e cosa ci si aspetta da loro. Per aumentare l'entusiasmo e la massima partecipazione, assicurarsi di includere la messaggistica di valore dell'utente oltre ai collegamenti alla formazione e al supporto in cui gli utenti possono ottenere informazioni aggiuntive man mano che avanzano nel corso del progetto pilota. Ecco alcune risorse di esempio per iniziare a usare il piano di comunicazione pilota:

- [Risorse pilota](https://aka.ms/UpgradeSuccessKit), inclusi modelli di posta elettronica e domande di esempio sul sondaggio sul feedback
- [Passare a Teams da Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), una guida introduttiva progettata per aiutare Skype for Business gli utenti a iniziare a usare Teams

## <a name="5-conduct-your-pilot"></a>5. Condurre il progetto pilota

Con tutta la logistica in atto, ora sei pronto per iniziare il tuo pilota. La conduzione del progetto pilota include la comunicazione con gli utenti, il monitoraggio della rete e dell'utilizzo per garantire che le prestazioni di rete e la qualità delle chiamate rimangano integri, raccogliendo feedback dai partecipanti e rivedendo i ticket helpdesk per le domande relative a Teams.

### <a name="tips-for-pilot-success"></a>Suggerimenti per il successo pilota

I suggerimenti seguenti possono contribuire a garantire il successo del progetto pilota:

- Prima di iniziare il progetto pilota, verificare che tutti i partecipanti pilota siano abilitati per la [modalità di coesistenza] appropriata
- (https://aka.ms/SkypeToTeams-SetCoexistence) vuoi convalidare.
- Ogni settimana, nel corso del progetto pilota, si incontrano con gli stakeholder del progetto per esaminare il feedback degli utenti, i dati sull'utilizzo, i dati di rete e i ticket helpdesk per garantire il corretto funzionamento del progetto pilota. Apportare le modifiche necessarie.

### <a name="suggested-timeline"></a>Sequenza temporale suggerita

Ecco una sequenza temporale suggerita per un progetto pilota di 30 giorni:

- Una settimana prima del kickoff pilota: inviare la comunicazione iniziale agli utenti pilota.
- Giorno 1: invia la comunicazione preliminare agli utenti pilota.
- Giorno 7: Organizzare la prima riunione settimanale del checkpoint del team di progetto.
- Giorno 14: invia comunicazioni di livello intermedio agli utenti pilota, con una riunione settimanale di checkpoint del team di progetto.
- Giorno 21: Organizzare una riunione settimanale di checkpoint del team di progetto.
- Giorno 30: inviare la comunicazione finale agli utenti pilota.
- Giorni 31-45: valutare i risultati pilota e pianificare i passaggi successivi.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Valutare le attività di apprendimento e valutare il piano di avanzamento

Una volta completato il progetto pilota, è il momento di raccogliere tutti i sondaggi di feedback, le statistiche di rete finali e i ticket di supporto per l'analisi rispetto ai propri obiettivi e determinare se implementare il piano di avanzamento. È possibile che l'organizzazione sia pronta per un'ampia distribuzione o che si voglia estendere il progetto pilota a più utenti oppure rivisitare la distribuzione pilota in un secondo momento dopo aver attenuato i problemi identificati. Tenere presente che il progetto pilota è un ottimo modo per prevedere i risultati tecnici e degli utenti in un ambiente _controllato_ ; attenzione a saltare troppo rapidamente.

Se i risultati indicano:

- **Gli obiettivi pilota (ad esempio la soddisfazione degli utenti e la qualità della rete) sono stati raggiunti**, quindi si dovrebbe essere pronti a procedere con la fase successiva dell'implementazione. A seconda degli obiettivi del progetto, questo potrebbe essere uno dei seguenti:
  - Estensione del progetto pilota ad altri partecipanti
  - [Abilitazione di Teams insieme a Skype for Business (modalità **Isole**) per alcune o tutte le organizzazioni](./setting-your-coexistence-and-upgrade-settings.md)
  - [Aggiornamento degli utenti da Skype for Business a Teams (**solo modalità Teams**) per alcuni o tutti gli utenti dell'organizzazione](./setting-your-coexistence-and-upgrade-settings.md)
- **Il progetto pilota non ha raggiunto i risultati desiderati (ad esempio la soddisfazione degli utenti e la qualità della rete),** ha preso del tempo per apportare le modifiche appropriate al piano e rivedere il progetto pilota.

> [!Tip]
> Arruola i partecipanti pilota come campioni peer per aiutare a evangelizzare e aggiungere nuovi utenti a Teams. I campioni peer possono comunicare facilmente con altri utenti, condividere le proprie esperienze e esperienze e offrire supporto e indicazioni ai colleghi. Altre informazioni sui [campioni](
https://adoption.microsoft.com/become-a-champion/) e su come usarli all'interno della propria implementazione.