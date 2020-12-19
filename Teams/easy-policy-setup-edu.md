---
title: Teams for Education Policy Wizard per applicare facilmente i criteri per l'apprendimento sicuro
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare la procedura guidata teams per Education Policy per applicare facilmente i criteri per studenti e docenti per garantire la sicurezza dell'ambiente di apprendimento.
f1keywords: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6480eb0ea698a783bbd231bacf2d6d1c23c7b2be
ms.sourcegitcommit: 9c1f3a72fb166b49a4b68bcdb9a2868bf86ca680
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718610"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Usare la procedura guidata teams per Education Policy per applicare facilmente i criteri per un ambiente di apprendimento sicuro

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Panoramica

La procedura guidata Microsoft teams per Education Policy semplifica la gestione dei criteri per studenti e docenti. Usalo per applicare in modo semplice e rapido il più importante set di criteri pertinenti per creare un'esperienza di apprendimento sicura e produttiva.

I criteri in team consentono di controllare il funzionamento dei team nell'ambiente e le caratteristiche disponibili per gli utenti. Ad esempio, esistono criteri per la chiamata, criteri per le riunioni e criteri di messaggistica, per citarne alcuni e ogni area dei criteri può essere personalizzata per soddisfare le esigenze dell'organizzazione.

Per mantenere un ambiente di apprendimento sicuro e focalizzato, è importante impostare i criteri per controllare cosa possono fare gli studenti in teams. Ad esempio, puoi usare i criteri per controllare chi può usare la chat privata e le chiamate private, che possono pianificare le riunioni e quali tipi di contenuto è possibile condividere. È anche possibile usare i criteri per attivare le caratteristiche dei team che arricchiscono l'esperienza di apprendimento.

I criteri devono essere regolati sia per studenti che per educatori per garantire la sicurezza dell'esperienza di apprendimento. I criteri per gli studenti devono essere più restrittivi per ridurre il rischio di ricevere livelli di accesso inappropriati. Gli insegnanti e il personale hanno bisogno di un set di criteri distinto che possa essere più permissivo per consentire loro di avere successo. Ad esempio, Consenti agli educatori di pianificare le riunioni e impedire agli studenti di farlo.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Schermata della procedura guidata":::

Questo articolo illustra come eseguire la procedura guidata.

> [!IMPORTANT]
> I criteri applicati dalla procedura guidata soddisfano le esigenze della maggior parte dei team per i clienti dell'Education. La procedura guidata regola la definizione globale (predefinita a livello di organizzazione) di un set di criteri di base con le impostazioni che consigliamo per la sicurezza degli studenti e lo applica agli studenti. La procedura guidata crea e assegna anche un set di criteri personalizzati agli insegnanti e al personale. La maggior parte dei team per i clienti dell'istruzione non deve usare altri metodi di assegnazione di criteri dopo l'applicazione della procedura guidata. Usare altri metodi di assegnazione dei criteri *solo* se si vogliono creare e gestire manualmente i criteri per studenti, docenti e personale.

## <a name="teams-for-education-policy-wizard"></a>Creazione guidata criteri team per l'istruzione

<a name="polwiz_intro"> </a>

La procedura guidata applica un set di definizioni di criteri principali agli studenti e un set distinto di definizioni di criteri di base per gli insegnanti e il personale, con impostazioni appropriate per ogni. Ecco cosa succede quando si esegue la procedura guidata.

La procedura guidata Configura i criteri basati sul tipo di Istituto di istruzione (**primario o secondario** o **superiore**). Si seleziona il tipo di Istituto e la procedura guidata esegue le operazioni seguenti:

- **Studenti**: la procedura guidata regola la definizione dei criteri globale (a livello di organizzazione predefinita) di ogni area di criteri coperta dalla procedura guidata con le nuove impostazioni predefinite appropriate per garantire la sicurezza degli studenti. In questo modo, gli studenti correnti e tutti i nuovi studenti ottengono il set di criteri più restrittivo.
- **Docenti e personale**: la procedura guidata crea un set di definizioni di criteri personalizzati per ogni area dei criteri coperta dalla procedura guidata, con impostazioni personalizzate per le esigenze di docenti e personale. Assegna quindi le definizioni dei criteri al gruppo di docenti e personale scelto. In questo modo, gli educatori e il personale ottengono un set di criteri più permissivo per consentire loro di avere successo.

