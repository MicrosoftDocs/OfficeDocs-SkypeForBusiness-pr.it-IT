---
title: Temi delle riunioni per le riunioni di Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Usando risorse aziendali approvate, come immagini e logo, per creare alcuni temi di riunione personalizzati per le riunioni di Teams all'interno dell'organizzazione.
ms.openlocfilehash: 768c589507cac3f100d2760fe6497872a7f8ee00
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800229"
---
# <a name="meeting-themes-for-teams-meetings"></a>Temi delle riunioni per le riunioni di Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

La personalizzazione nelle riunioni di Teams consente alle organizzazioni di estendere le loro identità visive nell'intera esperienza di riunione. Le immagini e i colori di un'organizzazione contribuiscono a favorire la costruzione della cultura aziendale interna e a aumentare la consapevolezza generale del marchio con gli ospiti. Con l'aiuto dei team di gestione del marchio e comunicazione aziendale di un'organizzazione, gli amministratori del tenant possono facilmente configurare e creare temi di riunione per diverse business unit e reparti all'interno di un unico tenant.
Per impostazione predefinita, gli utenti con licenza Premium di Teams a cui è stato assegnato un criterio di personalizzazione delle riunioni possono creare riunioni abilitate per i temi delle riunioni. Queste riunioni includono i temi per impostazione predefinita e chiunque partecipi alle riunioni può visualizzare i temi (inclusi gli utenti interni senza licenza, gli utenti guest e gli utenti anonimi).

> [!NOTE]
> I partecipanti che partecipano a Teams tramite l'esperienza Web non potranno vedere i temi delle riunioni.

## <a name="prerequisites"></a>Prerequisiti

Prima di configurare i temi delle riunioni in Riunioni di Teams, verificare di avere gli elementi seguenti:

