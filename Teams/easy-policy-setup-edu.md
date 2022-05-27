---
title: Teams per l'istruzione Creazione guidata Criteri per applicare facilmente criteri per l'apprendimento sicuro
author: serdars
ms.author: serdars
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
description: Informazioni su come usare la procedura guidata per i criteri di Teams per l'istruzione per applicare facilmente criteri per studenti e docenti per mantenere sicuro l'ambiente di apprendimento.
f1keywords: ''
ms.openlocfilehash: 245739f06d86459f119d9f5d0a37e67ac4098953
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675918"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usare la Creazione guidata Criteri di Teams per l'istruzione per applicare facilmente criteri per un ambiente di apprendimento sicuro

## <a name="overview"></a>Panoramica

La procedura guidata Microsoft Teams per l'istruzione criteri semplifica la gestione dei criteri per studenti e docenti. Usarla per applicare in modo semplice e rapido il set di criteri più importante per la creazione di un'esperienza di apprendimento sicura e produttiva.

I criteri in Teams consentono di controllare il comportamento di Teams nell'ambiente e le caratteristiche disponibili per gli utenti. Ad esempio, esistono criteri di chiamata, criteri di riunione e criteri di messaggistica, per citarne alcuni, e ogni area dei criteri può essere personalizzata in base alle esigenze dell'organizzazione.

Per mantenere un ambiente di apprendimento sicuro e concentrato, è importante impostare criteri per controllare le operazioni che gli studenti possono eseguire in Teams. Ad esempio, è possibile usare i criteri per controllare chi può usare la chat privata e le chiamate private, chi può pianificare le riunioni e quali tipi di contenuto possono essere condivisi. È anche possibile usare i criteri per attivare Teams caratteristiche che arricchiscono l'esperienza di apprendimento.

Per mantenere sicura l'esperienza di apprendimento, è necessario modificare i criteri sia per gli studenti che per i docenti. I criteri per gli studenti devono essere più restrittivi per ridurre il rischio di ricevere livelli di accesso inappropriati. I docenti e il personale hanno bisogno di un set di criteri separato che può essere più permissivo per consentire loro di avere successo. Ad esempio, consentire ai docenti di pianificare le riunioni e impedire agli studenti di farlo.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot della procedura guidata.":::

Questo articolo illustra come eseguire la procedura guidata.

> [!IMPORTANT]
> I criteri applicati dalla procedura guidata soddisfano le esigenze della maggior parte dei clienti Teams per l'istruzione. La procedura guidata modifica la definizione globale (predefinita a livello di organizzazione) di un set di criteri di base con impostazioni consigliate per la sicurezza degli studenti e le applica agli studenti. La procedura guidata crea e assegna anche un set di criteri personalizzati a docenti e personale. La maggior parte Teams per l'istruzione clienti non dovranno usare altri metodi di assegnazione dei criteri dopo aver eseguito questa procedura guidata. Usare altri metodi di assegnazione dei criteri *solo* se si vogliono creare e gestire manualmente i criteri per studenti, docenti e personale.

## <a name="teams-for-education-policy-wizard"></a>Creazione guidata Criteri di Teams per l'istruzione

<a name="polwiz_intro"> </a>

La procedura guidata applica un set di definizioni dei criteri di base agli studenti e un set separato di definizioni dei criteri di base a docenti e personale, con impostazioni appropriate per ognuno di essi. Ecco cosa succede quando si esegue la procedura guidata.

La procedura guidata configura i criteri in base al tipo di istituto di istruzione (**Primaria o Secondaria** o **Istruzione superiore**). Si seleziona il tipo di istituto e la procedura guidata esegue le operazioni seguenti:

- **Studenti**: la procedura guidata modifica la definizione dei criteri globali (predefiniti a livello di organizzazione) per ogni area dei criteri coperta dalla procedura guidata con le nuove impostazioni predefinite appropriate per garantire la sicurezza degli studenti. In questo modo gli attuali studenti e tutti i nuovi studenti ottengono il set di criteri più restrittivo.
- **Docenti e personale**: la procedura guidata crea un set di definizioni dei criteri personalizzate per ogni area dei criteri coperta dalla procedura guidata con impostazioni personalizzate per le esigenze di docenti e personale. Assegna quindi le definizioni dei criteri al gruppo di docenti e personale scelto. In questo modo, i docenti e il personale ottengono un set di criteri più permissivo per consentire loro di avere successo.

