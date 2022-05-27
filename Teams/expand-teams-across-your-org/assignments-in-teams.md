---
title: Attività per Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Informazioni su come gestire le assegnazioni nell'interfaccia di amministrazione di Microsoft Teams in Teams per l'istruzione.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed8b01b683d201bc26dec3d220c94fbc12e76f1c
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674668"
---
# <a name="assignments-in-teams-for-education"></a>Assegnare attività in Teams per l'istruzione

Le funzionalità Attività e Voti di Teams per l'istruzione consentono ai docenti di assegnare attività, lavoro o test agli studenti. I docenti possono gestire sequenze temporali degli esercizi, istruzioni, aggiungere risorse da consegnare, valutare con categorie e altro ancora. Possono anche tenere traccia dei progressi del corso e dei singoli studenti nella scheda Voti.

[Altre informazioni su Attività e voti in Teams per l'istruzione](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Per informazioni dettagliate sulle attività Teams su piattaforme diverse, vedi [Teams funzionalità per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrazioni delle assegnazioni nell'interfaccia di amministrazione di Microsoft Teams

Usando le impostazioni di amministrazione nell'interfaccia di amministrazione di Microsoft Teams, è possibile attivare o disattivare le funzionalità per i docenti all'interno dell'organizzazione e dei loro studenti. Di seguito sono riportate le impostazioni relative alle attività:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Riepilogo e-mail settimanale del tutore

I messaggi e-mail dei tutori vengono inviati ogni fine settimana ai genitori o ai tutori. Il messaggio contiene informazioni sulle attività della settimana precedente e per la prossima settimana. La sincronizzazione per genitori e tutori può essere configurata usando [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importare le informazioni di contatto dei genitori tramite la sincronizzazione di genitori e tutori in SDS. Per istruzioni su come abilitare la sincronizzazione per genitori e tutori, vedere [Abilitazione della sincronizzazione per genitori e tutori](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Attivare l'impostazione Guardian nell'interfaccia di amministrazione di Microsoft Teams, poiché l'impostazione è disattivata per impostazione predefinita. In questo modo gli insegnanti potranno inviare un riepilogo settimanale.

   > [!NOTE]
   > Gli insegnanti possono rifiutare esplicitamente il riepilogo deselezionando l'impostazione all'interno del proprio team di classe personale (**Attività Impostazioni > messaggi di posta elettronica genitori/tutori**).

Per verificare che Genitori riceverà l'e-mail, devono essere veri i tre elementi seguenti:

- Indirizzo di posta elettronica allegato al profilo degli studenti in SDS e contrassegnato come _Genitore_ o _Tutore_. Per informazioni dettagliate, vedere [Formato di file di sincronizzazione per genitori e tutori](/schooldatasync/parent-contact-sync-file-format).

- Gli studenti appartengono ad almeno una classe in cui la posta elettronica non è disabilitata dal docente nelle [impostazioni delle attività](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- I messaggi di posta elettronica conterranno informazioni sulle attività con una data di scadenza della settimana precedente o della prossima settimana.

L'impostazione predefinita per questa funzionalità è - **Disattivata**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode è una piattaforma di codifica basata su blocchi che dà vita all'informatica per tutti gli studenti.

MakeCode è un prodotto Microsoft soggetto alle [condizioni per l'utilizzo e](https://go.microsoft.com/fwlink/?LinkID=206977) alle informative [sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

L'impostazione predefinita per questa funzionalità è - **Disattivata**.

Per abilitare le assegnazioni MakeCode in Teams, passare al **centro Teams Amministrazione**, passare alla sezione **Attività** e impostare l'opzione di attivazione Codice su **Attivato**. Selezionare **Salva**. Attendere alcune ore per rendere effettive queste impostazioni.

Per altre informazioni sul funzionamento di questa funzionalità, guardare questo [video di dimostrazione](https://makecode.com/blog/teams/teams-assignments).

[Altre informazioni su MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) è un servizio di integrità accademica. Si tratta di un servizio di terze parti soggetto alle proprie condizioni e all'informativa sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

L'impostazione predefinita per questa funzionalità è - **Disattivata**.

Per abilitare Turnitin per l'organizzazione, è necessario un abbonamento Turnitin. È quindi possibile inserire le informazioni seguenti, disponibili nella console di amministrazione di Turnitin:

- **TurnitinApiKey**: GUID di 32 caratteri trovato nella console di amministrazione in Integrazioni.
- **TurnitinApiUrl**: URL HTTPS della console di amministrazione di Turnitin.

Ecco alcune istruzioni per ottenere queste informazioni.

**TurnitinApiUrl** è l'indirizzo host della console di amministrazione.
Esempio: `https://your-tenant-name.turnitin.com`

Nella console di amministrazione è possibile creare un'integrazione e una chiave API associata all'integrazione.

Seleziona **Integrazioni** dal menu laterale, quindi seleziona **Aggiungi integrazione** e assegna un nome all'integrazione.

![Screenshot che mostra l'aggiunta di una nuova integrazione.](./educationImages/Assignments_mopo_turnitin2.png)

**TurnitinApiKey** ti verrà fornito dopo aver seguito le istruzioni.
Copiare la chiave API e incollarla nell'interfaccia di amministrazione di Microsoft Teams.  Questa è l'unica volta che puoi visualizzare la chiave.

![Screenshot che mostra la copia della chiave API.](./educationImages/Assignments_mopo_turnitin3.png)

Dopo aver fatto clic sul pulsante **Salva** nell'interfaccia di amministrazione per questa impostazione, attendere alcune ore per rendere effettive queste impostazioni.

## <a name="assignments-data"></a>Dati delle assegnazioni

Le attività archivia le informazioni generate sia da insegnanti che da studenti. Tutti i dati vengono condivisi in modo condiviso tra l'insegnante e lo studente specifico per cui le informazioni sono destinate in classe. Sono presenti due archivi di questi dati, SharePoint e all'esterno di SharePoint.

>[!NOTE]
>Le stesse regole si applicano anche alle integrazioni di prima parte, ad esempio Valutazione della lettura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Dati delle assegnazioni nelle raccolte documenti di SharePoint

I file degli studenti associati a un invio per attività vengono archiviati in una raccolta documenti denominata *Lavoro degli studenti*. I file associati agli esercizi creati dai docenti e accessibili dagli studenti vengono archiviati in un'altra raccolta documenti denominata File di *classe* nel sito SharePoint corrispondente del team di classe. Le integrazioni di prima parte possono anche archiviare i dati delle attività nello stesso sito SharePoint del team di classe corrispondente (denominato: *Titolo attività + indicatore data e ora*).

#### <a name="files-associated-with-the-student"></a>File associati allo studente

Gli amministratori IT possono usare lo strumento Ricerca contenuto per cercare i file degli studenti (*Lavoro degli studenti*, *File di classe* o altri file di integrazione di prima parte) correlati agli invii di attività e file correlati agli esercizi. Ad esempio, un amministratore può cercare in tutti i siti SharePoint dell'organizzazione e usare il nome dello studente e il nome della classe o dell'attività nella query di ricerca per trovare i dati rilevanti per una richiesta dell'interessato (DSR).

#### <a name="files-associated-with-the-teacher"></a>File associati al docente

Gli amministratori IT possono usare lo strumento Ricerca contenuto per cercare i file dei docenti (*Lavoro degli studenti*, *File di classe* o altri file di integrazione di prima parte) correlati ad attività e file distribuiti agli studenti dai docenti all'interno di una classe per gli esercizi. Ad esempio, un amministratore può cercare in tutti i siti SharePoint dell'organizzazione e usare il nome del docente e il nome della classe o dell'attività nella query di ricerca per trovare i dati rilevanti per un DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Assegnazione di dati all'esterno di raccolte documenti di SharePoint

Alcuni dati correlati alle attività non vengono archiviati nel sito SharePoint del team di classe, il che significa che non è individuabile con Ricerca contenuto. Ciò include:

- Voti degli studenti e feedback del docente
- L'elenco dei documenti inviati per un'attività da ogni studente
- Dettagli dell'attività, ad esempio Scadenza e così via.
- Dati di integrazione di prima parte come i passaggi di valutazione della lettura o i dati di pronuncia degli studenti

Per questo tipo di dati, un amministratore IT o un proprietario dei dati, ad esempio un insegnante, potrebbe dover partecipare all'attività nel team di classe per trovare i dati rilevanti per un DSR. L'amministratore può aggiungersi come proprietario alla classe e visualizzare tutte le attività per il team di classe.

>[!NOTE]
>Se uno studente non fa più parte della classe, i dati potrebbero essere ancora presenti nella classe perché *non sono più iscritti*. Lo studente dovrà fornire all'amministratore del tenant l'elenco di tali classi di cui ha mai fatto parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Esportare in blocco i dati delle assegnazioni all'esterno delle raccolte documenti di SharePoint

#### <a name="for-a-student"></a>Per uno studente

Per esportare in blocco i dati di un singolo studente, prima di rimuovere lo studente dalle classi di cui fa parte, [eseguire lo script](/microsoft-365/education/deploy/configure-assignments-for-teams) e fornire il ``userId``. Se lo studente è stato rimosso dal sito, l'amministratore può aggiungerlo di nuovo alla classe prima di eseguire lo script oppure l'amministratore può fornire il ``userId`` e di ``classId`` cui lo studente ha mai fatto parte.

I dati sugli invii degli studenti verranno esportati.

#### <a name="for-a-teacher"></a>Per un insegnante

L'esportazione in blocco dei dati degli esercizi funziona allo stesso modo per uno studente, ma tutti gli invii a cui ha accesso il docente verranno esportati.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Eliminare in blocco i dati delle assegnazioni all'esterno di SharePoint raccolte documenti

#### <a name="for-a-student"></a>Per uno studente

Per eliminare in blocco i dati di un singolo studente, prima di rimuovere lo studente dalle classi di cui fa parte, [eseguire lo script](/microsoft-365/education/deploy/configure-assignments-for-teams) e fornire il ``userId``. Se lo studente è stato rimosso dal sito, l'amministratore può aggiungerlo di nuovo alla classe prima di eseguire lo script oppure l'amministratore può fornire il ``userId`` e di ``classId`` cui lo studente ha mai fatto parte.

L'offerta di un ``ClassId`` consentirà all'amministratore di eliminare solo le informazioni relative allo studente da una classe specifica.

#### <a name="for-a-teacher"></a>Per un insegnante

Poiché i dati di un'attività per un insegnante sono condivisi in tutta la classe, non esiste un'opzione di eliminazione in blocco. L'amministratore può invece aggiungersi alla classe, passare all'app ed eliminare l'attività.

Per altre informazioni, vedere [Configurare le assegnazioni per Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Rimozione di attività e voti

È anche possibile usare i criteri di Teams per rimuovere attività e voti per un utente specifico o per l'intero tenant.

Per rimuovere attività e voti per un singolo utente, passare al **Centro Teams Amministrazione** e passare alle **app Teams >** criteri di autorizzazione per creare una nuova definizione di criteri di autorizzazione per le app.  Quando crei la nuova definizione di criteri, imposta il criterio **app Microsoft** su _Blocca app specifiche e consenti a tutte le altre_ e aggiungi **Attività** all'elenco delle applicazioni bloccate. Dopo aver salvato la nuova definizione dei criteri, assegnarla agli utenti appropriati.

Per rimuovere attività e voti per l'intero tenant, vai al **Centro Teams Amministrazione**, passa alle **app Teams > Gestisci app** e cerca e seleziona **Attività** nell'elenco delle applicazioni. Modificare l'impostazione dello stato nella pagina delle impostazioni dell'applicazione assegnazione in _Bloccato_.

## <a name="assignments-diagnostic-tool-for-users"></a>Strumento di diagnostica delle assegnazioni per gli utenti

supporto tecnico Microsoft ha creato uno strumento per raccogliere i dati di diagnostica per consentire al team di progettazione Di Microsoft di analizzare i problemi relativi alla funzionalità Attività.

Questo strumento è accessibile all'interno di Attività su qualsiasi schermata in cui gli utenti riscontrano un problema.

Per visualizzare lo strumento di diagnostica in Teams, gli utenti possono:

- **Sul desktop e sul Web:**
  - Selezionare CTRL+/
- **Nei dispositivi mobili:**
  - Tocca lo schermo con due dita e ruota le dita di 45 gradi oppure
  - Toccare lo schermo con tre dita per 15 secondi

Una volta visualizzato lo strumento di diagnostica, gli utenti vedranno un elenco di dati che potrebbero essere necessari al supporto tecnico Microsoft.

I dati recuperati possono includere:

- ID gruppo
- ID tenant
- ID sessione
- ID assegnazione
- ID invio
- ID utente

Questi dati non vengono inviati automaticamente a Microsoft. Gli utenti devono copiare e incollare i dati in un agente del supporto tecnico Microsoft per quanto riguarda un ticket di supporto.

Se un utente recupera lo strumento di diagnostica, lo chiude, non vengono inviati dati.

Quando i dati vengono inviati a un agente del supporto tecnico Microsoft, vengono gestiti come dati di supporto ai sensi dei contratti di servizio Microsoft 365 dell'organizzazione.

Per istruzioni sull'uso di questo strumento di diagnostica che puoi condividere con docenti e studenti, vedi [Ottenere dati di diagnostica per risolvere i problemi relativi agli esercizi](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e).