- Accesso a Teams Premium SKU
- Sei un amministratore con accesso all'interfaccia di amministrazione di Teams o ti è stato assegnato un criterio di personalizzazione
- Il [logo](#adding-a-custom-logo-image), [l'immagine](#adding-a-custom-image) e il [colore](#adding-a-custom-color) personalizzati soddisfano le specifiche richieste

## <a name="setting-up-meeting-branding"></a>Configurazione della personalizzazione delle riunioni

Gli amministratori tenant possono configurare e gestire i temi delle riunioni per le riunioni di Teams nell'interfaccia di amministrazione di Teams.

### <a name="creating-a-customization-policy"></a>Creazione di criteri di personalizzazione

Per creare i temi della riunione, gli amministratori dovranno prima di tutto creare un nuovo criterio di personalizzazione delle riunioni o modificare i criteri esistenti.
Per abilitare i criteri in background personalizzati, gli amministratori eseguiranno la procedura seguente:

1. Aprire l'interfaccia di amministrazione di Teams
2. Selezionare **Riunioni** dal riquadro di spostamento
3. In **Riunioni** selezionare **Criteri di personalizzazione**
4. Selezionare un criterio esistente o crearne uno nuovo
5. All'interno dei criteri scelti, passare alla sezione **Oggetti visivi riunione personalizzati**
6. Attivare l'impostazione **Attualmente attiva** **per** abilitare l'impostazione
7. Selezionare **Salva** per abilitare i temi della riunione

> [!NOTE]
> Anche se è possibile accedere agli oggetti visivi riunione personalizzati dalla pagina Criteri riunione, è consigliabile accedervi tramite Criteri di personalizzazione per evitare di spostarsi tra i criteri predefiniti dell'organizzazione globale.

All'interno dei criteri di personalizzazione delle riunioni, gli amministratori possono iniziare a definire il proprio marchio creando un tema per la riunione.

I temi delle riunioni includono le risorse seguenti per il tema:

- Logo: immagine del logo dell'organizzazione.
- Immagine personalizzata: un'immagine del marchio dell'organizzazione (le immagini personalizzate non sono uguali agli [sfondi delle riunioni personalizzate](custom-meeting-backgrounds.md)).
- Colore personalizzato - si consiglia di utilizzare il colore principale o secondario del marchio - a seconda di quale dei migliori si adatta l'immagine del marchio e il logo.

Per creare un nuovo tema, seleziona **Aggiungi tema riunione**.

### <a name="adding-a-custom-logo-image"></a>Aggiunta di un'immagine del logo personalizzato

Riunioni di Teams supporta logo quadrati che vengono visualizzati sulle superfici chiave durante la riunione, inclusa la schermata della sala di attesa. Le immagini del logo devono soddisfare i rapporti di contrasto dell'accessibilità Microsoft (4:5:1).

I caricamenti devono attenersi ai seguenti parametri. Un amministratore può caricare solo:

- Formati di immagine PNG e JPEG per il logo.
- Immagine del logo con dimensioni massime di 5 MB.
- Immagini del logo con una dimensione minima di 576 px X 576 px.
- Solo un'immagine per tema del dispositivo.

### <a name="adding-a-custom-image"></a>Aggiunta di un'immagine personalizzata

Le riunioni di Teams supportano le immagini di un'organizzazione che scuotono la schermata delle riunioni e forniscono uno sfondo colorato alle riunioni.

> [!NOTE]
> Queste immagini non sono uguali agli [sfondi delle riunioni personalizzate](custom-meeting-backgrounds.md)

Le immagini personalizzate devono soddisfare i rapporti di contrasto di accessibilità Microsoft (4:5:1) e i caricamenti devono seguire questi parametri:

- Amministrazione possono caricare solo formati di immagine PNG e JPEG per l'immagine del marchio
- Amministrazione possibile caricare l'immagine del marchio solo con dimensioni massime di 5 MB
- Amministrazione possibile caricare l'immagine del marchio con le dimensioni seguenti:
  - Dimensioni minime: 360 px X 360 px
  - Dimensioni massime: 2048 px X 2048 px
- Amministrazione possibile caricare un minimo di 0 e un massimo di un'immagine per tema dal proprio dispositivo

### <a name="adding-a-custom-color"></a>Aggiunta di un colore personalizzato

Le riunioni di Teams supportano il colore principale o secondario di un'organizzazione nell'esperienza di riunione. È possibile immettere il valore del codice esadecimale del colore dell'organizzazione, che verrà visualizzato sulle superfici principali dell'esperienza di riunione.

> [!NOTE]
> Per supportare gli standard di accessibilità Microsoft, il colore finale generato potrebbe non corrispondere al colore del marchio.

### <a name="previewing-a-meeting-theme"></a>Anteprima del tema di una riunione

Dopo aver aggiunto le risorse della riunione, è possibile visualizzare in anteprima l'aspetto del tema prima del salvataggio.  Selezionando **Anteprima** verrà aperta la finestra di dialogo di anteprima e verrà visualizzato il tema appena definito sia per desktop che per i dispositivi mobili.

### <a name="save-meeting-theme"></a>Salvare il tema della riunione

Selezionando **Salva**, il tema della riunione viene salvato e applicato automaticamente alle riunioni. Se si seleziona **Salva e applica per un secondo momento** , il tema della riunione verrà salvato, ma non verrà applicato alle riunioni. Per applicare questo tema, selezionare **Salva** nell'autore del tema della riunione oppure usare l'interruttore **Attualmente attivo** nella tabella dei temi della riunione nella pagina dei criteri di personalizzazione.



### <a name="assigning-a-meeting-customization-policy-to-users"></a>Assegnazione di criteri di personalizzazione delle riunioni agli utenti

I criteri di personalizzazione delle riunioni possono essere assegnati a uno, molti o a un gruppo di utenti predefinito nel tenant. Assicurarsi che questi utenti abbiano una licenza Premium di Teams per usare queste funzionalità.

- Per impostazione predefinita, a tutti gli utenti con licenza viene assegnato il criterio Predefinito globale.
- I criteri di personalizzazione personalizzati sostituiscono l'impostazione predefinita globale
- A un utente con licenza può essere assegnato un solo criterio di personalizzazione

### <a name="use-cases-for-multiple-departments-or-business-units-in-one-tenant"></a>Casi d'uso per più reparti o business unit in un tenant

Alcune organizzazioni hanno più business unit con identità di marchio diverse all'interno dello stesso tenant. In questi casi, gli amministratori possono creare criteri di personalizzazione delle riunioni dedicati a ogni marchio. Possono anche assegnare un gruppo di utenti di reparto o di business unit a un criterio specifico.

#### <a name="a-use-case"></a>Un caso d'uso

Contoso Ltd. ha un singolo tenant in Microsoft Teams, contenente i profili utente di tutti i dipendenti di organizzazioni aziendali diverse. L'azienda sta cercando di adottare riunioni personalizzate con marchio in Teams per aumentare la presenza del marchio con i propri clienti e incoraggiare una cultura aziendale interna.

Contoso ha due business unit (BUs) nell'organizzazione: Contoso Technical Services e Contoso Education. Entrambe le unità BUs hanno immagini del marchio distinte e vogliono visualizzare il proprio marchio durante le riunioni interne ed esterne.

Per supportare questo caso d'uso, gli amministratori tenant possono creare due criteri di personalizzazione distinti:

- Criterio A - Contoso Technical Services: ospita il logo, l'immagine e il colore del marchio di Contoso Technical Service
- Criterio B - Contoso Education: ospita il logo, l'immagine e il colore del marchio Di Contoso Education

Possono continuare ad assegnare i dipendenti con licenza dei servizi tecnici Contoso al criterio A e i dipendenti con licenza di Contoso Education al criterio B.

## <a name="where-are-meeting-themes-visible"></a>Dove sono visibili i temi delle riunioni

Client supportati:

- Client desktop
- Android (solo versioni 11+ )
- iOS

|         | Partecipa a Launcher | Riunione pre-partecipazione | Sala d'attesa riunione | Finestra di condivisione della riunione |
| :---:          |     :---:      |         :---:  |         :---:  |         :---:  |
| **Logo**   | No | Sì| Sì| Sì|
| **Immagine**     | No | Sì| Sì| Sì|
| **Colore**     | Sì | Sì| Sì| Sì|

Logo e immagini saranno disponibili per Join Launcher negli aggiornamenti futuri.
> [!NOTE]
> La nuova esperienza di webinar userà queste funzionalità dei temi nelle riunioni. La pagina di registrazione del webinar verrà comunque utilizzata per configurare il marchio del webinar per la registrazione delle riunioni e le e-mail. Gli organizzatori della riunione possono disattivare i temi della riunione per un webinar rifiutando esplicitamente le opzioni della riunione. Scopri di più [sulla nuova esperienza di webinar](set-up-webinars.md)

### <a name="who-can-view-a-meeting-theme"></a>Chi può visualizzare il tema di una riunione

Anche se solo gli utenti con licenza a cui è assegnato un criterio di personalizzazione delle riunioni possono creare riunioni abilitate per i temi delle riunioni, chiunque può visualizzare i temi applicati a una riunione. Questi utenti includono:

- Utenti inclusi nel tenant Teams Premium con licenza
- Utenti nel tenant, senza licenza
- Guest di utenti tenant
- Utenti esterni
- Utenti anonimi

### <a name="how-to-turn-off-meeting-themes-for-a-meeting"></a>Come disattivare i temi della riunione per una riunione

Gli amministratori tenant possono consentire agli organizzatori di riunioni di disabilitare i temi della riunione per una specifica istanza della riunione. Se si disabilitano i temi della riunione, viene ripristinato il tema predefinito di Teams.

Per offrire agli organizzatori della riunione la possibilità di disabilitare i temi della riunione:

1. Passare al **criterio di personalizzazione delle riunioni**.
1. Attivare o disattivare l'impostazione **"Tema riunione" che consente agli organizzatori di disattivare il tema della riunione per riunioni specifiche**.

Gli organizzatori delle riunioni possono disattivare i temi della riunione:

1. Passare al menu **Opzioni riunione** per un'istanza della riunione.
1. Disattivazione dell'opzione **Permetti agli organizzatori di disattivare il tema della riunione**.

> [!NOTE]
>
> - Per le riunioni ricorrenti o le serie, l'opzione della riunione verrà applicata per ogni istanza della riunione.
> - I temi delle riunioni non verranno disabilitati per le riunioni in corso. Per applicare le modifiche, è necessario terminare la chiamata e riavviare la riunione.

## <a name="best-practices-for-meeting-themes"></a>Procedure consigliate per i temi delle riunioni

- Usare solo le risorse di immagine ufficiali dell'organizzazione. Non usare contenuto di immagini di cui non sei proprietario.
- Collabora con il tuo marchio e il team di marketing per assicurarti che le risorse e i colori delle immagini seguano insieme le linee guida del marchio della tua organizzazione.
- Assicurati di usare immagini del logo di alta qualità, visibili su dispositivi con schermo di piccole e grandi dimensioni.
- I colori generati nell'app Teams potrebbero essere diversi dai colori del marchio. Questo processo è stato creato per garantire il soddisfarsi degli standard di accessibilità Microsoft.
- Gli utenti con impostazioni del dispositivo a contrasto elevato non vedranno i temi delle riunioni.

### <a name="accessibility"></a>Accessibilità

Ecco alcuni punti per garantire che i requisiti di accessibilità siano soddisfatti:

- Segui i modelli e la struttura dell'interfaccia utente esistenti: la struttura e il testo correnti sullo schermo non vengono modificati con questa funzionalità.
- Rapporto contrasto immagine: le risorse dell'immagine sono necessarie per soddisfare il rapporto di contrasto dei colori 4:5:1.  
- Supporto per la generazione di colori accessibile: calcola l'output di colore accessibile che corrisponde più vicino all'input del colore del marchio mantenendo gli standard di accessibilità Microsoft  
- Supporto del contrasto elevato: per gli utenti con impostazioni di contrasto elevato abilitate, la personalizzazione non è applicabile. Continueranno a vedere l'esperienza di riunione predefinita di Teams.
- Controlli Amministrazione IT: gli amministratori IT possono impedire agli utenti con problemi di accessibilità di visualizzare il marchio: 
  - Controllo dei criteri, verificando che non vengano aggiunti a un criterio di personalizzazione. Questo controllo impedirà loro di creare riunioni abilitate per la personalizzazione.
  - Opzioni riunione: gli organizzatori della riunione possono disattivare il marchio per una riunione se un utente con problemi di accessibilità parteciperà alla riunione.
