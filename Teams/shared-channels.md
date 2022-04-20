---
title: Canali condivisi in Microsoft Teams (anteprima)
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come usare e gestire i canali condivisi in Microsoft Teams (anteprima).
ms.openlocfilehash: feecbdfe45e890b1e302d49bfdcaf7b6d3e19157
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817847"
---
# <a name="shared-channels-in-microsoft-teams-preview"></a>Canali condivisi in Microsoft Teams (anteprima)

I canali condivisi in Microsoft Teams creano spazi di collaborazione dove è possibile invitare persone che non fanno parte del team. Solo gli utenti proprietari o membri del canale condiviso possono accedervi. Anche se gli utenti guest (persone con account guest di Azure Active Directory nell’organizzazione) non possono essere aggiunti a un canale condiviso, è possibile invitare le persone esterne all'organizzazione a partecipare a un canale condiviso usando connessione diretta B2B di Azure AD.

Sarebbe preferibile usare un canale condiviso quando si collabora con un gruppo di persone che sono membri di team diversi. Ad esempio, le persone dei reparti progettazione, vendite e supporto che lavorano su aspetti diversi di uno stesso progetto o prodotto potrebbero collaborare usando un canale condiviso.

Solo i membri dei canali condivisi possono visualizzare e partecipare ai canali condivisi a cui vengono aggiunti. Gli altri membri del team a cui il canale condiviso è collegato non vedranno il canale.

Quando viene creato un canale condiviso, viene collegato al team padre e non può essere spostato in un altro team. Inoltre, i canali condivisi non possono essere convertiti in canali standard e viceversa.

