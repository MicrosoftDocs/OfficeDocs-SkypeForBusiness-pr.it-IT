---
title: Teams per l'istruzione Creazione guidata Criteri per applicare facilmente i criteri per l'apprendimento sicuro
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare la procedura guidata Teams per l'istruzione criteri di apprendimento per applicare facilmente criteri per studenti e docenti per mantenere sicuro l'ambiente di apprendimento.
f1keywords: ''
ms.openlocfilehash: d7e2959b5b824d8b053d9b912d0450c2209b4b1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604595"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usare la Teams per l'istruzione guidata criteri di protezione per applicare facilmente i criteri per un ambiente di apprendimento sicuro

## <a name="overview"></a>Panoramica

La Microsoft Teams per l'istruzione guidata criteri semplifica la gestione dei criteri per studenti e docenti. Usarlo per applicare in modo semplice e rapido il set più importante di criteri rilevanti per la creazione di un'esperienza di apprendimento sicura e produttiva.

I criteri in Teams consentono di controllare il comportamento Teams nell'ambiente e le caratteristiche disponibili per gli utenti. Ad esempio, esistono criteri per le chiamate, criteri riunione e criteri di messaggistica, per citarne alcuni e ogni area dei criteri può essere personalizzata in base alle esigenze dell'organizzazione.

Per mantenere un ambiente di apprendimento sicuro e mirato, è importante impostare criteri per controllare cosa possono fare gli studenti in Teams. Ad esempio, è possibile usare i criteri per controllare chi può usare la chat privata e le chiamate private, chi può pianificare riunioni e quali tipi di contenuto possono essere condivisi. È anche possibile usare i criteri per attivare Teams caratteristiche che arricchiscono l'esperienza di apprendimento.

Per mantenere al sicuro l'esperienza di apprendimento, è necessario modificare i criteri sia per gli studenti che per i docenti. I criteri per gli studenti devono essere più restrittivi per ridurre il rischio di ricevere livelli di accesso inappropriati. I docenti e il personale devono disporre di un set separato di criteri che possano essere più permissivi per consentire loro di avere successo. Ad esempio, consentire ai docenti di pianificare riunioni e limitare gli studenti a farlo.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot della procedura guidata":::

Questo articolo illustra come eseguire la procedura guidata.

> [!IMPORTANT]
> I criteri applicati dalla procedura guidata soddisferanno le esigenze della maggior parte Teams per l'istruzione clienti. La procedura guidata regola la definizione globale (predefinita a livello di organizzazione) di un set di criteri di base con impostazioni consigliate per la sicurezza degli studenti e la applica agli studenti. La procedura guidata crea e assegna anche un set di criteri personalizzati a docenti e personale. La maggior Teams per l'istruzione i clienti non dovranno usare altri metodi di assegnazione dei criteri dopo l'esecuzione di questa procedura guidata. Usare altri metodi di *assegnazione* dei criteri solo se si vogliono creare e gestire manualmente criteri per studenti, docenti e personale.

## <a name="teams-for-education-policy-wizard"></a>Teams per l'istruzione Creazione guidata Criteri

<a name="polwiz_intro"> </a>

La procedura guidata applica un set di definizioni dei criteri di base agli studenti e un set separato di definizioni dei criteri di base per docenti e personale, con impostazioni appropriate per ognuno di essi. Ecco cosa succede quando si esegue la procedura guidata.

La procedura guidata configura i criteri in base al tipo di istituto di istruzione (**Primario o Secondario** **o Istruzione superiore**). Selezionare il tipo di istituto e la procedura guidata esegue le operazioni seguenti:

- **Studenti:** la procedura guidata regola la definizione dei criteri globale (impostazione predefinita a livello di organizzazione) di ogni area dei criteri coperta dalla procedura guidata con nuove impostazioni predefinite appropriate per mantenere al sicuro gli studenti. In questo modo gli studenti correnti e tutti i nuovi studenti ottengono il set di criteri più restrittivo.
- **Docenti e personale:** la procedura guidata crea un set di definizioni dei criteri personalizzate per ogni area dei criteri coperta dalla procedura guidata con impostazioni personalizzate in base alle esigenze di docenti e personale. Assegna quindi le definizioni dei criteri al gruppo di docenti e al personale scelto. In questo modo, i docenti e il personale ottengono un set di criteri più permissivo per consentirgli di avere successo.

