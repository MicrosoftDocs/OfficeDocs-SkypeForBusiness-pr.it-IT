---
title: Pianificare la gestione del ciclo di vita
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 09/26/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Questo articolo fornisce informazioni su come pianificare l'implementazione delle funzionalità di gestione del ciclo di vita in Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ad4592799efef11b7d09d564af5217dd9cdd550
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951271"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Pianificare la gestione del ciclo di vita in Teams

Teams fornisce un set completo di strumenti per implementare processi di gestione del ciclo di vita della collaborazione per l'organizzazione. Questo articolo guida i professionisti IT nelle domande da porsi per determinare i requisiti per la gestione del ciclo di vita e gli strumenti da usare per soddisfarli. 

La pianificazione della gestione del ciclo di vita è importante, perché equivale a creare un piano per lavorare in modo efficiente. I progetti sono in genere costituiti da un inizio, una parte centrale e una fine. I team funzionano allo stesso modo, ma possono essere costruiti e usati in talmente tanti modi che non sempre è facile capire in che fase del ciclo di vita si trovino. Avere un piano per la gestione del ciclo di vita consente di tenere traccia dei progetti dell'organizzazione nel passaggio tra queste fasi.

> [!Tip]
> Per altre informazioni sul ciclo di vita in Microsoft Teams, guardare la sessione su [governance, gestione e ciclo di vita in Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Concetti relativi al ciclo di vita

Tutti i concetti e le definizioni seguenti hanno effetto sulle decisioni da assumere per la gestione del ciclo di vita.

**Team**

Un _team_ è un insieme di persone, contenuti e strumenti che facilitano la collaborazione. Per ogni team si definiscono i membri e le autorizzazioni e i criteri ad essi applicabili. I team sono basati sui gruppi di Microsoft 365 e le modifiche apportate all'appartenenza al gruppo di Office 365 vengono sincronizzate con il team. Come per gli altri gruppi di Microsoft 365, il provisioning del team viene eseguito automaticamente con una cassetta postale di Exchange, un sito di SharePoint, un blocco appunti di OneNote e altre risorse all'interno di Office 365. [Altre informazioni sui Gruppi di Microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Canali**

I canali sono gli spazi di collaborazione all'interno di un team in cui viene concretamente svolto il lavoro. Ogni canale rappresenta una sequenza di lavoro o un argomento diverso all'interno del team complessivo. Per ogni canale viene creata automaticamente una cartella nel sito di SharePoint in cui archiviare tutti i file condivisi in quel canale. Questo semplifica l'individuazione e l'uso dei documenti importanti per il team. È anche possibile estendere i canali con app attinenti alla sequenza di lavoro corrispondente, ad esempio si può aggiungere una dashboard di Power BI a un canale per tenere traccia della riuscita di un aspetto del progetto.

**Tipi di accesso dei team**

Determinano chi può partecipare al team:

-   I team _privati_ sono riservati ai membri del team autorizzati dai proprietari del team. Si tratta di un'impostazione tipica per i team di progetto e i team virtuali in un'organizzazione di grandi dimensioni.
-   I team _pubblici_ sono aperti alla partecipazione diretta di tutti gli utenti dell'organizzazione. Questo è utile per la collaborazione su argomenti di interesse generale di persone di reparti diversi che lavorano su progetti diversi. Si tratta di un'impostazione predefinita ideale per le organizzazioni di piccole dimensioni.

**Tipi di utenti e ruoli di amministratore dei team** 

Il tipo degli utenti del team ne determina il livello di controllo:

-   Il _creatore del team_ ha le autorizzazioni necessarie per creare un gruppo o un team nella directory. L'amministratore può vincolare questo tipo di utente a un subset di amministratori o utenti. Per altre informazioni, vedere [Gestire chi può creare gruppi di Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). 
-   Il _proprietario del team_ gestisce l'appartenenza e le impostazioni del team. Ogni team può avere fino a 100 proprietari.
-   Il _membro del team_ è un membro dell'organizzazione che partecipa a un team.
-   Un _guest_ è un utente esterno all'organizzazione. Chiunque abbia un indirizzo di posta elettronica può essere invitato come guest, se l'organizzazione ha abilitato l'[accesso guest](guest-access.md).

> [!Note]
> Per altre informazioni sulle capacità di proprietari del team e membri del team, vedere l'articolo [Assegnare ruoli e autorizzazioni in Microsoft Teams](assign-roles-permissions.md).

I ruoli di amministratore di Teams determinano le capacità dei titolari dei vari ruoli di amministratore. Sono descritti nella tabella seguente.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Ruolo&nbsp;&nbsp;</th>
    <th width="25%">Descrizione</th>
    <th width="60%">Può eseguire le attività seguenti, usando gli strumenti indicati</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Amministratore del servizio Teams</td>
    <td valign="top">Gestire il servizio Teams e creare e gestire i gruppi di Microsoft 365</td>
    <td valign="top">Gestire le riunioni, inclusi criteri riunione, configurazioni e bridge di conferenza<sup>1</sup><br><br>Gestire le funzionalità vocali, tra cui criteri di chiamata, inventario e assegnazione dei numeri di telefono, code delle chiamate e operatori automatici<sup>1</sup><br><br>Gestire la messaggistica, inclusi i criteri di messaggistica<sup>1</sup><br><br>Gestire tutte le impostazioni a livello di organizzazione, inclusi federazione, aggiornamento di Teams e impostazioni del client di Teams<sup>1</sup><br><br>Gestire i team dell'organizzazione e le impostazioni associate, inclusa l'appartenenza<sup>2</sup><br><br>Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate degli utenti usando il set di strumenti per la risoluzione dei problemi avanzato<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Amministratore comunicazioni Teams</td>
<td valign="top">Gestire le funzionalità per chiamate e riunioni all'interno del servizio Microsoft Teams</td>
<td valign="top">Gestire le riunioni, inclusi criteri riunione, configurazioni e bridge di conferenza<sup>1</sup><br><br>Gestire le funzionalità vocali, tra cui criteri di chiamata, inventario e assegnazione dei numeri di telefono, code delle chiamate e operatori automatici<sup>1</sup><br><br>Visualizzare la pagina del profilo utente e risolvere i problemi di qualità delle chiamate degli utenti usando il set di strumenti per la risoluzione dei problemi avanzato<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Specialista supporto comunicazioni Teams</td>
<td valign="top">Risolvere i problemi di comunicazione all'interno di Teams tramite strumenti di base</td>
<td valign="top">Accedere alla pagina del profilo utente per la risoluzione dei problemi delle chiamate in Analisi delle chiamate. Può vedere solo le informazioni relative allo specifico utente cercato.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Tecnico supporto comunicazioni Teams</td>
<td valign="top">Risolvere i problemi di comunicazione all'interno di Teams tramite strumenti avanzati</td>
<td valign="top">Accedere alla pagina del profilo utente per la risoluzione dei problemi delle chiamate in Analisi delle chiamate. Può visualizzare le informazioni complete dei record di chiamata.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">Modulo Skype for Business - PowerShell</a> o <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">interfaccia di amministrazione di Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">Modulo Microsoft Teams - PowerShell</a> o <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">interfaccia di amministrazione di Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Solo <a href="https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center">interfaccia di amministrazione di Microsoft Teams</a></td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Decisioni IT da prendere prima di iniziare

Prima di distribuire Teams nell'organizzazione, implementare i criteri di governance stabiliti dall'organizzazione. Questi possono includere ad esempio convenzioni di denominazione, criteri di scadenza, criteri di conservazione e così via. In generale, è molto più facile implementare questi requisiti prima di espandere la distribuzione all'intera organizzazione.

Per altre informazioni, vedere [Pianificare la governance in Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Fasi del ciclo di vita dei team

In generale, un team ha uno scopo allineato a un progetto o al raggiungimento di un obiettivo. Anche se un team è stato creato sulla base di un interesse condiviso, l'appartenenza al team probabilmente cambierà nel corso del tempo e la discussione potrebbe diventare obsoleta, ma riemergere in modo leggermente diverso in un altro team.

Ogni team ha un inizio, quando viene creato e vengono configurati i canali, una parte centrale, quando viene effettivamente usato per collaborare e svolgere parte di un flusso di lavoro e, a volte, una fine, quando il team ha completato il suo scopo e ha raggiunto la fine della vita utile. 

Per altre informazioni, vedere [Gestire i team nell'interfaccia di amministrazione di Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Fase 1: inizio

#### <a name="create-the-team"></a>Creare il team

Il primo passaggio consiste nel definire l'obiettivo del team, che può spaziare dai processi aziendali alla struttura dell'organizzazione, ai progetti oppure semplicemente alla creazione di un hub di collaborazione aperto non strutturato. La definizione dell'obiettivo del team va di pari passo con l'identificazione delle persone giuste. Per quanto possibile, è consigliabile favorire la collaborazione aperta puntando a un'ampia base di appartenenza. 

I proprietari del team invitano i membri del team, impostano l'immagine e la descrizione del team e configurano le autorizzazioni per i singoli membri. 

> [!Tip]
>  È consigliabile identificare almeno due proprietari del team, in modo da tenere conto di assenze o riassegnazioni.

#### <a name="team-origins"></a>Origini dei team

I team possono avere origine in vari modi, tra cui:

-   Creare il team da zero. Aggiungere membri usando singoli nomi utente o alias di posta elettronica oppure espandere una lista di distribuzione.
-   Creare il team da un team esistente e usarne la configurazione dei canali e qualsiasi configurazione delle app come modello. Se si vuole, è anche possibile usarne l'elenco dei membri.
-   Aggiungere un team a un gruppo di Office 365 esistente; in questo modo si consente al team l'accesso alla cassetta postale e al sito di SharePoint del gruppo.
-   Usare le API per Teams di Microsoft Graph o i cmdlet di PowerShell per creare team. Le API possono creare team a livello di programmazione in base agli attributi della Rubrica globale, ad esempio area geografica o reparto, o ai processi aziendali, ad esempio mandati dei clienti o registri di classe.

Seguire questi collegamenti per ottenere altre informazioni sull'organizzazione dei team:

-   [Procedure consigliate per l'organizzazione dei team in Teams](best-practices-organizing.md)
-   [Distribuire chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Distribuire riunioni e conferenze](deploy-meetings-microsoft-teams-landing-page.md)
-   [Distribuire Cloud Voice](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Qual è lo scopo del team?</li><li>Chi appartiene al team?</li><li>Il team sarà pubblico o privato?</li><li>I nuovi membri possono aggiungersi in autonomia o vengono aggiunti dai proprietari del team?</li><li>Chi avrà le autorizzazioni necessarie per creare canali o aggiungere schede, bot e connettori?</li></ul> |
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Creare il team.</li><li>Pianificare i canali.</li></ul>|


#### <a name="set-up-channels"></a>Configurare i canali

Qualunque proprietario o membro del team con autorizzazioni appropriate può creare canali in un team. È importante considerare l'obiettivo di ogni canale. Alcune possibilità sono la collaborazione su progetti, la discussione di argomenti o aree di interesse comune. Per impostazione predefinita, ogni team include un canale generale. Per la maggior parte dei team non sarà sufficiente e i membri creeranno altri canali. È probabile che il set di canali cresca in modo organico man mano che emergono nuovi argomenti o progetti e le discussioni potrebbero scavalcare il canale in cui sono iniziate.

Per suscitare interesse, il proprietario del canale può pubblicare un messaggio di benvenuto, caricare documenti pertinenti nella scheda **File** o aggiungere schede o connettori al canale. Il proprietario imposta anche la descrizione del canale e può aggiungere automaticamente ai preferiti i canali importanti, in modo che siano elencati per impostazione predefinita per tutti i membri del team.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Quali canali iniziali verranno aggiunti al team?</li><li>Quali indicazioni, se del caso, saranno fornite per l'aggiunta di nuovi canali? (Saranno organizzate per progetto, per argomento o altro?)</li></ul> |
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Creare i canali iniziali.</li><li>Pubblicare un messaggio di benvenuto.</li><li>Iniziare a collaborare.</li></ul>|

### <a name="stage-2-middle"></a>Fase 2: parte centrale

Quando ha inizio il lavoro in team, l'appartenenza al team inizia probabilmente a evolversi, insieme alla gerarchia dei canali. A meno che non sia necessario controllare rigorosamente e bloccare il team, è consigliabile incoraggiare l'esplorazione anche se conduce a vicoli ciechi. Man mano che acquistano dimestichezza, gli utenti possono provare a usare menzioni \@team, contrassegnare canali come preferiti e usare il canale generale per familiarizzare con la pubblicazione. Ogni team è diverso; lasciare che l'evoluzione del design sia guidata dall'utilizzo. Monitorare l'utilizzo e l'integrità del team tramite le funzionalità di reporting di Teams.

La fiducia, la tolleranza e lo spirito di collaborazione si sviluppano in modo naturale man mano che le comunicazioni di gruppo strategiche vengono iniziate e gestite in Teams. I membri del team vedono l'utilità delle conversazioni di gruppo rispetto alle chat tra due persone. I singoli team tendono a sviluppare la propria personalità, con l'aiuto di funzionalità divertenti come Giphy e adesivi. Allo stesso tempo, è importante scoraggiare ogni tipo di comportamento scortese o non autorizzato.

Poiché i team sono organismi viventi, a volte devono essere controllati e accuditi. Ecco alcune procedure consigliate:

-   Servirsi di promotori per incentivare l'utilizzo se inizia a calare e anche per individuare e diffondere nuovi comportamenti creativi. 
-   Gestire i guest in modo oculato, assicurandosi che il loro accesso termini quando terminano le esigenze aziendali.
-   Lasciare che i canali si evolvano parallelamente alle esigenze aziendali, aggiungendone di nuovi se necessario e permettendo ai più datati di giungere a esaurimento (o considerare la possibilità di archiviarli o eliminarli se contengono dati sensibili o effimeri, in base ai requisiti di conservazione).
-   Creare nuovi team man mano che emergono gruppi più ampi o aree basate su interessi.
-   Provare diversi tipi di collaborazione sui canali, ad esempio riunioni di canale o conversazioni su schede in merito ai documenti.

Se un team inizia a fossilizzarsi su determinate modalità, considerare la possibilità di:

-   Incentivare le comunicazioni all'interno del team in alternativa alla posta elettronica.
-   Usare le app per dispositivi mobili per aumentare il coinvolgimento.
-   Ridurre il numero di canali.

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Chi monitorerà l'utilizzo per identificare i problemi?</li><li>Quali metriche verranno usate per determinare l'integrità di un team?</li><li>Identificare i team che hanno raggiunto la fine della vita utile.</li><li>Identificare i team non integri che hanno ancora uno scopo, ma devono essere rivitalizzati.</li></ul> |
| ![Icona che descrive il passaggio successivo](media/audio_conferencing_image9.png)<br/>Passaggio successivo|<ul><li>Implementare un processo per il monitoraggio dell'integrità dei singoli team.</li></ul>|

### <a name="stage-3-end"></a>Fase 3: fine

Quando il lavoro di un team è concluso, è importante riconoscerlo formalmente. Questo dà ai membri del team un senso di completamento ed evita che qualcuno acceda a informazioni obsolete. È possibile usare il team stesso per eseguire le attività rituali di chiusura, come la stesura di relazioni finali e riepiloghi esecutivi.

È possibile eliminare i team di cui si è certi di non avere più bisogno, ad esempio un team creato esclusivamente a scopo di test o un team che contiene dati sensibili. I team vengono in realtà eliminati con una "eliminazione temporanea" che l'IT può annullare entro un massimo di 21 giorni (30 giorni per i gruppi di Microsoft 365). L'eliminazione dei team non influisce sulle chat o sui contenuti conservati in ottemperanza ai criteri di conformità. Anche per i canali esiste l'eliminazione temporanea e possono essere ripristinati entro un massimo di 21 giorni.

È anche possibile usare i criteri di scadenza e conservazione oltre alle funzionalità di archiviazione per ridurre l'esposizione associata ai team non più attivi o i cui proprietari hanno lasciato l'organizzazione.

Per informazioni su come configurare i criteri di scadenza e conservazione, vedere [Panoramica della sicurezza e della conformità in Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![Icona che descrive i punti decisionali](media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Definire a cosa corrisponda la fine del ciclo di vita di un team.</li><li>Decidere se mantenere disponibile il contenuto di un team e quanto a lungo.</li></ul> |
| ![Icona che descrive i passaggi successivi](media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Documentare le procedure consigliate e l'analisi di fine progetto.</li><li>Archiviare i dati, se necessario.</li></ul>|

## <a name="related-topics"></a>Argomenti correlati

[Guida introduttiva sulla governance per Teams](teams-adoption-governance-quick-start.md)