È sufficiente eseguire la procedura guidata una sola volta. I nuovi studenti ottengono automaticamente le definizioni dei criteri globali (a livello di organizzazione) applicate dalla procedura guidata e il nuovo personale aggiunto al gruppo selezionato viene assegnato automaticamente ai criteri personalizzati.

> [!NOTE]
> Vedere [i criteri applicati dalla procedura guidata](#policies-applied-by-the-wizard) per un elenco dettagliato delle definizioni dei criteri applicate dalla procedura guidata.

Ora cominciamo.

## <a name="run-the-wizard"></a>Eseguire la procedura guidata

<a name="polwiz_run"> </a>

Seguire questa procedura per eseguire la procedura guidata.

1. Se non si conosce team, viene avviata automaticamente la procedura guidata. In caso contrario, è possibile avviare la procedura guidata in qualsiasi momento dal dashboard. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Dashboard** e quindi, nella sezione **configurazione dei criteri per un riquadro dell'ambiente di apprendimento sicuro** , seleziona **configurazione rapida**.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot della procedura guidata nel dashboard":::

2. Selezionare il tipo di Istituto di istruzione (**primario o secondario** o **superiore**) e quindi selezionare **Avanti**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot della pagina nella procedura guidata per selezionare il tipo di Istituto":::

3. Cercare e selezionare un gruppo che contiene gli insegnanti e il personale, quindi selezionare **Avanti**. Se non sono ancora stati configurati gruppi per i docenti e il personale, [creare un gruppo](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)e quindi eseguire di nuovo la procedura guidata. <br/><br/>Al momento, è possibile selezionare un solo gruppo. Gli insegnanti e il personale del gruppo selezionato verranno assegnati a [un set di criteri personalizzati](#policies-applied-by-the-wizard) adatti alle proprie esigenze. Tieni presente che questo set di criteri è separato dai criteri applicati agli studenti.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Screenshot della pagina nella procedura guidata per selezionare l'educatore e il gruppo del personale":::

4. Esaminare le selezioni.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Screenshot della pagina nella procedura guidata per rivedere le selezioni":::

5. Selezionare **applica** per applicare le modifiche. Il completamento può richiedere alcuni minuti.<br/><br/>Le definizioni dei criteri globali (predefinito per l'intera organizzazione) vengono applicate immediatamente agli studenti. Per gli insegnanti e il personale, potrebbero essere necessarie poche ore per assegnare i criteri personalizzati a ogni membro del gruppo selezionato, a seconda delle dimensioni del gruppo. Questo accade in background, dopo aver completato questo passaggio.
6. Si sta arrivando, ma non si è ancora fatto! Ci sono altri aspetti da considerare. Esaminare quindi la procedura descritta nella sezione [cosa fare dopo aver eseguito la procedura guidata](#what-to-do-after-running-the-wizard) di questo articolo.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot della pagina nella procedura guidata per i passaggi successivi":::

## <a name="what-to-do-after-running-the-wizard"></a>Cosa fare dopo aver eseguito la procedura guidata

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Passaggio 1: rimuovere le assegnazioni dei criteri esistenti in conflitto con i criteri applicati dalla procedura guidata

> [!IMPORTANT]
> **Completare questo passaggio solo se sono stati assegnati criteri esistenti a studenti o docenti e personale *prima* di eseguire la procedura guidata**. Se non si dispone di criteri esistenti diversi da quelli creati dalla procedura guidata, saltare questo e passare al passaggio 2.

In teams, per una determinata area dei criteri, un criterio può essere applicato a un utente nei modi seguenti:

- Assegnazione diretta all'utente
- Assegnazione a un gruppo a cui l'utente fa parte
- Se l'utente non ha un criterio assegnato direttamente o non è un membro di un gruppo a cui è assegnato un criterio, l'utente ottiene automaticamente il criterio globale (a livello di organizzazione)

Se per un utente sono presenti più di una di queste assegnazioni di criteri, teams USA l'ordine seguente per determinare l'assegnazione di criteri. Per altre info, Vedi [quali criteri hanno la precedenza?](assign-policies.md#which-policy-takes-precedence) e [regole di precedenza](assign-policies.md#precedence-rules).

|Assegnazioni dei criteri di un utente|Criteri che hanno effetto |
|---------|---------|
|Criteri assegnati al gruppo: No<br/>Criteri assegnati direttamente all'utente: No    |Criteri predefiniti globali (a livello di organizzazione)      |
|Criteri assegnati al gruppo: No<br/>Criteri assegnati direttamente all'utente: Sì    |Criteri assegnati direttamente all'utente         |
|Criteri assegnati al gruppo: Sì<br/>Criteri assegnati direttamente all'utente: Sì     |Criteri assegnati direttamente all'utente         |
|Criteri assegnati al gruppo: Sì<br/>Criteri assegnati direttamente all'utente: No     |Criteri assegnati al gruppo<br/><br/>Se l'utente è un membro di più gruppi e a ogni gruppo viene assegnato un criterio della stessa area dei criteri, il criterio con la [classificazione delle assegnazioni di gruppo](assign-policies.md#group-assignment-ranking) più alto diventa effettivo.       |

A causa di questo ordine, i criteri creati dalla procedura guidata non avranno effetto se un utente ha assegnazioni dirette o assegnazioni di gruppo esistenti. Questo significa che dovrai rimuovere le assegnazioni dei criteri esistenti dall'utente in modo che il criterio applicato dalla procedura guidata abbia effetto.

Per ogni [area dei criteri applicata dalla procedura guidata](#policies-applied-by-the-wizard), eseguire le operazioni seguenti:

- Rimuovere tutte le assegnazioni dirette esistenti e le assegnazioni di gruppo dagli studenti in modo che la definizione dei criteri globale (a livello di organizzazione) applicata dalla procedura guidata abbia effetto.
- Rimuovere eventuali assegnazioni dirette in conflitto per gli insegnanti e il personale in modo che la definizione dei criteri personalizzata creata dalla procedura guidata abbia effetto. Usare la tabella precedente per determinare gli scenari che si applicano all'utente. <br/><br/>Tieni presente che la procedura guidata assegna criteri agli educatori e al gruppo di personale usando una [classificazione di assegnazione di gruppo](assign-policies.md#group-assignment-ranking) di 1, che è la classificazione più alta. Se gli insegnanti e il gruppo del personale hanno un criterio esistente della stessa area criteri assegnata, il criterio esistente viene spostato in una classificazione inferiore e i criteri assegnati dalla procedura guidata sono effettivi.

Leggi [altre](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) informazioni su come rimuovere i criteri assegnati direttamente agli utenti.

Ad esempio, è stato assegnato un criterio di riunione direttamente agli educatori e gli studenti hanno il criterio di riunione globale (predefinito a livello di organizzazione). In questo scenario, Rimuovi i criteri della riunione assegnati direttamente agli insegnanti in modo che la definizione dei criteri personalizzata per il criterio di riunione creata dalla procedura guidata diventi effettiva. Non è necessario eseguire alcuna operazione con il criterio di riunione globale (predefinito a livello di organizzazione) esistente per gli studenti perché nessun altro conflitto tra le riunioni.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Passaggio 2: verificare se sono disponibili altre misure che è possibile eseguire per la sicurezza degli studenti

La procedura guidata regola e applica automaticamente [questi criteri](#policies-applied-by-the-wizard). Ci sono alcune misure aggiuntive che potresti voler prendere in base alle esigenze dell'Istituto per mantenerle al sicuro.

Vedere [mantenere gli studenti al sicuro durante l'uso di team per l'apprendimento a distanza](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) per ulteriori raccomandazioni sulla sicurezza.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Passaggio 3: controllare il centro messaggi per gli aggiornamenti dei criteri

Al momento, la procedura guidata applica i criteri consigliati durante l'esecuzione. È importante sapere che man mano che i nuovi criteri diventano disponibili in teams, le impostazioni globali (predefinite a livello di organizzazione) per la sicurezza degli studenti non vengono aggiunte automaticamente dalla procedura guidata. Questa funzionalità sarà disponibile in una versione futura.

Fino a quando non è disponibile questa funzionalità, selezionare il [centro messaggi](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (nell'interfaccia di amministrazione di Microsoft 365) per mantenersi aggiornati sui nuovi criteri e sulle impostazioni dei criteri in teams. Man mano che le nuove caratteristiche diventano disponibili, potrebbe essere necessario aggiornare manualmente i criteri per garantire la sicurezza dell'ambiente di apprendimento.

## <a name="make-changes-in-the-wizard"></a>Apportare modifiche alla procedura guidata

<a name="polwiz_change"> </a>

Se è necessario apportare modifiche dopo l'esecuzione della procedura guidata, è possibile eseguirla di nuovo e modificare le selezioni.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams passare a **Dashboard** e quindi, nella sezione **configurazione dei criteri per un riquadro ambiente di apprendimento sicuro** , selezionare **Cambia**.
2. Da qui continuare in ogni pagina della procedura guidata per apportare le modifiche desiderate. È possibile modificare il tipo di Istituto, il gruppo di docenti e il personale a cui si vogliono assegnare i criteri o entrambi.

La tabella seguente riepiloga il risultato che si verifica quando si apporta una modifica nella procedura guidata.

|Tipo di modifica  |Comportamento dei criteri  |
|---------|---------|
|Cambiare sia il tipo di istituto scolastico che gli insegnanti e il gruppo di collaboratori    |<ul><li>**Studenti**: le definizioni dei criteri globali (a livello di organizzazione) basate sul nuovo tipo di Istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale**: viene creato un set di definizioni di criteri personalizzate basato sul nuovo tipo di Istituto di istruzione e viene assegnato al nuovo gruppo di docenti e membri del personale. Le definizioni di criteri personalizzate precedenti vengono rimosse dagli insegnanti e dal gruppo di membri del personale precedenti.</li></ul>    |
|Modificare solo il tipo di Istituto di istruzione    |<ul><li>**Studenti**: le definizioni dei criteri globali (a livello di organizzazione) basate sul nuovo tipo di Istituto di istruzione vengono applicate agli studenti.</li><li>**Docenti e personale**: una serie di definizioni di criteri personalizzate basate sul nuovo tipo di Istituto di istruzione viene creata e assegnata agli insegnanti e al gruppo di personale. Le definizioni di criteri personalizzate create per il tipo di istituto scolastico precedente vengono rimosse dal gruppo di docenti e personale.</li></ul>         |
|Modificare solo gli insegnanti e il gruppo di collaboratori   |<ul><li>**Studenti**: nessuna modifica alle definizioni dei criteri globali (a livello di organizzazione) applicate agli studenti.</li><li>**Docenti e personale**: le definizioni di criteri personalizzate vengono assegnate ai nuovi educatori e al gruppo di personale e rimossi dal gruppo di docenti e membri del personale precedente.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Criteri applicati dalla procedura guidata

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Aree di criteri

Ecco le aree dei criteri e i corrispondenti nomi dei criteri coperti dalla procedura guidata. Per trovare questi criteri, accedere all'interfaccia di amministrazione di Microsoft teams, quindi nella barra di spostamento sinistra passa a ogni pagina dell'area dei criteri.

#### <a name="students"></a>[**Studenti**](#tab/students/)

|Area dei criteri  |Nome dei criteri primari o secondari |Nome della politica per l'istruzione superiore  |
|---------|---------|---------|
|Criteri di team    |Globale (impostazione predefinita a livello di organizzazione)         |Globale (impostazione predefinita a livello di organizzazione)           |
|Criterio di riunione    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri per gli eventi live     |Globale (impostazione predefinita a livello di organizzazione)          |  Globale (impostazione predefinita a livello di organizzazione)          |
|Criteri di configurazione dell'app     |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di autorizzazione delle app    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di messaggistica     |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |
|Criteri di chiamata    |Globale (impostazione predefinita a livello di organizzazione)           |Globale (impostazione predefinita a livello di organizzazione)           |

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educators/)

|Area dei criteri  |Nome dei criteri primari o secondari |Nome della politica per l'istruzione superiore |
|---------|---------|---------|
|Criteri di team   |Educatori primari o secondari e staff-teams         |Insegnanti di istruzione superiore e staff-teams         |
|Criterio di riunione    |Educatori primari o secondari e riunioni del personale         |Insegnanti di istruzione superiore e staff-meeting         |
|Criteri per gli eventi live   | Educatori primari o secondari e personale-eventi Live         |Docenti e personale dell'istruzione superiore-eventi Live         |
|Criteri di messaggistica    |Educatori primari o secondari e personale-messaggistica         | Insegnanti di istruzione superiore e personale-messaggistica         |
|Criteri di chiamata    |Educatori primari o secondari e chiamate per il personale         |Insegnanti di istruzione superiore e chiamate del personale         |

* * *

### <a name="policy-settings"></a>Impostazioni dei criteri

Ecco un riepilogo delle impostazioni applicate dalla procedura guidata per ogni area dei criteri.

#### <a name="students"></a>[**Studenti**](#tab/student-settings/)

Ecco un elenco delle definizioni di criteri globali (a livello di organizzazione) regolate dalla procedura guidata e applicate agli studenti.

|Area dei criteri |Area secondaria  |Impostazione dei criteri  |Primario o secondario |Istruzione superiore |
|---------|---------|---------|---------|---------|
|Criteri di team   |         |Creare canali privati         |Disattivato       |Attivato|
|Criteri riunioni    |Generale         |Consenti l'uso di Riunione immediata nei canali         |Disattivato      |Attivato|
|  |        |Consenti il componente aggiuntivo per Outlook         |Disattivato       |Attivato|
|  |        |Consenti la pianificazione delle riunioni di canale        |Disattivato      |Attivato|
|  |        |Consenti la pianificazione di riunioni private       |Disattivato      |Attivato|
|  |Video & audio        |Consenti la trascrizione        |Attivato       |Attivato|
|  |        |Consenti registrazione cloud         |Disattivato      |Attivato|
|  |        |Modalità per audio IP       |Audio in uscita e in arrivo abilitato        |Audio in uscita e in arrivo abilitato|
|  |        |Modalità per video IP         |Video in uscita e in arrivo abilitato     |Video in uscita e in arrivo abilitato|
|  |       |Consentire video IP         |Attivato         |Attivato|
|  |       |Consenti flusso di NDI         |Disattivato         |Disattivato|
|  |       |Velocità in bit supporto (KB)         |50.000         |50.000|
|  |Condivisione di contenuti       |Modalità di condivisione dello schermo         |Schermo intero         |Schermo intero|
|  |       |Consenti a un partecipante di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti a un partecipante esterno di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti la condivisione di PowerPoint        |Attivato         |Attivato|
|  |       |Consenti la lavagna         |Attivato         |Attivato|
|  |       |Consenti note condivise         |Attivato        |Attivato|
|  |Partecipanti & ospiti       |Consenti alle persone anonime di avviare una riunione       |Disattivato         |Attivato|
|  |       |Ruoli con diritti di relatore nelle riunioni        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Ammetti automaticamente le persone        |EveryoneInCompany|EveryoneInCompany|
|  |       |Consenti agli utenti che chiamano di ignorare la sala di attesa        |Disattivato         |Disattivato|
|  |       |Consenti l'uso di Riunione immediata nelle riunioni private        |Disattivato         |Attivato|
|  |       |Abilita i sottotitoli in tempo reale       |Disabilitato ma l'utente può eseguire l'override         |Disabilitato ma l'utente può eseguire l'override|
|  |       |Consenti l'uso della chat nelle riunioni          |Attivato         |Attivato|
|Criteri per gli eventi live  |       |Consenti la pianificazione         |Disattivato         |Disattivato|
|  |       |Consenti trascrizione per i partecipanti          |Attivato       |Attivato|
|  |       |Chi può aggiungere eventi live pianificati        |Tutti gli utenti dell'organizzazione        |Tutti gli utenti dell'organizzazione|
|  |       |Chi può registrare un evento         |Sempre         |Sempre|
|Criteri di messaggistica  |       |I proprietari possono eliminare i messaggi inviati         |Disattivato|Attivato|
|  |       |Elimina i messaggi inviati         |Disattivato         |Attivato|
|  |       |Modificare i messaggi inviati         |Disattivato         |Attivato|
|  |       |Conferme di lettura         |Utente controllato         |Utente controllato|
|  |       |Chat         |Disattivato         |Attivato|
|  |       |Usare Giphy nelle conversazioni         |Disattivato         |Attivato|
|  |       |Valutazione del contenuto di Giphy         |Restrittive dell'        |Restrittive dell'|
|  |       |Usare memi nelle conversazioni         |Attivato         |Attivato|
|  |       |Usare gli adesivi nelle conversazioni         |Attivato         |Attivato|
|  |       |Consenti anteprime URL        |Attivato         |Attivato|
|  |       |Tradurre i messaggi         |Attivato         |Attivato|
|  |       |Consentire all'utilità di lettura immersiva di visualizzare i messaggi        |Attivato      |Attivato|
|  |       |Inviare messaggi urgenti con le notifiche prioritarie  |Disattivato         |Attivato|
|  |       |Creare messaggi vocali         |Consentito in chat e canali         |Consentito in chat e canali|
|  |       |Nei dispositivi mobili, visualizzare i canali preferiti sopra le chat recenti     |Abilitata         |Abilitata|
|  |       |Rimuovere utenti dalle chat di gruppo         |Disattivato         |Attivato|
|Criteri di autorizzazione delle app  |       |App Microsoft         |Bloccare le app specifiche e consentire a tutti gli altri > walkie talkie bloccati         |Consenti tutte le app|
|  |       |App di terze parti         |Consenti tutte le app         |Consenti tutte le app|
|  |       |App personalizzate         |Consenti tutte le app         |Consenti tutte le app|
|Criteri di configurazione dell'app  |           |Caricare app personalizzate           |Disattivato         |Disattivato|
|  |       |Consentire il blocco degli utenti |Attivato         |Attivato|
|  |       |App installate         |Nessuno         |Nessuno|
|  |       |App aggiunte         |Attività, calendario, Teams         |Attività, chat, team, calendario, chiamate, file
|Criteri di chiamata  |       |Effettuare chiamate private         |Disattivato        |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione         |Disattivato         |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni         |Disattivato         |Attivato|
|  |       |La segreteria telefonica è disponibile per il routing delle chiamate in ingresso         |Utente controllato         |Utente controllato|
|  |       |Le chiamate in ingresso possono essere instradate a gruppi di chiamate         |Disattivato        |Attivato|
|  |       |Consentire la delega per le chiamate in ingresso e in uscita         |Disattivato         |Attivato|
|  |       |Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN        |Disattivato         |Disattivato|
|  |       |La disponibilità di occupato è disponibile quando è in corso una chiamata         |Disattivato         |Disattivato|
|  |       |Consenti chiamate PSTN Web         |Disattivato         |Attivato|

#### <a name="educators-and-staff"></a>[**Docenti e personale**](#tab/educator-settings/)

Ecco un elenco delle definizioni di criteri personalizzate assegnate agli insegnanti e al gruppo di collaboratori scelti nella procedura guidata.  

|Area dei criteri |Area secondaria  |Impostazione dei criteri  |Primario o secondario |Istruzione superiore |
|---------|---------|---------|---------|---------|
|Criteri di team   |         |Creare canali privati         |Attivato       |Attivato|
|Criteri riunioni    |Generale         |Consenti l'uso di Riunione immediata nei canali         |Attivato      |Attivato|
|  |        |Consenti il componente aggiuntivo per Outlook         |Attivato       |Attivato|
|  |        |Consenti la pianificazione delle riunioni di canale        |Attivato      |Attivato|
|  |        |Consenti la pianificazione di riunioni private       |Attivato      |Attivato|
|  |Video & audio        |Consenti la trascrizione        |Attivato       |Attivato|
|  |        |Consenti registrazione cloud         |Attivato      |Attivato|
|  |        |Modalità per audio IP       |Audio in uscita e in arrivo abilitato        |Audio in uscita e in arrivo abilitato|
|  |        |Modalità per video IP         |Video in uscita e in arrivo abilitato     |Video in uscita e in arrivo abilitato|
|  |       |Consentire video IP         |Attivato         |Attivato|
|  |       |Consenti flusso di NDI         |Disattivato         |Disattivato|
|  |       |Velocità in bit supporto (KB)         |50.000         |50.000|
|  |Condivisione di contenuti       |Modalità di condivisione dello schermo         |Schermo intero         |Schermo intero|
|  |       |Consenti a un partecipante di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti a un partecipante esterno di fornire o richiedere il controllo         |Attivato         |Attivato|
|  |       |Consenti la condivisione di PowerPoint        |Attivato         |Attivato|
|  |       |Consenti la lavagna         |Attivato         |Attivato|
|  |       |Consenti note condivise         |Attivato        |Attivato|
|  |Partecipanti & ospiti       |Consenti alle persone anonime di avviare una riunione       |Attivato        |Attivato|
|  |       |Ruoli con diritti di relatore nelle riunioni        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Ammetti automaticamente le persone        |Organizzatoresolo|Organizzatoresolo|
|  |       |Consenti agli utenti che chiamano di ignorare la sala di attesa        |Disattivato         |Disattivato|
|  |       |Consenti l'uso di Riunione immediata nelle riunioni private        |Attivato         |Attivato|
|  |       |Abilita i sottotitoli in tempo reale       |Disabilitato ma l'utente può eseguire l'override         |Disabilitato ma l'utente può eseguire l'override|
|  |       |Consenti l'uso della chat nelle riunioni          |Attivato         |Attivato|
|Criteri per gli eventi live  |       |Consenti la pianificazione         |Attivato         |Attivato|
|  |       |Consenti trascrizione per i partecipanti          |Attivato       |Attivato|
|  |       |Chi può aggiungere eventi live pianificati        |Tutti gli utenti dell'organizzazione        |Tutti gli utenti dell'organizzazione|
|  |       |Chi può registrare un evento         |Registrare sempre         |Registrare sempre|
|Criteri di messaggistica  |       |I proprietari possono eliminare i messaggi inviati         |Attivato|Attivato|
|  |       |Elimina i messaggi inviati         |Attivato         |Attivato|
|  |       |Modificare i messaggi inviati         |Attivato         |Attivato|
|  |       |Conferme di lettura         |Utente controllato         |Utente controllato|
|  |       |Chat         |Attivato         |Attivato
|  |       |Usare Giphy nelle conversazioni         |Attivato        |Attivato|
|  |       |Valutazione del contenuto di Giphy         |Restrittive dell'        |Restrittive dell'|
|  |       |Usare memi nelle conversazioni         |Attivato         |Attivato|
|  |       |Usare gli adesivi nelle conversazioni         |Attivato         |Attivato|
|  |       |Consenti anteprime URL        |Attivato         |Attivato|
|  |       |Tradurre i messaggi         |Attivato         |Attivato|
|  |       |Consentire all'utilità di lettura immersiva di visualizzare i messaggi        |Attivato      |Attivato|
|  |       |Inviare messaggi urgenti con le notifiche prioritarie  |Attivato         |Attivato|
|  |       |Creare messaggi vocali         |Consentito in chat e canali         |Consentito in chat e canali|
|  |       |Nei dispositivi mobili, visualizzare i canali preferiti sopra le chat recenti     |Abilitata         |Abilitata|
|  |       |Rimuovere utenti dalle chat di gruppo         |Attivato        |Attivato|
|Criteri di chiamata  |       |Effettuare chiamate private         |Attivato       |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo alle persone dell'organizzazione         |Attivato        |Attivato|
|  |       |Inoltro di chiamata e squillo simultaneo a numeri di telefono esterni         |Attivato        |Attivato|
|  |       |La segreteria telefonica è disponibile per il routing delle chiamate in ingresso         |Utente controllato         |Utente controllato|
|  |       |Le chiamate in ingresso possono essere instradate a gruppi di chiamate         |Attivato        |Attivato|
|  |       |Consentire la delega per le chiamate in ingresso e in uscita         |Attivato         |Attivato|
|  |       |Impedire l'esclusione del pedaggio e inviare chiamate tramite la rete PSTN        |Disattivato         |Disattivato|
|  |       |La disponibilità di occupato è disponibile quando è in corso una chiamata         |Disattivato         |Disattivato|
|  |       |Consenti chiamate PSTN Web         |Attivato      |Attivato|

* * *

## <a name="related-topics"></a>Argomenti correlati

- [Criteri per i team e pacchetti di criteri per l'istruzione](policy-packages-edu.md)
- [Assegnare criteri a grandi gruppi di utenti nella tua scuola](batch-group-policy-assignment-edu.md)
- [Mantenere la sicurezza degli studenti durante l'uso di team per l'apprendimento a distanza](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
