---
title: Gestire team di grandi dimensioni in Microsoft Teams - procedure consigliate
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informazioni sulle procedure consigliate per la gestione di team di grandi dimensioni in Microsoft Teams per soddisfare le esigenze dell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199078"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gestire team di grandi dimensioni in Microsoft Teams - Procedure consigliate

Microsoft Teams è altrettanto efficace nel facilitare le comunicazioni tra piccoli gruppi con decine di membri e grandi gruppi con migliaia di membri. Rivedere [i limiti e le specifiche per Teams per](limits-specifications-teams.md) gli aggiornamenti sulle dimensioni dei team. L'aumento delle dimensioni del team porta a sfide operative e di gestione uniche. Questo articolo descrive le procedure consigliate per creare e gestire team di grandi dimensioni composti da migliaia di membri.

## <a name="value-of-large-teams"></a>Valore dei team di grandi dimensioni

I team di grandi dimensioni sono molto utili per abilitare i seguenti scenari di collaborazione:

- **Collaborazione a livello di reparto**: se l'organizzazione ha più reparti, ad esempio Finanze, Operazioni, R&D e così via, è possibile creare un singolo team che includa tutti i membri di un reparto specifico. Ora tutte le comunicazioni rilevanti per un reparto possono essere condivise in questo team, che facilita la portata e il coinvolgimento immediati dei membri.

- **Collaborazione nei gruppi di risorse dei dipendenti**: spesso le organizzazioni hanno grandi gruppi di persone con interessi comuni che appartengono a un reparto o a un gruppo di lavoro diverso. Ad esempio, ci può essere un gruppo di persone che condividono la passione per la finanza personale e gli investimenti. Spesso è difficile connettersi in un'organizzazione di grandi dimensioni. Per sviluppare community per tali gruppi, gli amministratori del tenant possono creare un team di grandi dimensioni che funge da gruppo di risorse pubblico a livello aziendale di cui chiunque può partecipare e trarre vantaggio. Alla fine, queste community raccolgono informazioni che possono essere apprezzate sia da membri nuovi che da membri esistenti.

- **Collaborazione tra membri interni ed esterni**: i prodotti più diffusi spesso sviluppano una community di early adopter desiderosi di provare le nuove versioni dei prodotti e fornire feedback. Gli early adopter sviluppano una relazione con i gruppi di prodotti per contribuire a dare forma al prodotto. In questi scenari, gli amministratori tenant possono configurare un team di grandi dimensioni che include sia i gruppi di prodotti interni che gli analizzatori esterni dei prodotti per facilitare un processo di sviluppo di prodotti avanzati. Questi team possono anche fornire assistenza clienti a un set selezionato di clienti.

## <a name="create-teams-from-existing-groups"></a>Creare team da gruppi esistenti

Usare gruppi di contatti, gruppi di sicurezza o gruppi di Office per avviare rapidamente il team. È possibile importare un gruppo per creare un team o crearne uno da un gruppo di Office.

**Importare un gruppo per creare un team**: quando si importa un gruppo con un massimo di 3.500 membri in Teams, Teams calcola automaticamente il numero totale di membri del gruppo. Si tratta di un'importazione unica e le modifiche future nel gruppo non verranno aggiornate automaticamente in Teams.

**Creare un team da un gruppo di Microsoft 365 di grandi dimensioni**: quando si crea un team da un gruppo di Microsoft 365 di grandi dimensioni, i membri fanno automaticamente parte del gruppo di Microsoft 365 **e** del team. In futuro, quando i membri del team si uniranno o abbandonano il gruppo di Microsoft 365, verranno aggiunti o rimossi automaticamente dal team.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importazione/esportazione/rimozione in blocco di membri in un team

Il portale di Azure consente agli utenti di importare/esportare/rimuovere in blocco membri in un gruppo di Microsoft 365. Per altre informazioni, vedere [Per importare in blocco i membri del gruppo](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).

