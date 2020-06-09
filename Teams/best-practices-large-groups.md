---
title: Gestire team di grandi dimensioni in Microsoft teams-procedure consigliate
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulle procedure consigliate per la gestione di team di grandi dimensioni in Microsoft teams per soddisfare le esigenze dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638906"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gestire team di grandi dimensioni in Microsoft teams-procedure consigliate
======================================================

Microsoft teams è ugualmente efficace per facilitare le comunicazioni tra piccoli gruppi con decine di membri e gruppi di grandi dimensioni con migliaia di membri. Rivedere i [limiti e le specifiche per i team](limits-specifications-teams.md) per gli aggiornamenti sulle dimensioni del team. L'aumento delle dimensioni del team porta a una gestione unica e alle sfide operative. In questo articolo vengono illustrate le procedure consigliate per la creazione e la gestione di team di grandi dimensioni composti da migliaia di membri.

## <a name="value-of-large-teams"></a>Valore di team di grandi dimensioni

I team di grandi dimensioni sono molto utili per abilitare gli scenari di collaborazione seguenti:

- **Collaborazione a livello di reparto**: se l'organizzazione ha più reparti, ad esempio finanza, operazioni, R&D e così via, è possibile creare un singolo team che includa tutti i membri in uno specifico reparto. Ora tutte le comunicazioni rilevanti per un reparto possono essere condivise in questo team, che facilita la portata immediata e l'impegno dei membri.

- **Collaborazione nei gruppi di risorse dei dipendenti**: spesso le organizzazioni hanno grandi gruppi di persone con interessi reciproci che appartengono a un altro reparto o gruppo di lavoro. Ad esempio, può essere presente un gruppo di persone che condividono la passione per la finanza personale e l'investimento. Spesso è difficile connettersi in un'organizzazione di grandi dimensioni. Per sviluppare community per tali gruppi, gli amministratori del tenant possono creare un team di grandi dimensioni che funge da gruppo di risorse pubblico a livello di società a cui chiunque può partecipare e sfruttare. Alla fine, queste community raccolgono informazioni che i membri nuovi e quelli esistenti possono godere.

- **Collaborazione tra membri interni ed esterni: i**prodotti più diffusi spesso sviluppano una community di early adopters desiderosi di provare nuovi rilasci di prodotto e di inviare feedback. I primi adottanti sviluppano una relazione con i gruppi di prodotti per dare forma al prodotto. In questi scenari, gli amministratori del tenant possono configurare un team di grandi dimensioni che include sia i gruppi di prodotti interni che gli analizzatori di prodotti esterni per facilitare un processo di sviluppo di prodotti RTF. Questi team possono anche supportare il cliente per un set di clienti selezionato.

## <a name="create-teams-from-existing-groups"></a>Creare team da gruppi esistenti

Usare i gruppi di contatti, i gruppi di sicurezza o i gruppi di Office per avviare il team. È possibile importare un gruppo per rendere un team o creare un team da un gruppo di Office.

**Importare un gruppo per creare un team**: quando si importa un gruppo con un massimo di 3.500 membri in teams, teams calcola automaticamente il numero totale di membri nel gruppo. Si tratta di un'unica operazione di importazione unica e le modifiche future del gruppo non verranno aggiornate automaticamente in teams.

**Creare un team da un gruppo microsoft 365 di grandi dimensioni**: quando si crea un team da un gruppo di Microsoft 365 di grandi dimensioni, i membri fanno automaticamente parte del gruppo Microsoft 365 **e** del team. In futuro, dato che i membri del team partecipano o lasciano il gruppo Microsoft 365, vengono aggiunti o rimossi automaticamente dal team.

## <a name="create-channels-to-focus-discussions"></a>Creare canali per concentrarsi sulle discussioni

È possibile restringere le discussioni di gruppo creando canali mirati. Vedere le [procedure consigliate per organizzare i team](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Limitare la creazione di canali

Se un membro del team è autorizzato a creare canali, il team può avere l'espansione dei canali. I proprietari del team devono disattivare la creazione, l'aggiornamento, l'eliminazione e il ripristino di un canale per i membri in **impostazioni > autorizzazioni dei membri**. Vedere [Panoramica di team e canali](teams-channels-overview.md).

![Immagine della schermata che mostra la sezione autorizzazioni per i membri della scheda Impostazioni della console di amministrazione.](media/no-channel-creation.png "Immagine della sezione autorizzazioni per i membri della scheda Impostazioni della console di amministrazione. Le opzioni Consenti ai membri di creare o eliminare i canali sono deselezionate.")

## <a name="add-favorite-channels"></a>Aggiungere canali preferiti

Per velocizzare l'individuazione di nuovi impegni e contenuti per l'utente, è possibile selezionare i canali preferiti disponibili per l'utente per impostazione predefinita. Nel riquadro **canali** dell'interfaccia di amministrazione selezionare i canali nella colonna **Mostra per membri** .

![Immagine dello schermo che mostra il riquadro canali della console di amministrazione.](media/favorite-channels.png "Immagine dello schermo che mostra il riquadro canali della console di amministrazione. Alcuni canali sono controllati per la presentazione per i membri.")

 Per informazioni dettagliate, vedere [creare i primi team e i canali](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regolare le applicazioni e i bot in team di grandi dimensioni

Per impedire l'aggiunta di applicazioni o bot distraenti, i proprietari del team possono disabilitare, aggiungere, rimuovere e caricare app e connettori per i membri del team. Nell'interfaccia di amministrazione in **impostazioni > autorizzazioni**per i membri deselezionare le tre opzioni che consentono ai membri di aggiungere app o connettori.

![Immagine della schermata che mostra la sezione autorizzazioni per i membri del riquadro Impostazioni.](media/disable-bots-connectors.png "Immagine della schermata che mostra la sezione autorizzazioni per i membri del riquadro Impostazioni. Le opzioni per consentire ai membri di aggiungere app o connettori sono deselezionate.")

Vedere [app, bot, connettori &](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regolare le menzioni del team e del canale

Le menzioni del team e del canale possono essere usate per attirare l'attenzione dell'intero team su determinati post del canale. Una volta usata una menzione in un post, viene inviata una notifica a migliaia di membri del team. Se le notifiche sono troppo frequenti, i membri del team possono diventare sovraccaricati e potrebbero lamentarsi con i proprietari del team. Per evitare menzioni del team o del canale, disattivare le menzioni del team e del canale per i membri deselezionando le caselle nel riquadro **> impostazioni** teams @mentions.

![Immagine della schermata che mostra la sezione menzioni del riquadro Impostazioni.](media/no-at-mentions.png "Immagine della schermata che mostra la sezione menzioni del riquadro Impostazioni. Le opzioni per la visualizzazione e l'accesso ai membri alle menzioni sono deselezionate.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerare la configurazione della moderazione nei canali

I proprietari del team possono abilitare la moderazione in un canale per controllare chi può creare nuovi post e rispondere ai post nel canale. Durante la configurazione della moderazione, è possibile scegliere uno o più membri del team come moderatori I proprietari del team sono moderatori per impostazione predefinita. Per altre informazioni, vedere [configurare e gestire la moderazione dei canali](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per organizzare i team](best-practices-organizing.md)
- [Creare un team a livello di organizzazione](create-an-org-wide-team.md)
