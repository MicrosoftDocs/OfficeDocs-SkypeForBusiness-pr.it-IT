---
title: Gestire l'app Aggiornamenti per l'organizzazione
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
description: Informazioni su come gestire l'app Aggiornamenti in Teams per gli utenti dell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 393793e5c0a5c4a305f26427951968c5614c052f
ms.sourcegitcommit: 5640e8264b61c1f8cf8eb212315eeba1a794e494
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2022
ms.locfileid: "65928859"
---
# <a name="manage-the-updates-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app Aggiornamenti per l'organizzazione in Microsoft Teams

## <a name="what-is-the-updates-app"></a>Che cos'è l'app Aggiornamenti

Gli aggiornamenti nell'app Microsoft Teams offrono ai membri dell'organizzazione un posto centralizzato in cui creare, rivedere e inviare gli aggiornamenti. Creando modelli, è possibile usare l'app Aggiornamenti per tenere traccia di tutto ciò di cui l'organizzazione ha bisogno. Gli aggiornamenti sono disponibili sia per il desktop che per i dispositivi mobili.

In Teams, gli utenti possono ottenere gli aggiornamenti dall'app store di Teams. Tutti gli aggiornamenti che devono inviare verranno visualizzati nella pagina **Invia** .

[![Immagine della pagina Invia in Teams per desktop.](media/updates-submit-small.png)](media/updates-submit.png#lightbox)

Gli utenti possono visualizzare gli aggiornamenti assegnati nella pagina **Revisione** .

[![Immagine della pagina Revisione in Teams per desktop.](media/updates-home-small.png)](media/updates-home.png#lightbox)

Quando a un utente viene assegnato un aggiornamento, questo viene visualizzato nel feed attività di Teams. Gli utenti possono anche visualizzare tutte le richieste di aggiornamento correnti e gli invii precedenti nell'app Aggiornamenti. Inoltre, chiunque può creare modelli e inviare richieste di aggiornamento.

Gli aggiornamenti includono modelli predefiniti per scenari aziendali comuni e l'opzione per creare un modello personalizzato. Chiunque può creare un modello per nuovi tipi di aggiornamenti.

## <a name="example-scenario"></a>Scenario di esempio

I dipendenti di un negozio di abbigliamento sono responsabili dell'apertura e della chiusura del negozio ogni giorno. Ogni mattina, il responsabile dei turni compila l'aggiornamento di apertura dello Store, un modello predefinito nell'app Aggiornamenti. In questo aggiornamento, descrivono eventuali problemi con la chiusura della notte precedente, rispondono a domande sulla pulizia del negozio e segnalano eventuali forniture che necessitano di rifornimento. L'invio di un aggiornamento consente loro di comunicare le loro esigenze per lo store e gli eventuali problemi in modo rapido ed efficiente. Gli aggiornamenti giornalieri offrono anche ai collaboratori dello Store l'opportunità di evidenziare ciò che sta andando bene.

Presso le strutture di produzione dello store, i dipendenti eseguono controlli di sicurezza con Gli aggiornamenti tramite dispositivi mobili.

![Immagine del modello di procedura dettagliata sulla sicurezza settimanale in un dispositivo mobile.](media/updates-mobile.png)

Nel frattempo, un team di lavoratori remoti sta aggiornando il sito Web dello store. Sono distribuiti in fusi orari, quindi le riunioni di stand-up giornaliere non sono comodi. Ognuno dei membri del team invia al responsabile del team report sugli aggiornamenti giornalieri sullo stato di avanzamento.

[Scarica la lookbook Aggiornamenti](https://go.microsoft.com/fwlink/?linkid=2197649&clcid=0x409) per vedere altri esempi di cosa puoi fare con Gli aggiornamenti.

## <a name="required-permissions-and-licenses"></a>Autorizzazioni e licenze richieste

Per distribuire gli aggiornamenti, è necessaria l'autorizzazione per gli elementi seguenti:

- Autorizzazioni per creare un database Microsoft Dataverse.

- Un account in [powerautomate.microsoft.com](https://powerautomate.microsoft.com/).

- Ruolo di amministratore nell'ambiente di destinazione.

- Licenza per Power Automate, Office 365 o Dynamics 365.

- La licenza per Microsoft Forms è necessaria per consentire agli utenti di configurare nuovi modelli.

## <a name="storage-with-microsoft-dataverse"></a>Archiviazione con Microsoft Dataverse

Il common data model (CDM) è il linguaggio dei dati condiviso usato dalle applicazioni aziendali e analitiche in Microsoft Dataverse. È costituito da un set di schemi di dati estendibili standardizzati pubblicati da Microsoft e dai nostri partner che consentono la coerenza dei dati e il relativo significato tra le applicazioni e i processi aziendali. Altre informazioni sul [modello di dati comune](/common-data-model/).

Gli aggiornamenti creati da un modello archiviano comunque i dati in Microsoft Dataverse, ad esempio il titolo, i dettagli, l'ID modello e altro ancora. Altre informazioni  [sull'archiviazione dei dati per Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Se si elimina il modello di modulo nel sito Microsoft Forms, il modello Aggiornamenti verrà interrotto e gli utenti non saranno in grado di inviare l'aggiornamento. Gli utenti ricevono un errore "CDB TableNotFound" quando provano ad aprire un modello eliminato in Microsoft Forms.

## <a name="updates-teams-app-permissions"></a>Aggiornamento delle autorizzazioni per le app Teams

L'app Aggiornamenti di Teams consente di accedere alle seguenti funzionalità:

- Ricevere messaggi e dati forniti dall'utente.

- Invio di messaggi e notifiche dell'utente.

- Render delle app e delle finestre di dialogo personali senza intestazione fornita da Teams.

- Accesso alle informazioni del profilo, ad esempio nome, indirizzo di posta elettronica, nome della società e lingua preferita.

- Ricevere messaggi e dati forniti dai membri del team nel canale.

- Inviare messaggi e notifiche in un canale.

- Accedere alle informazioni del team:
  - nome del team
  - elenco dei canali
  - elenco dei membri del team (nomi e indirizzi di posta elettronica dei membri del team)

- Uso delle informazioni del team per i contatti.

## <a name="disable-the-updates-app"></a>Disabilitare l'app Aggiornamenti

L'app Aggiornamenti è disponibile per impostazione predefinita. È possibile disabilitarla nell'interfaccia di amministrazione di Teams.

  1. Passare all'interfaccia di amministrazione di Teams.

  2. Passare a **app Teams** >  **Gestisci app**.

  3. Cerca l'app Aggiornamenti.

     [![Screenshot della struttura di spostamento dell'interfaccia di amministrazione con l'opzione App di Teams > Gestisci app evidenziata.](media/manage-updates-small.png)](media/manage-updates.png#lightbox)

  4. Seleziona **Aggiornamenti**.

  5. Selezionare l'interruttore per disabilitare l'app per l'organizzazione.
    ![Immagine dell'interruttore per abilitare o disabilitare gli aggiornamenti.](media/toggle-updates.png)

## <a name="pin-updates-to-teams"></a>Aggiungere aggiornamenti a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per aggiungere app più importanti per gli utenti degli utenti. Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams, dove gli utenti possono accedervi rapidamente e facilmente.

Per aggiungere l'app Aggiornamenti per gli utenti, è possibile modificare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri di configurazione dell'app personalizzati. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Criteri di conservazione

Gli aggiornamenti creati dall'app Aggiornamenti vengono archiviati nell'ambiente predefinito Microsoft Dataverse, che al momento non supporta i backup. Altre informazioni su come eseguire il [Backup e il ripristino di ambienti - Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments).

I dati archiviati in Forms non verranno eliminati finché l'autore del modello non lo pulirà dalla scheda **moduli eliminati** nell'app Web Microsoft Forms.

## <a name="conditional-access-policies"></a>Criteri di accesso condizionale

Attualmente, l'app Aggiornamenti in Teams non supporta i criteri di accesso condizionale impostati per Microsoft Teams.

## <a name="data-limitations"></a>Limitazioni dei dati

Ogni utente può creare al massimo 400 modelli di aggiornamenti e ogni modello può raccogliere un massimo di 50.000 richieste in base alla funzionalità corrente in Microsoft Forms.

## <a name="security"></a>Sicurezza

Dall'app Aggiornamenti di Teams, gli utenti hanno accesso per creare nuovi aggiornamenti e visualizzare gli aggiornamenti che hanno inviato e ricevuto. Gli utenti non avranno accesso agli aggiornamenti creati da altri utenti, a meno che non siano visualizzatori della richiesta.

> [!Note]
> A un utente viene assegnato il ruolo di visualizzatore di una richiesta se fa parte della chat o del canale in cui è stato creato il report di aggiornamento o se l'autore del modello li aggiunge manualmente come visualizzatore. Non potranno intervenire sulla richiesta se al momento della creazione del report non è stato assegnato quel ruolo.
