---
title: Gestire team di grandi dimensioni in Microsoft Teams procedure consigliate
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulle procedure consigliate per la gestione di team di grandi Microsoft Teams per soddisfare le esigenze dell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d856a47fb4d7888dcaa990cde9a3dd151dac79ea
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619672"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gestire team di grandi dimensioni in Microsoft Teams - Procedure consigliate

Microsoft Teams è altrettanto efficace nel facilitare le comunicazioni tra piccoli gruppi con decine di membri e gruppi di grandi dimensioni con migliaia di membri. Esaminare [i limiti e le specifiche per Teams](limits-specifications-teams.md) aggiornamenti sulle dimensioni del team. L'aumento delle dimensioni del team comporta sfide operative e di gestione uniche. Questo articolo descrive le procedure consigliate per la creazione e la gestione di team di grandi dimensioni composti da migliaia di membri.

## <a name="value-of-large-teams"></a>Valore dei team di grandi dimensioni

I team di grandi dimensioni sono molto utili per abilitare gli scenari di collaborazione seguenti:

- Collaborazione a livello di **reparto:** se l'organizzazione ha più reparti, ad esempio Finanze, Operazioni, R&D e così via, è possibile creare un singolo team che include tutti i membri di un reparto specifico. Ora tutte le comunicazioni pertinenti a un reparto possono essere condivise in questo team, facilitando la comunicazione immediata e l'impegno dei membri.

- **Collaborazione in gruppi di risorse dei** dipendenti: le organizzazioni spesso hanno grandi gruppi di persone con interessi reciproci che appartengono a un reparto o a un gruppo di lavoro diverso. Ad esempio, può esserci un gruppo di persone che condividono la passione per la finanza personale e gli investimenti. Spesso è difficile connettersi in un'organizzazione di grandi dimensioni. Per sviluppare community per tali gruppi, gli amministratori tenant possono creare un team di grandi dimensioni che funge da gruppo di risorse pubblico a livello di società a cui chiunque può partecipare e sfruttare. Alla fine, queste community raccolgono informazioni di cui possono usufruire sia i membri nuovi che quelli esistenti.

- **Collaborazione tra membri interni ed** esterni: i prodotti più diffusi spesso sviluppano una community di utenti che adottano i primi prodotti che desiderano provare nuovi rilasci di prodotti e fornire feedback. I primi utenti sviluppano una relazione con i gruppi di prodotti per contribuire a modellare il prodotto. In questi scenari, gli amministratori dei tenant possono configurare un team di grandi dimensioni che include sia gruppi di prodotti interni che valutatori di prodotti esterni per facilitare un processo di sviluppo di prodotti ricco. Questi team possono anche fornire assistenza clienti a un set selezionato di clienti.

## <a name="create-teams-from-existing-groups"></a>Creare team da gruppi esistenti

Usare i gruppi di contatti, i gruppi di sicurezza o Office per avviare il team. È possibile importare un gruppo per creare un team o crearne uno da un Office gruppo.

**Importare** un gruppo per creare un team: quando si importa un gruppo con un massimo di 3.500 membri in Teams, Teams calcola automaticamente il numero totale di membri del gruppo. Si tratta di una sola importazione e le modifiche future nel gruppo non verranno aggiornate automaticamente in Teams.

**Creare un team** da un gruppo di Microsoft 365 di grandi dimensioni: quando si crea un team da un gruppo di Microsoft 365 di grandi dimensioni, i membri fanno automaticamente parte del gruppo Microsoft 365 e **del** team. In futuro, quando i membri del team si uniscono o abbandonano il Microsoft 365 gruppo, vengono aggiunti o rimossi automaticamente dal team.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importare/esportare/rimuovere membri in blocco in un team

Il portale di Azure consente agli utenti di importare/esportare/rimuovere membri in blocco in un Microsoft 365 gruppo. Per altre informazioni, vedere [Per importare in blocco i membri del gruppo.](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)