È sufficiente eseguire la procedura guidata una sola volta. Ai nuovi studenti vengono automaticamente applicate le definizioni dei criteri globali (predefiniti a livello di organizzazione) dalla procedura guidata e ai nuovi membri del personale aggiunti al gruppo selezionato vengono assegnati automaticamente i criteri personalizzati.

Inoltre, ogni volta che viene aggiunta una nuova funzionalità a Teams, il valore predefinito appropriato per l'istruzione obbligatoria dei criteri per tale caratteristica verrà aggiunto automaticamente al valore globale (impostazione predefinita a livello di organizzazione) senza richiedere alcun intervento da parte dell'amministratore. In questo modo è possibile garantire che siano attivati i criteri corretti per mantenere gli studenti al sicuro e impegnati.

> [!NOTE]
> Per un elenco dettagliato delle definizioni dei criteri applicate dalla procedura guidata, vedere [Criteri applicati dalla procedura guidata](#policies-applied-by-the-wizard) .

Ora, iniziamo!

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

<a name="polwiz_run"> </a>

Seguire questa procedura per eseguire la procedura guidata.

1. Se non si ha familiari Teams, viene avviata automaticamente la procedura guidata. In caso contrario, è possibile avviare la procedura guidata in qualsiasi momento dal dashboard. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Home** e quindi nel riquadro **Configurazione dei criteri semplici per un ambiente di apprendimento sicuro** selezionare **Configurazione rapida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot della procedura guidata nel dashboard.":::

2. Seleziona il tipo di istituto di istruzione (**Primaria o Secondaria** o **Istruzione superiore**), quindi seleziona **Avanti**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot della pagina della procedura guidata per selezionare il tipo di istituto.":::

3. Cercare e selezionare i gruppi che contengono docenti e personale, quindi selezionare **Avanti**. Se non sono ancora stati configurati gruppi per docenti e personale, [creare un gruppo](/microsoft-365/admin/create-groups/create-groups) e quindi eseguire di nuovo la procedura guidata. <br/><br/>È possibile selezionare fino a tre gruppi. Ai docenti e al personale dei gruppi selezionati verrà assegnato [un set di criteri personalizzati](#policies-applied-by-the-wizard) su misura per le loro esigenze. Tenere presente che questo set di criteri è separato dai criteri applicati agli studenti.

    :::image type="content" source="media/edu-policy-wizard-add-3-groups.png" alt-text="Screenshot della pagina della procedura guidata per selezionare i gruppi di docenti e del personale.":::

4. Rivedere le selezioni.

    :::image type="content" source="media/edu-policy-wizard-3-groups-review.png" alt-text="Screenshot della pagina della procedura guidata per rivedere le selezioni.":::

5. Selezionare **Applica** per applicare le modifiche. Il completamento dell'operazione potrebbe richiedere alcuni minuti.<br/><br/>Le definizioni dei criteri Globali (predefinite a livello di organizzazione) vengono applicate immediatamente agli studenti. Per i docenti e il personale, potrebbero essere richieste alcune ore prima che i criteri personalizzati vengano assegnati a ogni membro dei gruppi selezionati, a seconda delle dimensioni dei gruppi. Questa situazione si verifica in background, dopo aver completato correttamente questo passaggio.
6. Sei in arrivo, ma non hai ancora finito! Ci sono altri aspetti da considerare. Vedere quindi la procedura descritta nella sezione [Operazioni da eseguire dopo l'esecuzione della procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot della pagina della procedura guidata per i passaggi successivi.":::

## <a name="what-to-do-after-running-the-wizard"></a>Operazioni da eseguire dopo l'esecuzione della procedura guidata

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Passaggio 1: Rimuovere le assegnazioni dei criteri esistenti in conflitto con i criteri applicati dalla procedura guidata

> [!IMPORTANT]
> **Completare questo passaggio solo se sono stati assegnati criteri esistenti a studenti o docenti e personale *prima* di eseguire la procedura guidata**. Se non si ha familiari Teams e non si hanno criteri diversi dai criteri creati dalla procedura guidata, ignorare questa procedura e andare al passaggio 2.

In Teams, per un determinato settore dei criteri, un criterio può essere applicato a un utente nei modi seguenti:

- Assegnazione diretta all'utente
- Assegnazione a un gruppo di cui l'utente è membro
- Se all'utente non è assegnato direttamente un criterio o non è membro di un gruppo a cui è assegnato un criterio, l'utente ottiene automaticamente il criterio Globale (impostazione predefinita a livello di organizzazione)

Se esistono più assegnazioni di criteri per un utente, Teams usa l'ordine seguente per determinare quale assegnazione di criteri ha effetto. Per altre informazioni, vedere [Quali criteri hanno la precedenza](policy-assignment-overview.md#which-policy-takes-precedence) o [Regole di precedenza per i gruppi](assign-policies-users-and-groups.md#precedence-rules).

|Assegnazioni dei criteri di un utente|Criteri applicati|
|---|---|
|Criteri assegnati al gruppo: No <p> Criteri assegnati direttamente all'utente: No|Criteri predefiniti globali (a livello di organizzazione)|
|Criteri assegnati al gruppo: No <p> Criterio assegnato direttamente all'utente: Sì|Criteri assegnati direttamente all'utente|
|Criteri assegnati al gruppo: Sì <p> Criterio assegnato direttamente all'utente: Sì|Criteri assegnati direttamente all'utente|
|Criteri assegnati al gruppo: Sì <p> Criteri assegnati direttamente all'utente: No|Criteri assegnati al gruppo <p> Se l'utente è membro di più gruppi e a ogni gruppo viene assegnato un criterio della stessa area di criteri, viene applicato il criterio con la [classificazione delle assegnazioni di gruppo](assign-policies-users-and-groups.md#group-assignment-ranking) più alta.|

A causa di questo ordine, i criteri creati dalla procedura guidata non hanno effetto se un utente ha assegnazioni dirette o assegnazioni di gruppo esistenti. Questo significa che sarà necessario rimuovere le assegnazioni di criteri esistenti dall'utente in modo che il criterio applicato dalla procedura guidata abbia effetto.

Per ogni [area dei criteri applicata dalla procedura guidata](#policies-applied-by-the-wizard), eseguire le operazioni seguenti:

- Rimuovere tutti gli esercizi diretti e le attività di gruppo esistenti dagli studenti in modo che venga applicata la definizione dei criteri Globale (impostazione predefinita a livello di organizzazione) applicata dalla procedura guidata.
- Rimuovere le assegnazioni dirette in conflitto per i docenti e il personale in modo che la definizione di criteri personalizzata creata dalla procedura guidata abbia effetto. Usare la tabella precedente per determinare gli scenari applicabili. <p> Tenere presente che la procedura guidata assegna criteri ai docenti e al gruppo del personale usando una classificazione di [assegnazione di gruppo](assign-policies-users-and-groups.md#group-assignment-ranking) di 1, che è la più alta. Se a un gruppo di docenti e personale è assegnato un criterio della stessa area di criteri, i criteri esistenti vengono spostati in una classificazione inferiore e i criteri assegnati dalla procedura guidata vengono applicati.

[Altre informazioni](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) su come rimuovere i criteri assegnati direttamente agli utenti.

Ad esempio, è stato assegnato un criterio riunione direttamente ai docenti e gli studenti hanno i criteri globali (impostazione predefinita a livello di organizzazione). In questo scenario, rimuovere i criteri riunione assegnati direttamente ai docenti in modo che la definizione di criteri personalizzati per il criterio riunione creato dalla procedura guidata di dia effetto. Non è necessario eseguire alcuna operazione con i criteri di riunione globali (predefiniti a livello di organizzazione) esistenti per gli studenti perché nessun altro criterio di riunione è in conflitto con esso.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Passaggio 2: Verificare la presenza di altre misure che è possibile adottare per la sicurezza degli studenti

La procedura guidata modifica e applica automaticamente [questi criteri](#policies-applied-by-the-wizard). Esistono poche misure aggiuntive che è consigliabile adottare in base alle esigenze dell'istituto per la sicurezza.

Per altri suggerimenti sulla sicurezza, vedere [Proteggere gli studenti durante l'uso di Teams per l'apprendimento a distanza](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA).

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Passaggio 3: Controllare la disponibilità di aggiornamenti dei criteri nel Centro messaggi

Attualmente, la procedura guidata applica i criteri consigliati quando viene eseguito. È importante sapere che quando nuovi criteri diventano disponibili in Teams, le impostazioni globali (predefinite a livello di organizzazione) per la sicurezza degli studenti vengono aggiornate automaticamente dalla procedura guidata.

Controllare spesso il [Centro](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) messaggi (nel interfaccia di amministrazione di Microsoft 365) per mantenersi aggiornati sulle nuove caratteristiche e sulle relative impostazioni dei criteri e dei criteri in Teams.

## <a name="make-changes-in-the-wizard"></a>Apportare modifiche nella procedura guidata

<a name="polwiz_change"> </a>

Se è necessario apportare modifiche dopo aver eseguito la procedura guidata, è possibile eseguirla di nuovo e modificare le selezioni.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Home** e quindi nel riquadro **Configurazione dei criteri semplici per un ambiente di apprendimento sicuro** selezionare **Cambia**.
2. Da qui, continuare in ogni pagina della procedura guidata per apportare le modifiche. È possibile cambiare il tipo di istituto, i gruppi di docenti e personale a cui assegnare i criteri o entrambi.

La tabella seguente riepiloga cosa accade quando si apporta una modifica alla procedura guidata.

|Tipo di modifica|Comportamento dei criteri|
|---|---|
|Modificare sia il tipo di istituto di istruzione che i docenti e i gruppi del personale|<ul><li>**Studenti**: le definizioni dei criteri globali (predefinite a livello di organizzazione) basate sul nuovo tipo di istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale**: viene creato e assegnato un set di definizioni di criteri personalizzati basate sul nuovo tipo di istituto di istruzione ai nuovi docenti e gruppi del personale. Le definizioni dei criteri personalizzati precedenti vengono rimosse dai docenti e dai gruppi del personale precedenti.</li></ul>|
|Modificare solo il tipo di istituto di istruzione|<ul><li>**Studenti**: le definizioni dei criteri globali (predefinite a livello di organizzazione) basate sul nuovo tipo di istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale**: viene creato e assegnato un set di definizioni di criteri personalizzati basate sul nuovo tipo di istituto di istruzione ai docenti e ai gruppi del personale. Le definizioni dei criteri personalizzati create per il tipo di istituto di istruzione precedente vengono rimosse dai docenti e dai gruppi del personale.</li></ul>|
|Modificare solo i docenti e i gruppi del personale|<ul><li>**Studenti**: nessuna modifica alle definizioni dei criteri globali (predefinite a livello di organizzazione) applicate agli studenti.</li><li>**Docenti e personale**: le definizioni dei criteri personalizzati vengono assegnate ai nuovi docenti e ai gruppi del personale e rimosse dai docenti e dai gruppi del personale precedenti.</li></ul>|

## <a name="policies-applied-by-the-wizard"></a>Criteri applicati dalla procedura guidata

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Aree politiche

Ecco le aree dei criteri e i nomi dei criteri corrispondenti coperti dalla procedura guidata. Per trovare questi criteri, passare all'interfaccia di amministrazione di Microsoft Teams e quindi nella barra di spostamento sinistra passare a ogni pagina dell'area dei criteri.

#### <a name="students"></a>[**Studenti**](#tab/students/)

|Area dei criteri|Nome del criterio primario o secondario|Nome della politica dell'istruzione superiore|
|---|---|---|
|Criteri di team|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criterio di riunione|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criteri per gli eventi live|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criteri di configurazione delle app|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criteri di autorizzazione per le app|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criteri di messaggistica|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|
|Criteri di chiamata|Globale (impostazione predefinita a livello di organizzazione)|Globale (impostazione predefinita a livello di organizzazione)|

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educators/)

|Area dei criteri|Nome del criterio primario o secondario|Nome della politica dell'istruzione superiore|
|---|---|---|
|Criteri di team|Docenti e personale primario o secondario - Teams|Docenti e personale didattico dell'istruzione superiore - Teams|
|Criterio di riunione|Docenti e personale primario o secondario - Riunione|Docenti e personale didattico dell'istruzione superiore - Riunione|
|Criteri per gli eventi live|Docenti e personale primario o secondario - Eventi live|Docenti e personale didattico dell'istruzione superiore - Eventi live|
|Criteri di messaggistica|Docenti e personale primario o secondario - Messaggistica|Docenti e personale didattico dell'istruzione superiore - Messaggistica|
|Criteri di chiamata|Docenti e personale primario o secondario - Chiamate|Docenti e personale didattico dell'istruzione superiore - Chiamate|

### <a name="policy-settings"></a>Impostazioni dei criteri

Ecco un riepilogo delle impostazioni applicate dalla procedura guidata per ogni area dei criteri.

> [!NOTE]
> Solo i proprietari del team possono creare canali condivisi.<br><br>I canali condivisi con altre organizzazioni richiedono la configurazione della [connessione diretta B2B di Azure AD](/azure/active-directory/external-identities/b2b-direct-connect-overview) , disabilitata per impostazione predefinita. Per abilitare questa caratteristica, vedere [Collaborare con partecipanti esterni in un canale](/microsoft-365/solutions/collaborate-teams-direct-connect) .

#### <a name="students"></a>[**Studenti**](#tab/student-settings/)

Ecco un elenco delle definizioni dei criteri globali (predefinite a livello di organizzazione) modificate dalla procedura guidata e applicate agli studenti.

|Area dei criteri|Sotto-area|Impostazione dei criteri|Primario o secondario|Istruzione superiore|
|---|---|---|---|---|
|Criteri di team||Creare canali privati|Disattivato|Attivato|
|||Creare canali condivisi|Attivato|Attivato|
|||Condividere un canale con partecipanti esterni|Attivato|Attivato|
|||Partecipare a un canale condiviso esterno|Attivato|Attivato|
|Criteri per le riunioni|Generale|Consenti l'uso di Riunione immediata nei canali|Disattivato|Attivato|
|||Consenti il componente aggiuntivo per Outlook|Disattivato|Attivato|
|||Consenti la pianificazione delle riunioni di canale|Disattivato|Attivato|
|||Consenti la pianificazione di riunioni private|Disattivato|Attivato|
|||Consenti registrazione riunione|Attivato|Attivato|
|||Who possibile registrarsi|Tutti gli utenti dell'organizzazione|Tutti gli utenti dell'organizzazione|
||Audio & video|Trascrizione|Attivato|Attivato|
|||Registrazione cloud|Disattivato|Attivato|
|||Modalità per audio IP|Audio in uscita e in arrivo abilitato|Audio in uscita e in arrivo abilitato|
|||Modalità per video IP|Video in uscita e in arrivo abilitato|Video in uscita e in arrivo abilitato|
|||Video IP|Attivato|Attivato|
|||Consenti streaming NDI|Disattivato|Disattivato|
|||Velocità in bit supporto (KB)|50,000|50,000|
||Condivisione di contenuti|Modalità condivisione schermo|Schermo intero|Schermo intero|
|||Consenti a un partecipante di fornire o richiedere il controllo|Attivato|Attivato|
|||Consenti a un partecipante esterno di fornire o richiedere il controllo|Attivato|Attivato|
|||condivisione PowerPoint|Attivato|Attivato|
|||Whiteboard|Attivato|Attivato|
|||Note condivise|Attivato|Attivato|
||Partecipanti & guest|Consenti alle persone anonime di avviare una riunione|Disattivato|Attivato|
|||Ruoli con diritti di relatore nelle riunioni|TuttiUserOverride|TuttiUserOverride|
|||Ammetti automaticamente le persone|EveryoneInCompany|EveryoneInCompany|
|||Consenti agli utenti che chiamano di ignorare la sala di attesa|Disattivato|Disattivato|
|||Riunione immediata in riunioni private|Disattivato|Attivato|
|||Sottotitoli in tempo reale|Disabilitato ma l'utente può ignorare|Disabilitato ma l'utente può ignorare|
|||Chattare nelle riunioni|Attivato|Attivato|
|Criteri per gli eventi live||Pianificazione di eventi live|Disattivato|Disattivato|
|||Trascrizione per i partecipanti|Attivato|Attivato|
|||Chi può aggiungere eventi live pianificati|Tutti gli utenti dell'organizzazione|Tutti gli utenti dell'organizzazione|
|||Who possibile registrare un evento|Sempre|Sempre|
|Criteri di messaggistica||I proprietari possono eliminare i messaggi inviati|Disattivato|Attivato|
|||Eliminare i messaggi inviati|Disattivato|Attivato|
|||Modificare i messaggi inviati|Disattivato|Attivato|
|||Conferme di lettura|Controllo dell'utente|Controllo dell'utente|
|||Chat|Disattivato|Attivato|
|||Giphy nelle conversazioni|Disattivato|Attivato|
|||Valutazione del contenuto Giphy|Rigorosa|Rigorosa|
|||Meme nelle conversazioni|Attivato|Attivato|
|||Adesivi nelle conversazioni|Attivato|Attivato|
|||Anteprime degli URL|Attivato|Attivato|
|||Tradurre messaggi|Attivato|Attivato|
|||Strumento di lettura immersiva per i messaggi|Attivato|Attivato|
|||Invio di messaggi urgenti con notifiche priorità|Disattivato|Attivato|
|||Creare messaggi vocali|Consentito nelle chat e nei canali|Consentito nelle chat e nei canali|
|||Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti|Abilitata|Abilitata|
|||Rimuovere utenti dalle chat di gruppo|Disattivato|Attivato|
|Criteri di autorizzazione per le app||App Microsoft|Bloccare app specifiche e consentire a tutti gli altri > Walkie-talkie bloccato|Consenti tutte le app|
|||App di terze parti|Consenti tutte le app|Consenti tutte le app|
|||App personalizzate|Consenti tutte le app|Consenti tutte le app|
|Criteri di configurazione delle app||Upload app personalizzate|Disattivato|Disattivato|
|||Aggiunta da parte dell'utente|Attivato|Attivato|
|||App installate|Nessuno|Nessuno|
|||App aggiunte|Attività, Calendario Teams|Attività, Chat, Teams, Calendario, Chiamate, File
|Criteri di chiamata||Effettuare chiamate private|Disattivato|Attivato|
|||Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione|Disattivato|Attivato|
|||Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni|Disattivato|Attivato|
|||La segreteria telefonica è disponibile per il routing delle chiamate in ingresso|Controllo dell'utente|Controllo dell'utente|
|||Le chiamate in ingresso possono essere instradate ai gruppi di chiamate|Disattivato|Attivato|
|||Consenti delega per le chiamate in ingresso e in uscita|Disattivato|Attivato|
|||Evitare il bypass a pagamento e inviare chiamate tramite PSTN|Disattivato|Disattivato|
|||Occupato è disponibile durante una chiamata|Disattivato|Disattivato|
|||Consenti chiamate PSTN Web|Disattivato|Attivato|

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educator-settings/)

Ecco un elenco delle definizioni dei criteri personalizzati assegnate ai docenti e ai gruppi di personale scelti nella procedura guidata.  

|Area dei criteri|Sotto-area|Impostazione dei criteri|Primario o secondario|Istruzione superiore|
|---|---|---|---|---|
|Criteri di team||Creare canali privati|Attivato|Attivato|
|||Creare canali condivisi|Attivato|Attivato|
|||Condividere un canale con partecipanti esterni|Attivato|Attivato|
|||Partecipare a un canale condiviso esterno|Attivato|Attivato|
|Criteri per le riunioni|Generale|Consenti l'uso di Riunione immediata nei canali|Attivato|Attivato|
|||Consenti il componente aggiuntivo per Outlook|Attivato|Attivato|
|||Consenti la pianificazione delle riunioni di canale|Attivato|Attivato|
|||Consenti la pianificazione di riunioni private|Attivato|Attivato|
|||Consenti registrazione riunione|Attivato|Attivato|
|||Who possibile registrarsi|Tutti gli utenti dell'organizzazione|Tutti gli utenti dell'organizzazione|
||Audio & video|Trascrizione|Attivato|Attivato|
|||Registrazione cloud|Attivato|Attivato|
|||Modalità per audio IP|Audio in uscita e in arrivo abilitato|Audio in uscita e in arrivo abilitato|
|||Modalità per video IP|Video in uscita e in arrivo abilitato|Video in uscita e in arrivo abilitato|
|||Video IP|Attivato|Attivato|
|||Consenti streaming NDI|Disattivato|Disattivato|
|||Velocità in bit supporto (KB)|50,000|50,000|
||Condivisione di contenuti|Modalità condivisione schermo|Schermo intero|Schermo intero|
|||Consenti a un partecipante di fornire o richiedere il controllo|Attivato|Attivato|
|||Consenti a un partecipante esterno di fornire o richiedere il controllo|Attivato|Attivato|
|||condivisione PowerPoint|Attivato|Attivato|
|||Whiteboard|Attivato|Attivato|
|||Note condivise|Attivato|Attivato|
||Partecipanti & guest|Consenti alle persone anonime di avviare una riunione|Attivato|Attivato|
|||Ruoli con diritti di relatore nelle riunioni|OrganizerOnlyUserOverride|OrganizerOnlyUserOverride|
|||Ammetti automaticamente le persone|OrganizerOnly|OrganizerOnly|
|||Consenti agli utenti che chiamano di ignorare la sala di attesa|Disattivato|Disattivato|
|||Riunione immediata in riunioni private|Attivato|Attivato|
|||Sottotitoli in tempo reale|Disabilitato ma l'utente può ignorare|Disabilitato ma l'utente può ignorare|
|||Chattare nelle riunioni|Attivato|Attivato|
|Criteri per gli eventi live||Pianificazione di eventi live|Attivato|Attivato|
|||Trascrizione per i partecipanti|Attivato|Attivato|
|||Chi può aggiungere eventi live pianificati|Tutti gli utenti dell'organizzazione|Tutti gli utenti dell'organizzazione|
|||Who possibile registrare un evento|Registra sempre|Registra sempre|
|Criteri di messaggistica||I proprietari possono eliminare i messaggi inviati|Attivato|Attivato|
|||Eliminare i messaggi inviati|Attivato|Attivato|
|||Modificare i messaggi inviati|Attivato|Attivato|
|||Conferme di lettura|Controllo dell'utente|Controllo dell'utente|
|||Chat|Attivato|Attivato
|||Giphy nelle conversazioni|Attivato|Attivato|
|||Valutazione del contenuto Giphy|Rigorosa|Rigorosa|
|||Meme nelle conversazioni|Attivato|Attivato|
|||Adesivi nelle conversazioni|Attivato|Attivato|
|||Anteprime degli URL|Attivato|Attivato|
|||Tradurre messaggi|Attivato|Attivato|
|||Strumento di lettura immersiva per i messaggi|Attivato|Attivato|
|||Invio di messaggi urgenti con notifiche priorità|Attivato|Attivato|
|||Creare messaggi vocali|Consentito nelle chat e nei canali|Consentito nelle chat e nei canali|
|||Nei dispositivi mobili, visualizza i canali preferiti sopra le chat recenti|Abilitata|Abilitata|
|||Rimuovere utenti dalle chat di gruppo|Attivato|Attivato|
|Criteri di chiamata||Effettuare chiamate private|Attivato|Attivato|
|||Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione|Attivato|Attivato|
|||Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni|Attivato|Attivato|
|||La segreteria telefonica è disponibile per il routing delle chiamate in ingresso|Controllo dell'utente|Controllo dell'utente|
|||Le chiamate in ingresso possono essere instradate ai gruppi di chiamate|Attivato|Attivato|
|||Consenti delega per le chiamate in ingresso e in uscita|Attivato|Attivato|
|||Evitare il bypass a pagamento e inviare chiamate tramite PSTN|Disattivato|Disattivato|
|||Occupato è disponibile durante una chiamata|Disattivato|Disattivato|
|||Consenti chiamate PSTN Web|Attivato|Attivato|

## <a name="related-topics"></a>Argomenti correlati

- [Criteri e pacchetti di criteri di Teams per l'istruzione](policy-packages-edu.md)
- [Assegnare criteri a grandi gruppi di utenti dell'istituto di istruzione](batch-group-policy-assignment-edu.md)
- [Proteggere gli studenti durante l'uso di Teams per l'apprendimento a distanza](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
