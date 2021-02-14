---
title: Gestire team di grandi dimensioni in Microsoft Teams - procedure consigliate
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulle procedure consigliate per gestire team di grandi dimensioni in Microsoft Teams per soddisfare le esigenze dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582663"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gestire team di grandi dimensioni in Microsoft Teams - Procedure consigliate
======================================================

Microsoft Teams è ugualmente efficace per agevolare le comunicazioni tra piccoli gruppi con decine di membri e gruppi di grandi dimensioni con migliaia di membri. Esaminare [i limiti e le specifiche per Teams per](limits-specifications-teams.md) gli aggiornamenti sulle dimensioni dei team. L'aumento delle dimensioni del team porta a sfide operative e di gestione specifiche. Questo articolo descrive le procedure consigliate per creare e gestire team di grandi dimensioni composti da migliaia di membri.

## <a name="value-of-large-teams"></a>Valore dei team di grandi dimensioni

I team di grandi dimensioni sono molto utili per abilitare gli scenari di collaborazione seguenti:

- **Collaborazione** a livello di reparto: se l'organizzazione ha più reparti, ad esempio Finanze, Operazioni, Ricerca&D e così via, è possibile creare un singolo team che includa tutti i membri di un reparto specifico. Ora tutte le comunicazioni pertinenti per un reparto possono essere condivise in questo team, facilitando il coinvolgimento e il coinvolgimento immediato dei membri.

- **Collaborazione nei gruppi di risorse dei** dipendenti: le organizzazioni spesso hanno grandi gruppi di persone con interessi comuni che appartengono a un reparto o a un gruppo di lavoro diverso. Ad esempio, ci può essere un gruppo di persone che condividono la stessa passione per la finanza personale e gli investimenti. Spesso è difficile connettersi in un'organizzazione di grandi dimensioni. Per sviluppare community per questi gruppi, gli amministratori del tenant possono creare un team di grandi dimensioni che funge da gruppo di risorse pubblico a livello aziendale a cui chiunque può partecipare e trarne vantaggio. Alla fine, queste community raccoglieranno informazioni che possono essere recuperate sia dai membri nuovi che da quelli esistenti.

- **Collaborazione tra membri interni ed** esterni: i prodotti più diffusi spesso sviluppano una community di early adopter che non vedenti di provare i rilasci di nuovi prodotti e fornire feedback. Gli early adopter sviluppano una relazione con i gruppi di prodotti per contribuire a modellare il prodotto. In questi scenari, gli amministratori del tenant possono configurare un team di grandi dimensioni che include sia gruppi di prodotti interni che valutatori esterni per facilitare un processo di sviluppo di un prodotto ricco. Questi team possono anche fornire supporto ai clienti a un gruppo selezionato di clienti.

## <a name="create-teams-from-existing-groups"></a>Creare team da gruppi esistenti

Usare i gruppi di contatti, i gruppi di sicurezza o i gruppi di Office per creare il team. È possibile importare un gruppo per creare un team o crearne uno da un gruppo di Office.

**Importare un gruppo** per creare un team: quando si importa un gruppo con un massimo di 3.500 membri in Teams, Teams calcola automaticamente il numero totale di membri del gruppo. Si tratta di una sola importazione una sola volta e le modifiche future nel gruppo non verranno aggiornate automaticamente in Teams.

Creare un team da un gruppo di **Microsoft 365** di grandi dimensioni: quando si crea un team da  un gruppo di Microsoft 365 di grandi dimensioni, i membri fanno automaticamente parte del gruppo di Microsoft 365 e del team. In futuro, quando i membri del team entraranno o abbandonano il gruppo di Microsoft 365, verranno automaticamente aggiunti o rimossi dal team.

## <a name="create-channels-to-focus-discussions"></a>Creare canali per concentrarsi sulle discussioni

È possibile restringere le discussioni del gruppo creando canali mirati. Vedere [le procedure consigliate per l'organizzazione dei team.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Limitare la creazione di canali

Se un membro del team è autorizzato a creare canali, può avere un'estensione del canale. I proprietari del team devono disattivare la creazione, l'aggiornamento, l'eliminazione e il ripristino dei canali per i membri nelle impostazioni **> autorizzazioni per i membri.** Vedi [Panoramica su team e canali.](teams-channels-overview.md)

![Immagine della schermata che mostra la sezione Autorizzazioni per i membri della scheda Impostazioni della console di amministrazione.](media/no-channel-creation.png "Immagine della sezione Autorizzazioni per i membri della scheda Impostazioni della console di amministrazione. Le opzioni consenti ai membri di creare o eliminare canali sono deselezionate.")

## <a name="add-favorite-channels"></a>Aggiungere canali preferiti

Per accelerare il coinvolgimento degli utenti e l'individuazione dei contenuti, è possibile selezionare i canali preferiti disponibili per impostazione predefinita. Nel riquadro **Canali** dell'interfaccia di amministrazione, controlla i canali nella **colonna Mostra per i** membri.

![Schermata che mostra il riquadro Canali della console di amministrazione.](media/favorite-channels.png "Schermata che mostra il riquadro Canali della console di amministrazione. Alcuni canali sono selezionati per Mostra per i membri.")

 Per [informazioni dettagliate, vedere Creare](get-started-with-teams-create-your-first-teams-and-channels.md) i primi team e canali.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regolare applicazioni e bot in team di grandi dimensioni

Per evitare di distrarre applicazioni o bot, i proprietari del team possono disabilitare, aggiungere, rimuovere e caricare app e connettori per i membri del team. Nell'interfaccia di amministrazione, **in Impostazioni > autorizzazioni** per i membri, deselezionare le tre opzioni che consentono ai membri di aggiungere app o connettori.

![Immagine della schermata che mostra la sezione Autorizzazioni per i membri del riquadro Impostazioni.](media/disable-bots-connectors.png "Immagine della schermata che mostra la sezione Autorizzazioni per i membri del riquadro Impostazioni. Le opzioni per consentire ai membri di aggiungere app o connettori sono deselezionate.")

Vedi [App, bot e & connettori.](deploy-apps-microsoft-teams-landing-page.md)

## <a name="regulate-team-and-channel-mentions"></a>Regolare le menzioni del team e del canale

Le menzioni di team e canali possono essere usate per attirare l'attenzione dell'intero team su determinati post del canale. Una volta usata una menzione in un post, viene inviata una notifica a migliaia di membri del team. Se le notifiche sono troppo frequenti, i membri del team possono essere sovraccarichi e i proprietari del team potrebbero lamentarsi. Per evitare menzioni del team o del canale, disattivare le menzioni del team e del canale per i membri deselezionando le caselle nel riquadro > @mentions impostazioni **dei** team.

![Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni.](media/no-at-mentions.png "Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni. Le opzioni per mostrare e concedere ai membri l'accesso alle menzioni sono deselezionate.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerare la configurazione della moderazione nei canali

I proprietari del team possono abilitare la moderazione in un canale per controllare chi può creare nuovi post e rispondere ai post nel canale. Durante la configurazione della moderazione, è possibile scegliere uno o più membri del team come moderatori I proprietari dei team sono i moderatori per impostazione predefinita. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per l'organizzazione di Teams](best-practices-organizing.md)
- [Creare un team a livello di organizzazione](create-an-org-wide-team.md)