È necessario eseguire la procedura guidata una sola volta. I nuovi studenti ottengono automaticamente le definizioni dei criteri globali (impostazione predefinita a livello di organizzazione) applicate dalla procedura guidata e ai nuovi membri aggiunti al gruppo selezionato vengono assegnati automaticamente i criteri personalizzati.

Inoltre, ogni volta che viene aggiunta una nuova funzionalità a Teams, il valore predefinito appropriato pertinente dell'EDU del criterio per tale caratteristica verrà aggiunto automaticamente al valore globale (impostazione predefinita a livello di organizzazione) senza richiedere l'intervento dell'amministratore. In questo modo si garantisce la sicurezza e l'coinvolgimento degli studenti.

> [!NOTE]
> Per un elenco dettagliato delle definizioni dei criteri applicate dalla procedura [guidata,](#policies-applied-by-the-wizard) vedere Criteri applicati dalla procedura guidata.

Ora, iniziamo!

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

<a name="polwiz_run"> </a>

Seguire questa procedura per eseguire la procedura guidata.

1. Se non si ha la Teams, la procedura guidata viene avviata automaticamente. In caso contrario, è possibile avviare la procedura guidata in qualsiasi momento dal dashboard. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione Microsoft Teams, passare **a** **Dashboard** e quindi nel riquadro Configurazione semplice dei criteri per un ambiente di apprendimento sicuro selezionare **Configurazione rapida.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot della procedura guidata nel dashboard":::

2. Selezionare il tipo di istituto di istruzione (**Primario o Secondario** o Istruzione **superiore**), quindi scegliere **Avanti**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot della pagina della procedura guidata per selezionare il tipo di istituto":::

3. Cercare e selezionare un gruppo contenente i docenti e il personale, quindi selezionare **Avanti.** Se non è ancora stato configurato alcun gruppo per i docenti e il [personale,](/microsoft-365/admin/create-groups/create-groups)creare un gruppo e quindi eseguire di nuovo la procedura guidata. <br/><br/>Attualmente è possibile selezionare un solo gruppo. Ai docenti e al personale del gruppo selezionato verrà assegnato [un set](#policies-applied-by-the-wizard) di criteri personalizzati personalizzati in base alle proprie esigenze. Tenere presente che questo set di criteri è separato dai criteri applicati agli studenti.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Screenshot della pagina della procedura guidata per selezionare il gruppo di docenti e personale":::

4. Rivedere le selezioni.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Screenshot della pagina della procedura guidata per rivedere le selezioni":::

5. Selezionare **Applica** per applicare le modifiche. Il completamento dell'operazione potrebbe richiedere alcuni minuti.<br/><br/>Le definizioni dei criteri globali (predefinite a livello di organizzazione) vengono applicate immediatamente agli studenti. Per i docenti e il personale, l'assegnazione dei criteri personalizzati a ogni membro del gruppo selezionato può richiedere alcune ore, a seconda delle dimensioni del gruppo. Questa situazione si verifica in background dopo aver completato correttamente questo passaggio.
6. Stai arrivando, ma non hai ancora finito! Ci sono altre cose da considerare. Vedere quindi i passaggi descritti nella sezione Operazioni [da eseguire dopo l'esecuzione della procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot della pagina della procedura guidata per i passaggi successivi":::

## <a name="what-to-do-after-running-the-wizard"></a>Procedura dopo l'esecuzione della procedura guidata

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Passaggio 1: Rimuovere le assegnazioni dei criteri esistenti in conflitto con i criteri applicati dalla procedura guidata

> [!IMPORTANT]
> **Completare questo  passaggio solo se sono** stati assegnati criteri esistenti a studenti o docenti e personale prima di eseguire la procedura guidata. Se non si ha Teams criteri esistenti diversi dai criteri creati dalla procedura guidata, ignorare questa opzione e andare al passaggio 2.

In Teams, per un'area dei criteri specifica, un criterio può essere applicato a un utente nei modi seguenti:

- Assegnazione diretta all'utente
- Assegnazione a un gruppo di cui l'utente è membro
- Se all'utente non è assegnato direttamente un criterio o non è un membro di un gruppo a cui è assegnato un criterio, l'utente ottiene automaticamente il criterio Globale (impostazione predefinita a livello di organizzazione)

Se per un utente sono presenti più assegnazioni di criteri, Teams l'ordine seguente per determinare quale assegnazione dei criteri ha effetto. Per altre informazioni, vedere [Quali criteri hanno la precedenza?](assign-policies.md#which-policy-takes-precedence) e Regole di [precedenza.](assign-policies.md#precedence-rules)

|Assegnazioni dei criteri di un utente|Criteri che hanno effetto |
|---------|---------|
|Criterio assegnato al gruppo: No<br/>Criterio assegnato direttamente all'utente: No    |Criterio predefinito globale (a livello di organizzazione)      |
|Criterio assegnato al gruppo: No<br/>Criterio assegnato direttamente all'utente: Sì    |Criterio assegnato direttamente all'utente         |
|Criterio assegnato al gruppo: Sì<br/>Criterio assegnato direttamente all'utente: Sì     |Criterio assegnato direttamente all'utente         |
|Criterio assegnato al gruppo: Sì<br/>Criterio assegnato direttamente all'utente: No     |Criterio assegnato al gruppo<br/><br/>Se l'utente è un membro di più gruppi e a ogni gruppo viene assegnato un criterio della stessa area dei criteri, viene utilizzato il criterio con la classificazione di assegnazione [di](assign-policies.md#group-assignment-ranking) gruppo più alta.       |

A causa di questo ordine, i criteri creati dalla procedura guidata non saranno applicati se un utente ha già attività dirette o di gruppo. Questo significa che sarà necessario rimuovere le assegnazioni dei criteri esistenti dall'utente in modo che il criterio applicato dalla procedura guidata abbia effetto.

Per ogni [area dei criteri applicata dalla procedura guidata,](#policies-applied-by-the-wizard)eseguire le operazioni seguenti:

- Rimuovere tutte le attività dirette e di gruppo esistenti dagli studenti in modo che la definizione dei criteri Globale (predefinita a livello di organizzazione) applicata dalla procedura guidata sia effettiva.
- Rimuovere eventuali assegnazioni dirette in conflitto per docenti e personale in modo che la definizione dei criteri personalizzati creata dalla procedura guidata sia effettiva. Usare la tabella precedente per determinare gli scenari applicabili. <br/><br/>Tenere presente che la procedura guidata assegna criteri ai [](assign-policies.md#group-assignment-ranking) docenti e al gruppo di personale usando una classificazione delle assegnazioni di gruppo di 1, ovvero la classificazione più alta. Se ai docenti e al gruppo di personale è assegnato un criterio esistente della stessa area dei criteri, il criterio esistente viene spostato in una classificazione inferiore e i criteri assegnati dalla procedura guidata vengono applicate.

[Altre informazioni](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) su come rimuovere i criteri assegnati direttamente agli utenti.

Ad esempio, è stato assegnato un criterio di riunione direttamente ai docenti e gli studenti hanno il criterio di riunione Globale (impostazione predefinita a livello di organizzazione). In questo scenario, rimuovere i criteri riunione assegnati direttamente ai docenti in modo che la definizione dei criteri personalizzati per i criteri di riunione creati dalla procedura guidata sia effettiva. Non è necessario eseguire alcuna operazione con i criteri di riunione globali (predefiniti a livello di organizzazione) esistenti per gli studenti perché nessun altro criterio di riunione è in conflitto con esso.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Passaggio 2: Verificare la presenza di altre misure che è possibile adottare per la sicurezza degli studenti

La procedura guidata modifica e applica automaticamente [questi criteri.](#policies-applied-by-the-wizard) Sono disponibili alcune misure aggiuntive, che è possibile adottare in base alle esigenze dell'istituto per rimanere al sicuro.

Per altri consigli sulla sicurezza, vedere Tenere gli studenti al sicuro [Teams l'apprendimento a](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) distanza.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Passaggio 3: Controllare la disponibilità di aggiornamenti dei criteri nel Centro messaggi

Attualmente, la procedura guidata applica i criteri consigliati quando viene eseguita. È importante sapere che quando i nuovi criteri diventano disponibili in Teams, le impostazioni globali (predefinite a livello di organizzazione) per la sicurezza degli studenti vengono aggiornate automaticamente dalla procedura guidata. 

Tuttavia, controllare [spesso](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) il Centro messaggi (nel interfaccia di amministrazione di Microsoft 365) per rimanere aggiornati sulle nuove caratteristiche e sui criteri e le impostazioni dei criteri in Teams. 

## <a name="make-changes-in-the-wizard"></a>Apportare modifiche nella procedura guidata

<a name="polwiz_change"> </a>

Se è necessario apportare modifiche dopo aver eseguito la procedura guidata, è possibile eseguirla di nuovo e modificare le selezioni.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare **a** **Dashboard** e quindi nel riquadro Configurazione dei criteri per un ambiente di apprendimento sicuro selezionare **Cambia**.
2. Da qui, continuare con ogni pagina della procedura guidata per apportare le modifiche. È possibile modificare il tipo di istituto, il gruppo di docenti e personale a cui si vogliono assegnare i criteri o entrambi.

La tabella seguente riepiloga cosa succede quando si apporta una modifica nella procedura guidata.

|Tipo di modifica  |Comportamento dei criteri  |
|---------|---------|
|Modificare sia il tipo di istituto di istruzione che il gruppo di docenti e personale    |<ul><li>**Studenti:** le definizioni dei criteri globali (predefinite a livello di organizzazione) basate sul nuovo tipo di istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale:** viene creato e assegnato al nuovo gruppo di docenti e personale un set di definizioni dei criteri personalizzati in base al nuovo tipo di istituto di istruzione. Le definizioni dei criteri personalizzati precedenti vengono rimosse dai docenti e dal gruppo di personale precedente.</li></ul>    |
|Modificare solo il tipo di istituto di istruzione    |<ul><li>**Studenti:** le definizioni dei criteri globali (predefinite a livello di organizzazione) basate sul nuovo tipo di istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale:** viene creato un set di definizioni dei criteri personalizzati in base al nuovo tipo di istituto di istruzione e viene assegnato ai docenti e al gruppo di personale. Le definizioni dei criteri personalizzati create per il tipo di istituto di istruzione precedente vengono rimosse dal gruppo di docenti e personale.</li></ul>         |
|Modificare solo i docenti e il gruppo di personale   |<ul><li>**Studenti:** nessuna modifica alle definizioni dei criteri globali (predefinite a livello di organizzazione) applicate agli studenti.</li><li>**Docenti e personale:** le definizioni dei criteri personalizzati vengono assegnate ai nuovi docenti e al gruppo di personale e rimosse dal gruppo di docenti e personale precedente.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Criteri applicati dalla procedura guidata

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Aree dei criteri

Ecco le aree dei criteri e i nomi dei criteri corrispondenti coperti dalla procedura guidata. Per trovare questi criteri, passare all'interfaccia Microsoft Teams di amministrazione e quindi, nel riquadro di spostamento sinistro, passare a ogni pagina dell'area dei criteri.

#### <a name="students"></a>[**Studenti**](#tab/students/)

|Area criteri  |Nome del criterio principale o secondario |Nome dei criteri per l'istruzione superiore  |
|---------|---------|---------|
|Criteri di team    |Globale (impostazione predefinita a livello di organizzazione)         |Globale (impostazione predefinita a livello di organizzazione)           |
|Criterio di riunione    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri per gli eventi live     |Globale (impostazione predefinita a livello di organizzazione)          |  Globale (impostazione predefinita a livello di organizzazione)          |
|Criteri di configurazione delle app     |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di autorizzazione per le app    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di messaggistica     |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di chiamata    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educators/)

|Area criteri  |Nome del criterio principale o secondario |Nome dei criteri per l'istruzione superiore |
|---------|---------|---------|
|Criteri di team   |Docenti e personale docente primario o secondario - Teams         |Docenti e personale dell'istruzione superiore - Teams         |
|Criterio di riunione    |Docenti e personale docente primario o secondario - Riunione         |Docenti e personale dell'istruzione superiore - Riunione         |
|Criteri per gli eventi live   | Docenti e personale principale o secondario - Eventi live         |Docenti e personale dell'istruzione superiore - Eventi live         |
|Criteri di messaggistica    |Docenti e personale docente primario o secondario - Messaggistica         | Docenti e personale dell'istruzione superiore - Messaggistica         |
|Criteri di chiamata    |Docenti e personale docente primario o secondario - Chiamate         |Docenti e personale dell'istruzione superiore - Chiamate         |

* * *

### <a name="policy-settings"></a>Impostazioni dei criteri

Ecco un riepilogo delle impostazioni applicate dalla procedura guidata per ogni area dei criteri.

#### <a name="students"></a>[**Studenti**](#tab/student-settings/)

Ecco un elenco delle definizioni dei criteri globali (predefinite a livello di organizzazione) modificate dalla procedura guidata e applicate agli studenti.

|Area criteri |Area secondaria  |Impostazione dei criteri  |Principale o Secondario |Istruzione superiore |
|---------|---------|---------|---------|---------|
|Criteri di team   |         |Creare canali privati         |Disattivato       |Attivato|
|Criteri per le riunioni    |Generale         |Consenti l'uso di Riunione immediata nei canali         |Disattivato      |Attivato|
|  |        |Consenti il componente aggiuntivo per Outlook         |Disattivato       |Attivato|
|  |        |Consenti la pianificazione delle riunioni di canale        |Disattivato      |Attivato|
|  |        |Consenti la pianificazione di riunioni private       |Disattivato      |Attivato|
|  |        |Consentire la registrazione alla riunione              |Attivato       |Attivato|
|  |        |Who possibile registrare    |Tutti gli utenti dell'organizzazione      |Tutti gli utenti dell'organizzazione|
|  |Video & audio        |Consenti la trascrizione        |Attivato       |Attivato|
|  |        |Consenti la registrazione cloud         |Disattivato      |Attivato|
|  |        |Modalità per audio IP       |Audio in uscita e in arrivo abilitato        |Audio in uscita e in arrivo abilitato|
|  |        |Modalità per video IP         |Video in uscita e in arrivo abilitato     |Video in uscita e in arrivo abilitato|
|  |       |Consenti video IP         |Attivato         |Attivato|
|  |       |Consenti streaming NDI         |Disattivato         |Disattivato|
|  |       |Velocità in bit supporto (KB)         |50,000         |50,000|
|  |Condivisione di contenuti       |Modalità condivisione schermo         |Schermo intero         |Schermo intero|
|  |       |Consenti a un partecipante di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti a un partecipante esterno di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti la condivisione di PowerPoint        |Attivato         |Attivato|
|  |       |Consenti la lavagna         |Attivato         |Attivato|
|  |       |Consenti note condivise         |Attivato        |Attivato|
|  |Partecipanti & guest       |Consenti alle persone anonime di avviare una riunione       |Disattivato         |Attivato|
|  |       |Ruoli con diritti di relatore nelle riunioni        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Ammetti automaticamente le persone        |EveryoneInCompany|EveryoneInCompany|
|  |       |Consenti agli utenti che chiamano di ignorare la sala di attesa        |Disattivato         |Disattivato|
|  |       |Consenti l'uso di Riunione immediata nelle riunioni private        |Disattivato         |Attivato|
|  |       |Abilita i sottotitoli in tempo reale       |Disabilitato ma l'utente può eseguire l'override         |Disabilitato ma l'utente può eseguire l'override|
|  |       |Consenti l'uso della chat nelle riunioni          |Attivato         |Attivato|
|Criteri per gli eventi live  |       |Consenti la pianificazione         |Disattivato         |Disattivato|
|  |       |Consenti trascrizione per i partecipanti          |Attivato       |Attivato|
|  |       |Chi può aggiungere eventi live pianificati        |Tutti gli utenti dell'organizzazione        |Tutti gli utenti dell'organizzazione|
|  |       |Who registrare un evento         |Sempre         |Sempre|
|Criteri di messaggistica  |       |I proprietari possono eliminare i messaggi inviati         |Disattivato|Attivato|
|  |       |Eliminare i messaggi inviati         |Disattivato         |Attivato|
|  |       |Modificare i messaggi inviati         |Disattivato         |Attivato|
|  |       |Conferme di lettura         |Controllato dall'utente         |Controllato dall'utente|
|  |       |Chat         |Disattivato         |Attivato|
|  |       |Usare Giphys nelle conversazioni         |Disattivato         |Attivato|
|  |       |Classificazione del contenuto Giphy         |Strict        |Strict|
|  |       |Usare Memes nelle conversazioni         |Attivato         |Attivato|
|  |       |Usare gli adesivi nelle conversazioni         |Attivato         |Attivato|
|  |       |Consenti anteprime URL        |Attivato         |Attivato|
|  |       |Tradurre i messaggi         |Attivato         |Attivato|
|  |       |Consentire lo strumento di lettura immersiva per la visualizzazione dei messaggi        |Attivato      |Attivato|
|  |       |Invio di messaggi urgenti con notifiche priorità  |Disattivato         |Attivato|
|  |       |Creare messaggi vocali         |Consentito nelle chat e nei canali         |Consentito nelle chat e nei canali|
|  |       |Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti     |Abilitata         |Abilitata|
|  |       |Rimuovere utenti dalle chat di gruppo         |Disattivato         |Attivato|
|Criteri di autorizzazione per le app  |       |App Microsoft         |Bloccare app specifiche e consentire a tutti gli > Walkie Talkie bloccato         |Consenti tutte le app|
|  |       |App di terze parti         |Consenti tutte le app         |Consenti tutte le app|
|  |       |App personalizzate         |Consenti tutte le app         |Consenti tutte le app|
|Criteri di configurazione delle app  |           |Upload app personalizzate           |Disattivato         |Disattivato|
|  |       |Consentire l'aggiunta di utenti |Attivato         |Attivato|
|  |       |App installate         |Nessuno         |Nessuno|
|  |       |App aggiunte         |Attività, Calendario, Teams         |Attività, Chat, Teams, Calendario, Chiamate, File
|Criteri di chiamata  |       |Effettuare chiamate private         |Disattivato        |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione         |Disattivato         |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni         |Disattivato         |Attivato|
|  |       |La segreteria telefonica è disponibile per il routing delle chiamate in ingresso         |Controllato dall'utente         |Controllato dall'utente|
|  |       |Le chiamate in ingresso possono essere instradati ai gruppi di chiamate         |Disattivato        |Attivato|
|  |       |Consentire la delega per le chiamate in ingresso e in uscita         |Disattivato         |Attivato|
|  |       |Evitare il bypass a pedaggio e inviare chiamate tramite PSTN        |Disattivato         |Disattivato|
|  |       |Occupato in caso di disponibilità è disponibile durante una chiamata         |Disattivato         |Disattivato|
|  |       |Consenti chiamate PSTN Web         |Disattivato         |Attivato|

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educator-settings/)

Ecco un elenco delle definizioni dei criteri personalizzati assegnate ai docenti e al gruppo di personale scelto nella procedura guidata.  

|Area criteri |Area secondaria  |Impostazione dei criteri  |Principale o Secondario |Istruzione superiore |
|---------|---------|---------|---------|---------|
|Criteri di team   |         |Creare canali privati         |Attivato       |Attivato|
|Criteri per le riunioni    |Generale         |Consenti l'uso di Riunione immediata nei canali         |Attivato      |Attivato|
|  |        |Consenti il componente aggiuntivo per Outlook         |Attivato       |Attivato|
|  |        |Consenti la pianificazione delle riunioni di canale        |Attivato      |Attivato|
|  |        |Consenti la pianificazione di riunioni private       |Attivato      |Attivato|
|  |        |Consentire la registrazione alla riunione              |Attivato       |Attivato|
|  |        |Who possibile registrare    |Tutti gli utenti dell'organizzazione      |Tutti gli utenti dell'organizzazione|
|  |Video & audio        |Consenti la trascrizione        |Attivato       |Attivato|
|  |        |Consenti la registrazione cloud         |Attivato      |Attivato|
|  |        |Modalità per audio IP       |Audio in uscita e in arrivo abilitato        |Audio in uscita e in arrivo abilitato|
|  |        |Modalità per video IP         |Video in uscita e in arrivo abilitato     |Video in uscita e in arrivo abilitato|
|  |       |Consenti video IP         |Attivato         |Attivato|
|  |       |Consenti streaming NDI         |Disattivato         |Disattivato|
|  |       |Velocità in bit supporto (KB)         |50,000         |50,000|
|  |Condivisione di contenuti       |Modalità condivisione schermo         |Schermo intero         |Schermo intero|
|  |       |Consenti a un partecipante di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti a un partecipante esterno di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti la condivisione di PowerPoint        |Attivato         |Attivato|
|  |       |Consenti la lavagna         |Attivato         |Attivato|
|  |       |Consenti note condivise         |Attivato        |Attivato|
|  |Partecipanti & guest       |Consenti alle persone anonime di avviare una riunione       |Attivato        |Attivato|
|  |       |Ruoli con diritti di relatore nelle riunioni        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Ammetti automaticamente le persone        |OrganizerOnly|OrganizerOnly|
|  |       |Consenti agli utenti che chiamano di ignorare la sala di attesa        |Disattivato         |Disattivato|
|  |       |Consenti l'uso di Riunione immediata nelle riunioni private        |Attivato         |Attivato|
|  |       |Abilita i sottotitoli in tempo reale       |Disabilitato ma l'utente può eseguire l'override         |Disabilitato ma l'utente può eseguire l'override|
|  |       |Consenti l'uso della chat nelle riunioni          |Attivato         |Attivato|
|Criteri per gli eventi live  |       |Consenti la pianificazione         |Attivato         |Attivato|
|  |       |Consenti trascrizione per i partecipanti          |Attivato       |Attivato|
|  |       |Chi può aggiungere eventi live pianificati        |Tutti gli utenti dell'organizzazione        |Tutti gli utenti dell'organizzazione|
|  |       |Who registrare un evento         |Registra sempre         |Registra sempre|
|Criteri di messaggistica  |       |I proprietari possono eliminare i messaggi inviati         |Attivato|Attivato|
|  |       |Eliminare i messaggi inviati         |Attivato         |Attivato|
|  |       |Modificare i messaggi inviati         |Attivato         |Attivato|
|  |       |Conferme di lettura         |Controllato dall'utente         |Controllato dall'utente|
|  |       |Chat         |Attivato         |Attivato
|  |       |Usare Giphys nelle conversazioni         |Attivato        |Attivato|
|  |       |Classificazione del contenuto Giphy         |Strict        |Strict|
|  |       |Usare Memes nelle conversazioni         |Attivato         |Attivato|
|  |       |Usare gli adesivi nelle conversazioni         |Attivato         |Attivato|
|  |       |Consenti anteprime URL        |Attivato         |Attivato|
|  |       |Tradurre i messaggi         |Attivato         |Attivato|
|  |       |Consentire lo strumento di lettura immersiva per la visualizzazione dei messaggi        |Attivato      |Attivato|
|  |       |Invio di messaggi urgenti con notifiche priorità  |Attivato         |Attivato|
|  |       |Creare messaggi vocali         |Consentito nelle chat e nei canali         |Consentito nelle chat e nei canali|
|  |       |Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti     |Abilitata         |Abilitata|
|  |       |Rimuovere utenti dalle chat di gruppo         |Attivato        |Attivato|
|Criteri di chiamata  |       |Effettuare chiamate private         |Attivato       |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione         |Attivato        |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni         |Attivato        |Attivato|
|  |       |La segreteria telefonica è disponibile per il routing delle chiamate in ingresso         |Controllato dall'utente         |Controllato dall'utente|
|  |       |Le chiamate in ingresso possono essere instradati ai gruppi di chiamate         |Attivato        |Attivato|
|  |       |Consentire la delega per le chiamate in ingresso e in uscita         |Attivato         |Attivato|
|  |       |Evitare il bypass a pedaggio e inviare chiamate tramite PSTN        |Disattivato         |Disattivato|
|  |       |Occupato in caso di disponibilità è disponibile durante una chiamata         |Disattivato         |Disattivato|
|  |       |Consenti chiamate PSTN Web         |Attivato      |Attivato|

* * *

## <a name="related-topics"></a>Argomenti correlati

- [Criteri e pacchetti di criteri di Teams per l'istruzione](policy-packages-edu.md)
- [Assegnare criteri a grandi set di utenti dell'istituto di istruzione](batch-group-policy-assignment-edu.md)
- [Mantenere gli studenti al sicuro durante l'Teams per l'apprendimento a distanza](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
