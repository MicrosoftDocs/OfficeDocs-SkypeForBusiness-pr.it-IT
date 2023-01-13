---
title: Configurare la sala di attesa delle riunioni di Microsoft Teams per le riunioni sensibili
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Informazioni su come configurare la sala di attesa delle riunioni di Teams per migliorare la sicurezza per le riunioni riservate usando criteri di amministrazione, etichette di riservatezza e modelli di riunione.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800148"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>Configurare la sala di attesa delle riunioni di Microsoft Teams per le riunioni sensibili

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

La sala di attesa della riunione è uno strumento che consente di garantire che le persone non appropriate non siano ammesse alle riunioni. Tenendo diversi tipi di partecipanti nella sala d'attesa, gli organizzatori della riunione possono controllarli e assicurarsi che partecipino alla riunione in modo appropriato.

Per impostazione predefinita, le persone dell'organizzazione e [gli utenti guest](guest-access.md) sono ammessi alle riunioni direttamente e i partecipanti da domini attendibili e partecipanti anonimi devono attendere nella sala di attesa per essere ammessi da un organizzatore della riunione. Gli organizzatori di riunioni possono modificare questa impostazione predefinita per ogni riunione creata.

La sala di attesa e altre impostazioni correlate possono essere controllate dall'amministratore di Teams usando criteri di riunione, modelli di riunione ed etichette di riservatezza per personalizzare l'esperienza per utenti diversi e tipi diversi di riunioni.

La tabella seguente elenca le caratteristiche che è possibile usare per gestire l'esperienza di sala di attesa per l'organizzazione e dove configurarle.

|Impostazione|criteri di Amministrazione|Etichetta di riservatezza|Modello|Organizzatore della riunione|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Annuncia quando i chiamanti che accedono o abbandonano l'accesso|No|No|Sì|Sì|
|Gli utenti anonimi e i chiamanti possono avviare una riunione|Sì|No|No|No|
|Gli utenti anonimi possono partecipare a una riunione|Sì|No|No|No|
|Persone chiamata in ingresso può ignorare la sala di attesa|Sì|Sì|Sì|Sì|
|Chi può evitare la sala di attesa|Sì|Sì|Sì|Sì|

Per informazioni su come usare modelli ed etichette di riservatezza per configurare le impostazioni delle riunioni, vedere [Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md) e [Usare le etichette di riservatezza per proteggere elementi del calendario, riunioni di Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

## <a name="lobby-settings-for-different-types-of-meetings"></a>Impostazioni della sala di attesa per diversi tipi di riunioni

Le impostazioni seguenti sono disponibili per gli utenti che possono ignorare la sala di attesa:

- Tutti
- Utenti dell'organizzazione, organizzazioni attendibili e guest
- Utenti dell’organizzazione e guest
- Utenti dell’organizzazione
- Persone invitati
- Organizzatori e co-organizzatori

Mentre l'organizzatore della riunione sceglie in genere l'impostazione da usare per ogni riunione, è possibile applicare una determinata impostazione usando un modello di riunione o un'etichetta di riservatezza.

Se l'organizzazione richiede che determinati tipi di riunioni non siano presenti a persone esterne all'organizzazione, prendere in considerazione un modello di riunione che consenta solo agli utenti dell'organizzazione di ignorare la sala di attesa. In questo modo, le persone esterne all'organizzazione che sono state accidentalmente invitate o a cui è stato inviato un collegamento alla riunione non possono partecipare direttamente alla riunione.

Se l'organizzazione ha riunioni in cui vengono condivise informazioni altamente riservate ed è necessario assicurarsi che partecipi solo alcune persone, è consigliabile usare un modello di riunione o un'etichetta di riservatezza che consenta solo agli organizzatori della riunione di ignorare la sala di attesa. In questo modo gli organizzatori possono controllare ogni partecipante in arrivo per assicurarsi che partecipino alla riunione. In questo modo si impedisce anche l'avvio della riunione finché un organizzatore non partecipa.

Per le riunioni riservate in generale, è consigliabile usare l'opzione **Persone invitati**. In questo modo, le persone che non hanno un invito a una riunione (inclusi gli inviti inoltrati) passano dalla sala di attesa. L'organizzatore della riunione può anche impedire l'inoltro quando crea la riunione.

Per informazioni sull'uso di modelli di riunione ed etichette di riservatezza insieme, vedere [Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni sensibili](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>Partecipanti che chiamano telefonicamente

Per impostazione predefinita, i partecipanti che accedono tramite telefono passano attraverso la sala di attesa. Gli amministratori possono modificare questa impostazione predefinita con gli utenti connessi con accesso in ingresso **possono ignorare i criteri per le riunioni dell'amministratore della sala di attesa** . Se si vuole applicare questa impostazione per attivarla o disattivarla, è necessario usare un modello di riunione o un'etichetta di riservatezza.

In alcuni casi in cui si vuole consentire ai chiamanti di ignorare la sala di attesa, gli organizzatori della riunione possono controllare questa impostazione oppure è possibile applicarla tramite un modello di riunione o un'etichetta di riservatezza.

#### <a name="join-and-leave-notifications"></a>Notifiche di partecipazione e uscita

Gli organizzatori della riunione hanno la possibilità di fare in modo che i partecipanti che chiamano tramite telefono vengano annunciati quando accedono o abbandonano una riunione. Per assicurarsi che i partecipanti al telefono vengano annunciati per determinati tipi di riunioni, è possibile applicare questa impostazione con un modello di riunione.

## <a name="meeting-with-anonymous-participants"></a>Riunione con partecipanti anonimi

A meno che non si consenta a tutti di ignorare la sala di attesa, i partecipanti anonimi devono passare attraverso la sala di attesa per partecipare alla riunione. Gli organizzatori della riunione possono quindi decidere se questi partecipanti devono essere ammessi.

Se l'organizzazione non consente affatto ai partecipanti anonimi di partecipare alle riunioni, è possibile disattivare l'impostazione **Gli utenti anonimi possono partecipare a una riunione** nell'interfaccia di amministrazione di Teams. Per altre informazioni, vedere [Gestire le impostazioni delle riunioni in Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

Se nell'organizzazione sono presenti determinati gruppi, ad esempio il marketing, che devono organizzare riunioni con partecipanti anonimi e altri utenti, come la ricerca, che non dovrebbero, è possibile usare i criteri di riunione di Teams per configurare l'accesso anonimo alle riunioni per gruppi diversi. Per il corretto funzionamento dell'impostazione **Gli utenti anonimi possono partecipare a una riunione** indicata in precedenza. Per informazioni dettagliate, vedere [Impostazioni dei criteri riunione - Partecipanti & guest](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Gestire riunioni esterne e chattare in Microsoft Teams](/microsoftteams/manage-external-access)
