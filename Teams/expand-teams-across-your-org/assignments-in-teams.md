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
description: Informazioni su come gestire le attività nell'Microsoft Teams di amministrazione di Teams per l'istruzione.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88414131b5ba8fee750efef8d0b6f6f5313e13fd
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363142"
---
# <a name="assignments-in-teams-for-education"></a>Assegnare attività in Teams per l'istruzione

Le funzionalità Attività e voti in Teams per l'istruzione i docenti possono assegnare attività, lavoro o quiz agli studenti. I docenti possono gestire le sequenze temporali delle assegnazioni, le istruzioni, aggiungere risorse per l'assegnazione, classificare con le rubriche e altro ancora. Possono anche tenere traccia dello stato di avanzamento della classe e dei singoli studenti nella scheda Voti.

[Altre informazioni su Attività e voti in Teams per l'istruzione](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Per informazioni dettagliate Teams attività in piattaforme diverse, vedere Teams [funzionalità per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrazioni di assegnazioni nell'interfaccia Microsoft Teams di amministrazione

Usando le impostazioni di amministrazione nell'Microsoft Teams di amministrazione, è possibile attivare o disattivare le funzionalità per i docenti all'interno dell'organizzazione e per i loro studenti. Di seguito sono riportate le impostazioni relative alle attività:

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>Digest della posta elettronica del tutore settimanale

I messaggi di posta elettronica dei tutori vengono inviati ogni fine settimana a genitori o tutori. Il messaggio di posta elettronica contiene informazioni sulle attività della settimana precedente e della settimana successiva. La sincronizzazione padre e tutore può essere impostata [usando School Data Sync](/schooldatasync/parent-contact-sync).

1. Importare le informazioni sul contatto padre tramite Parent e Guardian Sync in SDS. Per istruzioni su come abilitare la sincronizzazione padre e tutore, vedere Abilitazione [della sincronizzazione padre e tutore](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Attivare l'impostazione Guardiano nell'Microsoft Teams di amministrazione, perché l'impostazione è disattivata per impostazione predefinita. In questo modo gli insegnanti potranno inviare un riepilogo settimanale.

   > [!NOTE]
   > Gli insegnanti possono rifiutare esplicitamente il digest deselezionando l'impostazione all'interno del proprio team di classe personale (Attività Impostazioni > **e-mail genitori/tutori**).

Per verificare che i genitori otterrà il messaggio di posta elettronica, i tre elementi seguenti devono essere veri:

- Indirizzo di posta elettronica allegato al profilo dello studente in SDS e contrassegnato _come genitore_ o _tutore_. Per informazioni dettagliate, vedere [Formato di file di sincronizzazione padre e tutore](/schooldatasync/parent-contact-sync-file-format).

- Gli studenti appartengono ad almeno una classe in cui la posta elettronica non è disabilitata dal docente nelle impostazioni [dell'attività](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

- I messaggi di posta elettronica conterranno informazioni sulle attività con una data di scadenza della settimana precedente o della settimana successiva.

L'impostazione predefinita per questa funzionalità è - **Disattivato**.

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode è una piattaforma di codifica basata su blocchi che dà vita all'informatica per tutti gli studenti.

MakeCode è un prodotto Microsoft soggetto alle condizioni per l'uso [e alle](https://go.microsoft.com/fwlink/?LinkID=206977) politiche [sulla privacy microsoft](https://go.microsoft.com/fwlink/?LinkId=521839) .

L'impostazione predefinita per questa funzionalità è - **Disattivato**.

Per abilitare le assegnazioni MakeCode in Teams, passare all'interfaccia di amministrazione di **Teams**, passare alla sezione Attività e  attivare l'opzione MakeCode **.** Fare clic su **Salva**. Consentire l'applicazione di queste impostazioni per alcune ore.

Per altre informazioni sul funzionamento di questa funzionalità, guardare questa [dimostrazione video](https://makecode.com/blog/teams/teams-assignments).

[Altre informazioni su MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin è](https://www.turnitin.com/) un servizio di integrità accademica. Si tratta di un servizio di terze parti soggetto alle proprie condizioni e all'informativa sulla privacy. L'utente è responsabile dell'uso di prodotti e servizi di terze parti.

L'impostazione predefinita per questa funzionalità è - **Disattivato**.

Per abilitare Turnitin per l'organizzazione, è necessario un abbonamento Turnitin. È quindi possibile immettere le informazioni seguenti, disponibili nella console di amministrazione di Turnitin:

- **TurnitinApiKey**: si tratta di un GUID di 32 caratteri trovato nella console di amministrazione in Integrazioni.
- **TurnitinApiUrl**: URL HTTPS della console di amministrazione di Turnitin.

Ecco alcune istruzioni per ottenere queste informazioni.

**TurnitinApiUrl è** l'indirizzo host della console di amministrazione.
Esempio: `https://your-tenant-name.turnitin.com`

La console di amministrazione consente di creare un'integrazione e una chiave API associata all'integrazione.

Selezionare **Integrazioni** dal menu laterale, quindi selezionare **Aggiungi** integrazione e assegnare un nome all'integrazione.

![Screenshot che mostra l'aggiunta di una nuova integrazione.](./educationImages/Assignments_mopo_turnitin2.png)

**L'oggetto TurnitinApiKey** verrà assegnato dopo aver seguito le istruzioni visualizzate.
Copiare la chiave API e incollarla nell'Microsoft Teams di amministrazione.  Questa è l'unica volta in cui è possibile visualizzare la chiave.

![Screenshot che mostra la copia della chiave API.](./educationImages/Assignments_mopo_turnitin3.png)

Dopo aver fatto **clic sul pulsante** Salva nell'interfaccia di amministrazione per questa impostazione, consentire l'applicazione di queste impostazioni per alcune ore.

## <a name="assignments-data"></a>Dati delle assegnazioni

Le attività archiviano le informazioni generate sia da docenti che da studenti. Tutti i dati vengono condivisi in modo condiviso tra l'insegnante e lo studente specifico per cui le informazioni sono destinate in classe. Ci sono due negozi di questo tipo, SharePoint e all'esterno di SharePoint.

>[!NOTE]
>Le stesse regole si applicano anche alle integrazioni di terze parti, ad esempio l'avanzamento della lettura.

### <a name="assignments-data-in-sharepoint-document-libraries"></a>Dati delle assegnazioni nelle SharePoint documenti

I file degli studenti associati a un invio per l'attività vengono archiviati in una raccolta documenti denominata Lavoro *degli studenti*. I file associati alle attività create da docenti e accessibili dagli studenti vengono archiviati in un'altra raccolta documenti ,*denominata File di* classe, nel sito di SharePoint team di classe corrispondente. Le integrazioni di prima parte possono anche archiviare i dati delle attività nello stesso sito di SharePoint team di classe corrispondente (denominato: *Titolo attività + timestamp*).

#### <a name="files-associated-with-the-student"></a>File associati allo studente

Gli amministratori IT possono usare lo strumento Ricerca contenuto per cercare file degli *studenti (Lavoro* degli *studenti, File* di classe o altri file di integrazione di 1° parte) correlati agli invii di attività e ai file correlati alle attività. Ad esempio, un amministratore può cercare in tutti i siti di SharePoint dell'organizzazione e usare il nome dello studente e il nome della classe o dell'attività nella query di ricerca per trovare i dati rilevanti per una richiesta DSR (Data Subject Request).

#### <a name="files-associated-with-the-teacher"></a>File associati al docente

Gli amministratori IT possono usare lo strumento Ricerca contenuto per cercare i file degli *insegnanti (Lavoro* degli *studenti, File* di classe o altri file di integrazione di 1° parte) correlati alle attività, nonché i file distribuiti agli studenti dai docenti all'interno di una classe per le attività. Ad esempio, un amministratore può cercare in tutti i siti SharePoint dell'organizzazione e usare il nome del docente e il nome della classe o dell'attività nella query di ricerca per trovare i dati rilevanti per un DSR.

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>Dati delle assegnazioni all'esterno SharePoint raccolte documenti

Alcuni dati relativi alle attività non vengono archiviati nel sito SharePoint team di classe, quindi non è possibile individuarlo con Ricerca contenuto. Sono inclusi:

- Voti degli studenti e feedback del docente
- Elenco di documenti inviati per un'attività da ogni studente
- Dettagli dell'attività, ad esempio Scadenza e così via.
- Dati di integrazione di prima parte come i passaggi dello stato di avanzamento della lettura o i dati sulla pronuncia degli studenti

Per questo tipo di dati, un amministratore IT o un proprietario di dati, ad esempio un docente, potrebbe essere necessario accedere all'attività nel team di classe per trovare i dati rilevanti per un DSR. L'amministratore può aggiungersi come proprietario alla classe e visualizzare tutte le attività del team di classe.

>[!NOTE]
>Se uno studente non fa più parte della classe, i dati potrebbero essere ancora presenti nella classe come non *più iscritti*. Lo studente dovrà fornire all'amministratore del tenant l'elenco di tali classi di cui fa parte.

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>Esportare in blocco i dati delle assegnazioni all'esterno SharePoint raccolte documenti

#### <a name="for-a-student"></a>Per uno studente

Per esportare in blocco i dati di un singolo studente, prima di rimuovere lo studente dalle classi di cui fa parte, eseguire lo  [script](/microsoft-365/education/deploy/configure-assignments-for-teams) e fornire l'istruzione ``userId``. Se lo studente è stato rimosso dal sito, l'amministratore può aggiungere di nuovo lo studente alla classe prima di eseguire lo script oppure ``userId`` ``classId`` l'amministratore può fornire il e di cui lo studente ha fatto parte.

I dati sugli invii degli studenti verranno esportati.

#### <a name="for-a-teacher"></a>Per un docente

L'esportazione in blocco dei dati delle attività funziona allo stesso modo per uno studente, ma tutti gli invii a cui l'insegnante ha accesso verranno esportati.

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>Eliminare in blocco i dati delle assegnazioni all'esterno SharePoint raccolte documenti

#### <a name="for-a-student"></a>Per uno studente

Per eliminare in blocco i dati di un singolo studente, prima di rimuovere lo studente dalle classi di cui fa parte, eseguire lo [script](/microsoft-365/education/deploy/configure-assignments-for-teams) e fornire l'istruzione ``userId``. Se lo studente è stato rimosso dal sito, l'amministratore può aggiungere di nuovo lo studente alla classe prima di eseguire lo script oppure ``userId`` ``classId`` l'amministratore può fornire il e di cui lo studente ha fatto parte.

Se si specifica un ``ClassId`` , l'amministratore può eliminare solo le informazioni sullo studente da una classe specifica.

#### <a name="for-a-teacher"></a>Per un docente

Poiché i dati di un'attività per un docente vengono condivisi in tutta la classe, non esiste un'opzione di eliminazione in blocco. L'amministratore può invece aggiungersi alla classe, passare all'app ed eliminare l'attività.

Per altre informazioni,  [vedereConfigurare le assegnazioni per Teams](/microsoft-365/education/deploy/configure-assignments-for-teams).

## <a name="removing-assignments-and-grades"></a>Rimozione di attività e voti

È anche possibile usare i Teams per rimuovere assegnazioni e voti per un utente specifico o per l'intero tenant.

Per rimuovere assegnazioni e voti per un singolo utente, passare **all'interfaccia** di amministrazione di Teams e passare Teams **app >** Criteri di autorizzazione per creare una nuova definizione dei criteri di autorizzazione per le app.  Quando si crea la nuova definizione dei criteri, impostare i criteri delle  **app Microsoft** su Blocca app specifiche e consentire a tutti gli altri utenti e aggiungere Attività **all'elenco** delle applicazioni bloccate. Dopo aver salvato la nuova definizione dei criteri, assegnarla agli utenti appropriati.

Per rimuovere attività e voti per l'intero tenant, passare **all'interfaccia** di amministrazione di Teams, passare Teams **app > Gestisci app** e cercare e selezionare Attività nell'elenco delle applicazioni. Modificare l'impostazione dello stato nella pagina Impostazioni applicazione assegnazione su _Bloccato_.