[Confronta i canali condivisi con altri tipi di canali](/microsoftteams/teams-channels-overview#channel-feature-comparison).

## <a name="best-practices-for-the-shared-channels-preview"></a>Procedure consigliate per l'anteprima dei canali condivisi

I canali condivisi sono in anteprima e richiedono la configurazione di [Anteprima pubblica in Microsoft Teams](/MicrosoftTeams/public-preview-doc-updates). Se si prevede di condividere i canali con altre organizzazioni, è necessario che anche queste abbiano configurato l'anteprima pubblica di Teams.

È consigliabile abilitare l'anteprima per tutti gli utenti. Gli utenti per i quali l'anteprima non è abilitata non possono creare canali condivisi, ma possono comunque essere aggiunti ai canali condivisi. L'abilitazione dell'anteprima per tutti gli utenti consente di garantire un'esperienza coerente.

## <a name="getting-started-with-shared-channels"></a>Introduzione ai canali condivisi

I canali condivisi sono abilitati per impostazione predefinita in Teams. È possibile scegliere se le persone possono creare canali condivisi, se possono condividerli con persone esterne all'organizzazione e se possono partecipare a canali condivisi esterni[creando criteri di canale](/MicrosoftTeams/teams-policies).

Se si prevede di condividere i canali con persone esterne all'organizzazione, leggere [Pianificare la collaborazione esterna](/microsoft-365/solutions/plan-external-collaboration) per importanti considerazioni sulla pianificazione.

La condivisione di canali con persone esterne all'organizzazione richiede anche la configurazione delle impostazioni di accesso tra tenant in Azure AD. Ogni organizzazione con cui si vogliono condividere i canali deve anch’essa completare questa configurazione. Per informazioni dettagliate, vedere [Collaborare con partecipanti esterni in un canale](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="shared-channel-creation"></a>Creazione di canali condivisi

Solo i proprietari del team possono creare un canale condiviso. I membri del team e gli utenti guest non possono crearli. La possibilità di creare canali condivisi può essere gestita a livello di organizzazione. Usare i [criteri](teams-policies.md) per controllare quali utenti dell'organizzazione sono autorizzati a creare canali condivisi.

La persona che crea un canale condiviso è il proprietario del canale condiviso e solo il proprietario del canale condiviso può aggiungere o rimuovere direttamente le persone da quest’ultimo. (Volendo, è possibile aggiungere più proprietari). Il proprietario di un canale condiviso può aggiungere qualsiasi utente dell'organizzazione al canale condiviso che ha creato. I membri di un canale condiviso dispongono di uno spazio di conversazione sicuro e, quando vengono aggiunti nuovi membri, possono visualizzare tutte le conversazioni del canale condiviso (anche quelle precedenti).

I proprietari del team possono visualizzare i nomi di tutti i canali condivisi nel loro team ed eliminare qualsiasi canale condiviso nel team. I proprietari del team non possono visualizzare i file in un canale condiviso o le conversazioni e l'elenco dei membri di un canale condiviso, a meno che non siano membri di tale canale condiviso.

I membri del team possono visualizzare solo i canali condivisi a cui sono stati aggiunti.

La clonazione di un team non clona i canali condivisi associati.

## <a name="shared-channel-deletion"></a>Eliminazione del canale condiviso

Il canale condiviso eliminato può essere ripristinato entro 30 giorni dall'eliminazione. Quando viene ripristinato un canale condiviso eliminato, verranno ripristinate anche tutte le appartenenze precedenti (condivisione di singoli utenti e team).

I team eliminati possono essere ripristinati entro 30 giorni dall'eliminazione. Quando un team viene eliminato, vengono eliminati anche tutti i canali condivisi. Quando un team eliminato viene ripristinato, vengono ripristinati anche tutti i canali condivisi con tutte le relazioni di condivisione.

Quando un team viene archiviato, la condivisione individuale rimane intatta, ma la condivisione con team diversi dal team padre viene rimossa. Quando viene annullata l’archiviazione del team archiviato, tutti i canali condivisi vengono ripristinati con la sola condivisione individuale.

## <a name="adding-and-removing-owners-and-members"></a>Aggiunta e rimozione di proprietari e membri

Il proprietario di un canale condiviso non può essere rimosso tramite il client di Teams se è l'ultimo proprietario di uno o più canali condivisi.

Se l'ultimo proprietario del canale condiviso lascia l'organizzazione o viene rimosso dal gruppo di Microsoft 365 associato al team, un membro del canale condiviso verrà automaticamente promosso come proprietario del canale condiviso. È consigliabile aggiungere più proprietari per evitare tale situazione.

## <a name="channel-owner-settings"></a>Impostazioni del proprietario del canale

Ogni canale condiviso ha le proprie impostazioni che possono essere gestite dal proprietario del canale, tra cui la possibilità di aggiungere e rimuovere membri, aggiungere schede e @menzioni per l'intero canale. Queste impostazioni sono indipendenti dalle impostazioni del team padre. Quando viene creato un canale condiviso, questo eredita le impostazioni del team padre, le quali possono essere modificate in seguito, indipendentemente dalle impostazioni del team padre.

Il proprietario del canale condiviso può fare clic su **Gestisci canale** e quindi usare le schede **membri** e **Impostazioni** per aggiungere o rimuovere membri e modificare le impostazioni.

## <a name="shared-channel-owner-and-member-actions"></a>Azioni del proprietario e dei membri del canale condiviso

La tabella seguente illustra le azioni che i proprietari, i membri e gli utenti guest possono eseguire nei canali condivisi.

|Azione  |Proprietario di un team|Membro di un team|Utente guest di un team|Proprietario del canale condiviso|Membro del canale condiviso|Partecipante esterno del canale condiviso|
|---------|---------|---------|---------|---------|---------|---------|
|Crea canale condiviso|Controllato dall’amministratore|Controllato dall’amministratore e dal proprietario del team|No|N/D|No|No|
|Elimina canale condiviso|Sì|No|No|Sì|No|No|
|Lascia il canale condiviso|N/D|N/D|N/D|Sì, a meno che non sia l'ultimo proprietario|Sì|Sì|
|Modifica canale condiviso|No|N/D|N/D|Sì|No|No|
|Ripristina il canale condiviso eliminato|Sì|No|No|Sì|No|No|
|Aggiungere membri|No|N/D|N/D|Sì|No|No|
|Modificare le impostazioni|No|N/D|N/D|Sì|No|No|
|Gestire schede e app|No|N/D|N/D|Sì, le app devono essere installate per il team|Controllato dal proprietario del canale|No|

## <a name="shared-channel-sharepoint-sites"></a>Siti di SharePoint del canale condiviso

Ogni canale condiviso ha [il proprio sito di SharePoint](/SharePoint/teams-connected-sites). Il sito separato serve a garantire che l'accesso ai file del canale condiviso sia limitato ai soli membri del canale condiviso. Questi siti vengono creati con una raccolta documenti per impostazione predefinita e possono essere facilmente migliorate per ottenere siti completi tramite l'[interfaccia di gestione dei siti](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Ogni sito viene creato nella stessa area geografica del sito del team padre. Questi siti semplificati hanno un ID modello personalizzato, "TEAMCHANNEL#0", per semplificare la gestione con PowerShell e API Graph. 

> [!NOTE]
> Solo le persone con autorizzazioni di proprietario o membro nel canale avranno accesso al contenuto nel sito del canale condiviso. Solo le persone con i permessi di proprietario o membro nel canale avranno accesso al contenuto nel sito del canale condiviso.

Il sito del canale condiviso sincronizza la classificazione dei dati dal sito del team padre. L'appartenenza al proprietario del sito e ai gruppi di membri viene mantenuta sincronizzata con l'appartenenza al canale condiviso. Le autorizzazioni del sito per un sito del canale condiviso non possono essere gestite in modo indipendente tramite SharePoint. 

Teams gestisce il ciclo di vita del sito del canale condiviso. Se il sito viene cancellato al di fuori di Teams, verrà ripristinato automaticamente entro quattro ore, purché il canale condiviso sia ancora attivo. Se il sito viene eliminato definitivamente, verrà eseguito il provisioning di un nuovo sito per il canale condiviso.

Se viene ripristinato un canale condiviso o un team contenente un canale condiviso, i siti verranno ripristinati con esso. Se un sito del canale condiviso viene ripristinato oltre il periodo di eliminazione temporanea di 30 giorni per il canale condiviso, il sito opererà come sito autonomo.

## <a name="shared-channel-messages"></a>Messaggi del canale condiviso

I messaggi del canale condiviso vengono archiviati in una cassetta postale di sistema dedicata associata al canale condiviso anziché alla cassetta postale di gruppo.

Per altre informazioni sull'esecuzione di una ricerca eDiscovery per i messaggi dei canali condivisi, vedere [Eseguire un'analisi eDiscovery dei contenuti in Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Considerazioni sull'accesso ai file nei canali condivisi

I file, le cartelle e i blocchi appunti di OneNote in un canale condiviso possono essere condivisi con le persone esterne al canale tramite la [Condivisione file standard di SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c).

Se a un utente viene concesso l'accesso a un file, una cartella o un blocco appunti in un canale condiviso tramite SharePoint, la rimozione dell'utente dal team o dal canale condiviso non rimuoverà l'accesso dell'utente al file, alla cartella o al blocco appunti.

Se un blocco appunti esistente viene aggiunto come scheda a un canale condiviso, l'accesso al canale condiviso non verrà modificato e il blocco appunti manterrà le autorizzazioni esistenti.

## <a name="resources-for-your-users"></a>Risorse per gli utenti

Gli articoli seguenti possono essere utili nel caso di utilizzo dei canali condivisi da parte degli utenti dell'organizzazione.

[Creare un canale condiviso in Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Condividere un canale con altre persone in Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Condividere un canale con un team](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[Perché usare un canale condiviso rispetto ad altri tipi di canale in Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Guest e canali condivisi in Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Ruoli di proprietario e membro del canale condiviso in Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels-preview"></a>Limiti per i canali condivisi (anteprima)

La tabella seguente descrive il numero massimo di canali e di membri.

|Numero massimo di...|Valore|Note|
|:---------|:----|:----|
|Membri di un team|25.000|Include tutti gli utenti del team e i membri diretti nei canali condivisi.|
|Canali condivisi per team|50|Ospitato e condiviso con il team. (Include i canali eliminati durante il periodo di ripristino di 30 giorni).|
|Teams un canale può essere condiviso con|50|Esclusione del team padre|
|Membri in un canale condiviso|1.000 membri diretti, compreso fino a 50 team. (Ogni team con cui viene condiviso il canale viene conteggiato come un membro ai fini di tale limite.)|Gli aggiornamenti in tempo reale sono disponibili solo per 25.000 utenti alla volta e solo 25.000 utenti appariranno nella lista dei canali.|

Si applicano anche le limitazioni seguenti:

- I canali condivisi supportano le schede tranne Stream, Planner e Forms.

- Le app LOB, i bot, i connettori e le estensioni dei messaggi non sono supportati per l'anteprima pubblica.

- Quando si crea un team da un team esistente, qualsiasi canale condiviso nel team esistente non verrà copiato.

- Le notifiche dai canali condivisi non sono incluse nei messaggi di posta elettronica di attività perse.

## <a name="related-topics"></a>Argomenti correlati

[Panoramica della connessione diretta B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurare le impostazioni di accesso tra tenant per la connessione diretta B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Panoramica su team e canali in Teams](teams-channels-overview.md)

[Canali privati in Microsoft Teams](/microsoftteams/private-channels)