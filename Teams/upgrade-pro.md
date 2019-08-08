---
title: Upgrade Pro per Microsoft Teams | Roadmap
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Usare queste indicazioni se si è in un'organizzazione di grandi dimensioni o se è stata ampiamente personalizzata la distribuzione di Skype for business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d34c111302c3e8de173b4c553589ab840495118
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236038"
---
# <a name="upgrade-pro"></a>Upgrade Pro

Progettato per organizzazioni di grandi dimensioni o con distribuzioni complesse di Skype for business (ad esempio, distribuzioni di voci ibride o cloud), aggiornare gli account Pro per un ciclo di vita di aggiornamento più lungo insieme a diversi scenari di aggiornamento, incluso l'uso di Microsoft Teams insieme a Skype for business fino a quando teams è pronto per l'organizzazione.

Segmentato in tre fasi, Aggiorna Pro copre:

|**[Pre-aggiornamento](#pre-upgrade)** |**[Aggiornamento](#upgrade)** |**[Post-aggiornamento](#post-upgrade)** |
|---|---|---|
|Realizzare il valore di Teams<ul><li>Preparare l'ambiente</li><li>Adottare team per la collaborazione, le riunioni e/o le chiamate</li><li>Pianificare l'aggiornamento di Skype for business a teams nel tempo</li></ul> |Eseguire la migrazione di utenti da Skype for business<ul><li>Notificare e preparare gli utenti</li><li>Trasferire gli utenti in modalità solo Teams</li><li>Tenere traccia dello stato di avanzamento rispetto agli obiettivi</li></ul> | Amplificare il ROI <ul><li>Monitorare l'integrità e la qualità della rete</li><li>Mantenere l'eccitazione degli utenti</li><li>Pianificare l'innovazione in teams in corso</li></ul>|

> [!NOTE]
> Comprendiamo che il viaggio in teams può comportare l'uso di più [modalità](https://aka.ms/skypetoteams-coexist) e l'aggiornamento di gruppi di utenti in orari diversi, che ti consentiranno di controllare l'esperienza di aggiornamento degli utenti mantenendo lo slancio con i team. <br><br>
Per illustrare come può essere spiegato il percorso di aggiornamento, è stato fornito un piano di esempio che definisce un viaggio che passa dalla modalità Skype for business alla **Islands** solo a teams. Inoltre, il piano di esempio delinea un'organizzazione che ha diviso gli utenti in quattro gruppi di aggiornamento o coorti __. Usando questo modello, Personalizza il piano per includere il tuo viaggio specifico in teams, incorporando le varie [modalità](https://aka.ms/skypetoteams-coexist) che userai e il numero di gruppi di aggiornamento in cui segmentare gli utenti.

## <a name="pre-upgrade"></a>Pre-aggiornamento

**Preparare l'organizzazione per i team.** Per garantire un aggiornamento efficace ai team, è importante allocare tempo sufficiente per la preparazione. Non solo la tua organizzazione sarà in grado di iniziare rapidamente a realizzare il valore di teams, potrai accelerare l'aggiornamento da Skype for business non appena i team saranno pronti per te. Monitorare la [Roadmap](https://aka.ms/O365Roadmap) per i miglioramenti previsti per i team; Questo ti aiuterà a identificare la sequenza temporale di aggiornamento appropriata per l'organizzazione. Se hai già abilitato teams insieme a Skype for business, usa queste attività di pre-aggiornamento come checkpoint per convalidare la disponibilità dell'organizzazione prima di aggiornare gli utenti ai team.

> [!Tip]
> Scaricare il [Kit di aggiornamento di successo](https://aka.ms/UpgradeSuccessKit) per i materiali di conformità degli utenti del modello, ad esempio le comunicazioni e i sondaggi degli utenti, oltre a un piano di progetto di aggiornamento di esempio e un piano di test pilota. Gli elementi disponibili nel kit sono contrassegnati con un asterisco (\*) negli elenchi riportati di seguito.

### <a name="days-1ndash7-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>Giorni 1&ndash;7: creare il piano di aggiornamento per verificare che l'organizzazione sia configurata per il successo a lungo termine

|Passaggio||Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Definire le parti interessate** |Considerare l'ambito del progetto e identificare le parti interessate in merito alla disponibilità tecnica e alla disponibilità degli utenti a guidare la responsabilità e il successo. |[Integrare le parti interessate](upgrade-enlist-stakeholders.md) |
|**2** |**Definire la visione del progetto** |La tua visione è l'"immagine grande" o l'eventuale stato finale che risponde alla domanda: "perché stiamo eseguendo questo progetto?" Una visione ideale si riferisce ai driver aziendali e al valore aggiunto degli utenti dell'organizzazione. |[Visione del progetto](upgrade-define-project-scope.md#project-vision) |
|**3** |**Definire l'ambito del progetto** |La tua visione può essere realizzata solo nel tempo, attraverso varie fasi. L'ambito del progetto definisce in questo momento lo stato attivo del progetto e serve a tenere il team di progetto incentrato sulle attività correnti, consentendo di realizzare una visione a lungo termine. |[Ambito del progetto](upgrade-define-project-scope.md#project-scope) |
|**4** |**Definire gli obiettivi del progetto** |I tuoi obiettivi definiscono il risultato che vuoi e ti permettono di misurare il successo del progetto. Gli obiettivi possono essere definiti come obiettivi e risultati chiave (OKRs) e le misure di successo del progetto possono essere definite come indicatori di successo chiave (KSIs). È essenziale ottenere una partecipazione completa dagli stakeholder del progetto alla definizione di OKRs e KSIs, per essere sicuri che sentano un senso di proprietà e allineino queste misure di successo alle attività di progetto definite. Gli obiettivi dovrebbero includere una combinazione di successo tecnico e incentrato sull'utente. |[Obiettivi del progetto](upgrade-define-project-scope.md#project-goals) |
|**5** |**Identificare i rischi e i piani di mitigazione** |È importante valutare in modo proattivo i potenziali rischi e definire un piano di attenuazione per superare i problemi che potrebbero sorgere, quindi il progetto può continuare verso i tuoi obiettivi. Un registro di rischio è uno strumento eccellente per tenere traccia dei rischi del progetto, insieme a quanto sono probabili e al loro potenziale impatto, e ad acquisire il piano di attenuazione. La tabella seguente mostra un esempio di registro dei rischi. |[Rischi e attenuazione](upgrade-define-project-scope.md#risks-and-mitigation) |
|**6** |**Definire la sequenza temporale** |Impostare una sequenza temporale per le attività cardine chiave, ad esempio per consentire a teams insieme a Skype for business per tutti gli utenti o a avviare aggiornamenti in fasi degli utenti, oltre alla data di completamento. Una sequenza temporale definita aiuta l'unità del team di progetto verso uno stato finale coerente e informa la pianificazione del lavoro di destra, contribuendo a garantire che il progetto rimanga in carreggiata. Si consideri una sequenza temporale non troppo accelerata (in cui le attività potrebbero essere elenco). |[Sequenza temporale](upgrade-define-project-scope.md#timeline)<br><br>[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit)|
|**7** |**Definire la strategia appropriata per l'aggiornamento e la coesistenza di Skype for business e teams** |Come cliente esistente di Skype for business, la transizione completa ai team può richiedere del tempo. Puoi tuttavia iniziare a realizzare il valore dei teams oggi, consentendo agli utenti di usare teams insieme a Skype for business. Poiché esistono alcune funzionalità sovrapposte tra le due app, è consigliabile esaminare le modalità di coesistenza e di aggiornamento disponibili per determinare il percorso appropriato per l'organizzazione. Per un'esperienza ottimale, pilota la strategia di coesistenza pianificata prima di distribuire in generale a tutti gli utenti. |[Informazioni sulla coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)<br><br>[Scegliere il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)|

### <a name="days-8ndash15-evaluate-your-organizations-readiness-for-teams"></a>Giorni 8&ndash;15: valutare la disponibilità dell'organizzazione per i team

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Valutare l'ambiente esistente per identificare i rischi e i requisiti** |La valutazione dell'ambiente consente di identificare i rischi e i requisiti che influenzano la distribuzione complessiva. Identificando questi elementi in modo proattivo, è possibile modificare la pianificazione per garantirne il successo. |[Valutare l'ambiente prima di eseguire l'aggiornamento a teams](upgrade-plan-journey-evaluate-environment.md) |
|**2** |**Completare Office 365 e teams Technical onboarding** |Sfruttando gli elenchi di controllo onboarding esistenti per identificare le attività e le attività per completare la preparazione tecnica per la collaborazione e le funzionalità vocali con teams. |[Preparare il servizio per l'aggiornamento a teams](upgrade-prepare-environment-prepare-service.md) |
|**3** |**Ottimizzare la rete per i team, in particolare per gli scenari multimediali in tempo reale** |Se si sta distribuendo audio, video o riunioni, è possibile eseguire alcuni passaggi aggiuntivi per ottimizzare la rete per tale funzionalità. Teams USA la tecnologia audio e video (codec) che possono adattarsi&mdash;e quindi eseguire meglio in&mdash;condizioni di rete. Per garantire prestazioni ottimali e coerenti, è consigliabile preparare la rete per i team. |[Preparare la rete per l'aggiornamento a teams](upgrade-prepare-environment-prepare-network.md) |
|**4** |**Valutare la disponibilità del cambiamento organizzativo** |Per realizzare il valore di teams, gli utenti devono effettivamente usarlo. Semplicemente l'attivazione di teams non garantisce che si raggiunga l'obiettivo. Gli utenti hanno casi di utilizzo diversi e stili di apprendimento variabili e si adattano alle nuove tecnologie a velocità diverse. La comprensione della base utente consente di preparare il livello di istruzione giusto per facilitare e accelerare l'adozione degli utenti. |[Preparazione del cambiamento organizzativo](upgrade-org-change-readiness.md#organizational-change-readiness) |
|**5** |**Preparare un piano di preparazione dell'utente per definire come comunicare, formare e supportare gli utenti** |Per garantire una ricettività ottimale alla nuova tecnologia, usa una combinazione di messaggistica a portata di mano (che incorpora la messaggistica Vision/value e i casi di utilizzo universale) e la messaggistica, la formazione e il supporto personalizzati per gli utenti e le coorti che hai definito e anche per il tuo ritardatari, in base alle esigenze. Questo piano personalizzato consentirà di semplificare l'adozione degli utenti, consentendo all'utente di correlarsi più rapidamente ai team, dimostrando di comprendere le proprie esigenze. Questo può essere usato come pilota, a bordo e per eseguire l'aggiornamento a teams. |[Preparare un piano di preparazione degli utenti](upgrade-user-readiness.md)<br><br>[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit)<br><br>[Formazione video Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Passare a teams da Skype for business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**6** |**Annunciare il lancio in sospeso di Microsoft Teams** |La comunicazione con gli utenti in anticipo consente agli utenti di sentirsi inclusi, riduce la confusione genera entusiasmo per Microsoft teams, contribuendo ad accelerare l'aggiornamento da Skype for business nel tempo. | [Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit) |
|**7** |**Preparare il personale IT per i team** |Gli amministratori del tenant di Office 365, i lead tecnici e il servizio di supporto tecnico sono responsabili della Guida di un'esperienza utente di alta qualità. Questo include garantire che la rete sia pronta per supportare team, configurare Team per gli utenti e riuscire a risolvere efficacemente i problemi che potrebbero presentarsi. |[Preparare il personale IT per Microsoft Teams](https://docs.microsoft.com/microsoftteams/upgrade-prepare-it-pros)<br><br>[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit) |

### <a name="days-16ndash60-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>Giorni 16&ndash;60: eseguire un progetto pilota per verificare che l'organizzazione sia pronta e informare il viaggio ottimale per i team

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Strutturare il pilota Logistics** |Un pilota di successo ha definito date di inizio e di fine e obiettivi chiaramente definiti per misurare il successo. Questi obiettivi devono essere allineati all'ambito del progetto più ampio e verranno usati per informare il percorso in avanti dopo la fine del pilota. |[Strutturare il pilota Logistics](pilot-essentials.md#1-outline-pilot-logistics) |
|**2** |**Selezionare i partecipanti pilota e gli scenari di test** |Selezionare partecipanti pilota non solo in base a ruoli o utenti, ma anche in base al loro progetto e al lavoro cross-team. Il pilota dovrebbe estendersi a persone chiave, formazione e helpdesk, in modo da poter convalidare completamente la soluzione, ottimizzando pienamente le risorse per la gestione dei progetti, assicurandosi di includere gli utenti principali di Skype for business. |[Selezionare i partecipanti pilota e gli scenari di test](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
|**3** |**Progettare il piano di test e il sondaggio di feedback** |Identificare le attività chiaramente definite per il completamento dei partecipanti e un modo per condividere il loro feedback. Raggruppare le attività per offrire scenari reali agli utenti, dimostrando la pertinenza delle attività quotidiane. |[Progettare il piano di test e il sondaggio di feedback](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
|**4** |**Creare un piano di comunicazioni pilota** |Educare i partecipanti al progetto pilota su cosa succede, quando e perché e cosa ci si aspetta. Per stimolare l'eccitazione e la massima partecipazione, assicurati di includere messaggi di valore utente oltre ai collegamenti a formazione e supporto in cui gli utenti possono ottenere informazioni aggiuntive durante l'avanzamento del progetto. |[Creare un piano di comunicazioni](pilot-essentials.md#4-create-your-communications-plan)<br><br>[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit) |
|**5** |**Eseguire il pilota** |L'esecuzione di un pilota include la comunicazione con gli utenti, il monitoraggio della rete e l'uso per garantire che le prestazioni della rete e la qualità delle chiamate rimangano integri, raccolgono feedback dai partecipanti e rivedendo i ticket dell'helpdesk per domande correlate a Squadre. |[Eseguire il pilota](pilot-essentials.md#5-conduct-your-pilot) |
|**6** |**Valutare le informazioni e valutare il piano di avanzamento** |Raccogliere tutti i sondaggi di feedback, le statistiche finali della rete e supportare i ticket per l'analisi in base agli obiettivi e determinare se è possibile implementare il piano di andata e ritorno. |[Valutare le informazioni e valutare il piano di avanzamento](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan) |

### <a name="day-60-until-upgrade-deploy-teams-in-coexistence-with-skype-for-business"></a>Giorno 60 fino all'aggiornamento: distribuire teams in coesistenza con Skype for business

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Annunciare il lancio ufficiale di Teams** |Comunicare con gli utenti per avviare il lancio organizzativo dei team per garantire la consapevolezza e il valore fondiario e beneficiare degli utenti. Considerare più forme di comunicazione, tra cui un evento di avvio e un messaggio di posta elettronica. |[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit) |
|**2** |**Abilitare la modalità di coesistenza appropriata per gli utenti** |Seguire i passaggi per impostare la modalità di coesistenza appropriata per l'organizzazione. |[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md) |
|**3** |**Rimanere informati sulla roadmap per i team** |Monitorare la roadmap dei team e valutare continuamente la disponibilità dell'organizzazione per identificare il momento giusto per il passaggio a teams. |[Roadmap Teams](https://aka.ms/teamsroadmap) |
|**4** |**Inviare comunicazioni aggiuntive e coinvolgere i campioni di team per stimolare** l'eccitazione e l'adozione di Team |Incoraggiare l'adozione degli utenti e mantenere le emozioni per i team con le comunicazioni e i campioni in corso. |[Microsoft 365 Champions Program](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Aggiornamento

**Fare in modo che il trasferimento ufficiale sia in teams.** Quando si aggiornano gli utenti, è possibile spostarli in modalità di coesistenza **solo** in teams. Teams diventa l'app principale per la chat, le riunioni, le chiamate e la collaborazione e l'accesso all'app Skype for business è disabilitato. Anche se gli aspetti tecnici di questa fase sono abbastanza semplici, considera l'effetto che la modifica potrebbe avere sull'esperienza utente e Consenti al tempo per gli utenti di passare ufficialmente le loro attività da Skype for business a teams. Per ridurre gli utenti che hanno esperienze diverse con client diversi, provare a limitare la finestra di aggiornamento end-to-end a 45 giorni o giù di lì.

### <a name="days-1ndash45-implement-your-upgrade-from-skype-for-business-to-teams"></a>Giorni 1&ndash;45: implementare l'aggiornamento da Skype for business a teams

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Verificare di aver completato le attività di pre-aggiornamento descritte in precedenza** |Aiuta a garantire il successo dell'aggiornamento confermando il completamento di tutte le attività di pianificazione e preparazione. |Tutte le versioni precedenti |
|**2** |**Avviare comunicazioni agli utenti nel primo gruppo di aggiornamento** |Iniziare a eseguire il piano di comunicazione pre-, durante e dopo l'aggiornamento per guidare la consapevolezza, impostare le aspettative e condividere i vantaggi dei team con gli utenti prima del loro aggiornamento. |[Preparare un piano di preparazione degli utenti](upgrade-user-readiness.md)<br><br>[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit)<br><br>[Formazione video Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Passare a teams da Skype for business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**3** |**Abilitare la modalità di coesistenza con teams only per gli utenti del primo gruppo di aggiornamento** |Seguire i passaggi appropriati per l'ambiente Skype for business per eseguire la migrazione degli utenti tecnici. |[Eseguire l'aggiornamento da Skype for business online a teams](upgrade-to-teams-execute-skypeforbusinessonline.md)<br><br>[Eseguire l'aggiornamento da una distribuzione ibrida di Skype for business a teams](upgrade-to-teams-execute-skypeforbusinesshybrid.md)<br><br>[Eseguire l'aggiornamento da una distribuzione locale di Skype for business a teams](upgrade-to-teams-execute-skypeforbusinessonpremises.md) |
|**4** |**Ripetere le attività di aggiornamento precedenti per i gruppi di aggiornamento rimanenti in un ciclo di rotazione** |Continuare a guidare il piano di comunicazioni in corso e aggiornare i gruppi di utenti in base al piano. | |
|**5** |**Inviare sondaggi di feedback post-aggiornamento a tutti gli utenti** |Sfrutta un sondaggio di feedback per acquisire feedback e informazioni dettagliate dagli utenti. |[Aggiornare il kit di successo](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>Post-aggiornamento

**Massimizzare il valore aziendale con teams.** Dopo che l'organizzazione è stata completamente aggiornata in teams, prenditi il tempo necessario per valutare il successo rispetto agli obiettivi e implementare un piano per continuare a avanzare.

### <a name="days-1ndash14-measure-the-success-of-your-upgrade"></a>Giorni 1&ndash;14: misurare il successo dell'aggiornamento

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Valutare il successo dell'aggiornamento iniziale** |Valutare lo stato di avanzamento rispetto agli obiettivi stabiliti nella fase di pre-aggiornamento. |[Obiettivi del progetto](upgrade-define-project-scope.md#project-goals) |
|**2** |**Implementare un piano di attenuazione per gli obiettivi che non sono tracciati.** |Definire strategie di attenuazione o di correzione dei corsi per gli obiettivi che non vengono soddisfatti. |[Obiettivi del progetto](upgrade-define-project-scope.md#project-goals) |

### <a name="ongoing"></a>In corso

|Passaggio | |Riepilogo |Risorsa |
|---|---|---|---|
|**1** |**Monitorare l'integrità e la qualità della rete** |L'implementazione di un piano per monitorare e mitigare l'integrità della rete consentirà di garantire un'esperienza utente positiva oltre a ridurre le chiamate al proprio supporto tecnico. |[Monitorare l'integrità e la qualità della rete](continue-journey.md#monitor-for-network-health-and-quality) |
|**2** |**Slancio e adozione dell'utente dell'unità** |Incoraggiare l'adozione degli utenti e mantenere le emozioni per i team con un piano di adozione in corso. |[Slancio e adozione dell'utente dell'unità](continue-journey.md#drive-user-momentum-and-adoption) |
|**3** |**Preparare le nuove funzionalità** |La creazione di un ciclo di modifica all'interno dell'organizzazione assicura la gestione dei miglioramenti della collaborazione continua e la realizzazione del valore massimo. |[Preparare le nuove funzionalità](continue-journey.md#prepare-for-new-functionality) |

> [!Note]
> Il contenuto di Upgrade Pro è in continua evoluzione. Assicurati di controllare le informazioni più aggiornate e di leggere il Blog di [Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog).

> [!Important]
> Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams. Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.