Poiché ogni team è supportato da un gruppo Microsoft 365, è possibile usare il portale di Azure per eseguire queste operazioni nel gruppo corrispondente al team. Le operazioni dei membri si rifletteranno nel team entro 24 ore.

## <a name="create-channels-to-focus-discussions"></a>Creare canali per concentrarsi sulle discussioni

È possibile limitare le discussioni di gruppo creando canali evidenziati. Vedere [Procedure consigliate per l'organizzazione dei team](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Limitare la creazione di canali

Se un membro del team è autorizzato a creare canali, il team può avere canali tentacolari. I proprietari dei team devono disattivare la creazione, l'aggiornamento, l'eliminazione e il ripristino dei canali per i membri in **Impostazioni > autorizzazioni per i membri**. Vedere [Panoramica di team e canali](teams-channels-overview.md).

![Immagine della schermata che mostra la sezione autorizzazioni membro della scheda Impostazioni della console di amministrazione.](media/no-channel-creation.png "Immagine della schermata della sezione Autorizzazioni membro della scheda Impostazioni della console di amministrazione. Le opzioni Consenti ai membri di creare o eliminare canali sono deselezionate.")

## <a name="add-favorite-channels"></a>Aggiungere i canali preferiti

Per velocizzare il coinvolgimento degli utenti e l'individuazione dei contenuti, è possibile selezionare i canali preferiti disponibili per l'utente per impostazione predefinita. Nel riquadro **Canali** dell'interfaccia di amministrazione controllare i canali nella colonna **Mostra per i membri** .

![Immagine della schermata che mostra il riquadro canali della console di amministrazione.](media/favorite-channels.png "Immagine della schermata che mostra il riquadro Canali della console di amministrazione. Alcuni canali sono selezionati per Mostra per i membri.")

 Per informazioni dettagliate, vedere [Creare i primi team e canali](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regolare applicazioni e bot in team di grandi dimensioni

Per evitare l'aggiunta di applicazioni o bot che possono distrarre, i proprietari del team possono disabilitare, aggiungere, rimuovere e caricare app e connettori per i membri del team. Nell'interfaccia di amministrazione, in **Impostazioni > autorizzazioni per i membri**, deselezionare le tre opzioni che consentono ai membri di aggiungere app o connettori.

![Immagine della schermata che mostra la sezione Autorizzazioni membro del riquadro Impostazioni.](media/disable-bots-connectors.png "Immagine della schermata che mostra la sezione Autorizzazioni membro del riquadro Impostazioni. Le opzioni per consentire ai membri di aggiungere app o connettori sono deselezionate.")

Vedere [una panoramica delle app Teams](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regolare le menzioni di team e canali

Le menzioni del team e del canale possono essere usate per attirare l'attenzione dell'intero team su determinati post del canale. Una volta usata una menzione in un post, viene inviata una notifica a migliaia di membri del team. Se le notifiche sono troppo frequenti, i membri del team possono sovraccaricarsi e potrebbero lamentarsi con i proprietari del team. Per evitare menzioni del team o del canale, disattivare le menzioni del team e del canale per i membri deselezionando le caselle nel riquadro **Impostazioni > @mentions** team.

![Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni.](media/no-at-mentions.png "Immagine della schermata che mostra la sezione Menzioni del riquadro Impostazioni. Le opzioni per mostrare e concedere ai membri l'accesso alle menzioni sono deselezionate.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considerare la configurazione della moderazione nei canali

I proprietari del team possono abilitare la moderazione in un canale per controllare chi può creare nuovi post e rispondere ai post nel canale. Durante la configurazione della moderazione, è possibile scegliere uno o più membri del team come moderatori I proprietari dei team sono moderatori per impostazione predefinita. Per altre informazioni, vedere [Configurare e gestire la moderazione del canale](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Argomenti correlati

- [Procedure consigliate per l'organizzazione di Teams](best-practices-organizing.md)
- [Creare un team a livello di organizzazione](create-an-org-wide-team.md)