Poiché ogni team è supportato da un Microsoft 365, è possibile usare il portale di Azure per eseguire queste operazioni nel gruppo corrispondente al team. Le operazioni dei membri verranno riflesse nel team entro 24 ore.

## <a name="create-channels-to-focus-discussions"></a>Creare canali per concentrarsi sulle discussioni

È possibile restringere le discussioni di gruppo creando canali mirati. Vedere [Procedure consigliate per l'organizzazione dei team.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Limitare la creazione di canali

Se a un membro del team è consentito creare canali, il team può avere un'espansione dei canali. I proprietari del team devono disattivare la creazione, l'aggiornamento, l'eliminazione e il ripristino dei canali per i membri Impostazioni > **autorizzazioni per i membri.** Vedere [Panoramica di team e canali.](teams-channels-overview.md)

![Immagine della schermata che mostra la sezione autorizzazioni per i membri della console di amministrazione Impostazioni scheda.](media/no-channel-creation.png "Immagine della schermata della sezione autorizzazioni per i membri della console di amministrazione Impostazioni scheda. Le opzioni consenti ai membri di creare o eliminare canali sono deselezionate.")

## <a name="add-favorite-channels"></a>Aggiungere canali preferiti

Per velocizzare il coinvolgimento degli utenti e l'individuazione dei contenuti, è possibile selezionare i canali preferiti disponibili per impostazione predefinita per l'utente. Nel riquadro **Canali** dell'interfaccia di amministrazione controllare i canali nella **colonna Mostra per i** membri.

![Immagine della schermata che mostra il riquadro canali della console di amministrazione.](media/favorite-channels.png "Immagine della schermata che mostra il riquadro canali della console di amministrazione. Alcuni canali sono controllati per Mostra per i membri.")

 Per [informazioni dettagliate, vedere Creare](get-started-with-teams-create-your-first-teams-and-channels.md) i primi team e canali.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regolare applicazioni e bot in team di grandi dimensioni

Per evitare l'aggiunta di applicazioni o bot distratti, i proprietari del team possono disabilitare, aggiungere, rimuovere e caricare app e connettori per i membri del team. Nell'interfaccia di amministrazione in **Impostazioni > autorizzazioni per** i membri deselezionare le tre opzioni che consentono ai membri di aggiungere app o connettori.

![Immagine della schermata che mostra la sezione Autorizzazioni membri del riquadro Impostazioni membri.](media/disable-bots-connectors.png "Immagine della schermata che mostra la sezione Autorizzazioni per i membri del riquadro Impostazioni gruppo. Le opzioni per consentire ai membri di aggiungere app o connettori sono deselezionate.")

Vedere [App, bot, & connettori](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regolare le menzioni del team e del canale

Le menzioni del team e del canale possono essere usate per attirare l'attenzione dell'intero team su determinati post del canale. Una volta usata una menzione in un post, viene inviata una notifica a migliaia di membri del team. Se le notifiche sono troppo frequenti, i membri del team possono diventare sovraccarichi e potrebbero lamentarsi con i proprietari del team. Per evitare menzioni di team o canali, disattivare le menzioni di team e canali per i membri deselezionando le caselle nel riquadro Impostazioni > @mentions **team.**

![Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni testo.](media/no-at-mentions.png "Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni. Le opzioni per mostrare e concedere ai membri l'accesso alle menzioni sono deselezionate.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerare la configurazione della moderazione nei canali

I proprietari del team possono abilitare la moderazione in un canale per controllare chi può creare nuovi post e rispondere ai post nel canale. Durante la configurazione della moderazione, è possibile scegliere uno o più membri del team come moderatori I proprietari del team sono moderatori per impostazione predefinita. Per altre informazioni, vedere [Configurare e gestire la moderazione dei canali.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per l'organizzazione dei Teams](best-practices-organizing.md)
- [Creare un team a livello di organizzazione](create-an-org-wide-team.md)