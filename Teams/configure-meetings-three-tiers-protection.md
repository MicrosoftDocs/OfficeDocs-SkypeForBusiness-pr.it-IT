---
title: Configurare le riunioni di Teams con tre livelli di protezione
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
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Informazioni su come configurare le riunioni di Teams per una maggiore sicurezza usando tre livelli di protezione, bilanciando la sicurezza con la facilità di collaborazione.
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800128"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>Configurare le riunioni di Teams con tre livelli di protezione

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Gli articoli di questa serie offrono opzioni per l'uso delle funzionalità di conformità disponibili in Teams e Microsoft 365 per creare un ambiente di riunione che soddisfi i requisiti di conformità. Esamineremo le opzioni disponibili con le etichette e i modelli di riservatezza e come usarle insieme ad altre impostazioni di amministrazione di Teams.

> [!Note]
> Le impostazioni delle riunioni nelle etichette di riservatezza e nei modelli di riunione personalizzati richiedono Teams Premium.

Questo articolo definisce quattro diverse configurazioni, a partire da una configurazione di base per le riunioni che non hanno requisiti di conformità specifici. Ogni configurazione aggiuntiva rappresenta un passaggio significativo nella protezione man mano che le opzioni delle riunioni diventano più limitate. Le configurazioni di questo articolo forniscono esempi su come configurare la protezione per le riunioni con diversi livelli di sensibilità. Usare questi esempi per capire cosa è possibile e modificare le impostazioni specifiche in base alle esigenze dell'organizzazione.

Verranno illustrate queste tre configurazioni:

- Protezione prevista

- Protezione sensibile

- Protezione altamente sensibile

Verrà inoltre illustrata una variante della configurazione altamente sensibile progettata per le presentazioni con un'interazione minima da parte dei partecipanti.

## <a name="three-tiers-at-a-glance"></a>Tre livelli a colpo d'occhio

La tabella seguente riepiloga le configurazioni per ogni livello. Usare queste configurazioni come punti di partenza e modificare le configurazioni in base alle esigenze dell'organizzazione. A seconda delle esigenze di conformità, potrebbe non essere necessario ogni livello.

|&nbsp;|Linea|Sensibile|Altamente sensibile|Presentazione altamente sensibile|
|:-----|:-----|:-----|:-----|:-----|
|Consentire la fotocamera per i partecipanti|**Attivato**|**Attivato**|**Attivato**|**Disattivato**|
|Consentire il microfono per i partecipanti|**Attivato**|**Attivato**|**Attivato**|**Disattivato**|
|Applicare una filigrana al feed video di tutti gli utenti|**Disattivato**|**Disattivato**|**Attivato**|**Attivato**|
|Applicare una filigrana al contenuto condiviso|**Disattivato**|**Disattivato**|**Attivato**|**Attivato**|
|Crittografia end-to-end|**Disattivato**|**Disattivato**|**Attivato**|**Attivato**|
|Gestire ciò che i partecipanti vedono|**Disattivato**|**Attivato**|**Attivato**|**Attivato**|
|Chat della riunione|**Attivato**|**Attivato**|**Solo in riunione**|**Disattivato**|
|Persone chiamata in ingresso può ignorare la sala di attesa|**Disattivato**|**Disattivato**|**Disattivato**|**Disattivato**|
|Impedire la copia del contenuto della chat negli Appunti|**Disattivato**|**Disattivato**|**Attivato**|**Attivato**|
|Registra automaticamente|**Disattivato**|**Disattivato**|**Disattivato**|**Disattivato**|
|Chi può evitare la sala di attesa|**Persone dell'organizzazione, persone in domini attendibili e guest**|**Persone invito**|**Solo io e co-organizzatori**|**Solo io e co-organizzatori**|
|Chi può presentare|**Utenti dell’organizzazione e guest**|**Utenti dell’organizzazione e guest**|**Solo organizzatori e co-organizzatori**|**Solo organizzatori e co-organizzatori**|
|Chi può registrare|**Organizzatori e relatori**|**Organizzatori e co-organizzatori**|Disabilitato a causa della filigrana|Disabilitato a causa della filigrana|

I dettagli su come configurare ogni livello sono trattati in:

- [Configurare le riunioni di Teams con la protezione di base](configure-meetings-baseline-protection.md)
- [Configurare le riunioni di Teams con la protezione dei dati sensibili](configure-meetings-sensitive-protection.md)
- [Configurare le riunioni di Teams con protezione per i dati altamente sensibili](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>Gestione della conformità con etichette di riservatezza e modelli di riunione

Sia i modelli di riunione che le etichette di riservatezza hanno la possibilità di applicare determinate impostazioni delle riunioni. La maggior parte delle impostazioni può essere applicata come attivata o disattivata oppure può essere lasciata non configurata in modo che l'organizzatore della riunione possa impostarle.

> [!Important]
> Alcune funzionalità sono [controllate dai criteri di amministrazione](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) e devono essere abilitate prima di poter essere controllate dai modelli di riunione e dalle etichette di riservatezza.

Alcune impostazioni sono disponibili solo nelle etichette di riservatezza, mentre altre sono disponibili solo nei modelli. Molti sono disponibili in entrambi:

- Chat
- Crittografia end-to-end
- Impostazioni della sala di attesa
- Registrazione di una riunione
- Watermarking

Le etichette e i modelli di riservatezza possono essere usati insieme per soddisfare le esigenze di conformità. Per altre informazioni, vedere [Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme](meeting-templates-sensitivity-labels-policies.md).

## <a name="meeting-chat"></a>Chat della riunione

La chat della riunione può essere una parte importante della collaborazione durante una riunione. Tuttavia, è consigliabile limitare la chat della riunione in determinati tipi di riunioni per evitare la condivisione di informazioni riservate.

Gli amministratori possono controllare la chat della riunione nei modi seguenti:

- **I criteri per le riunioni dell'amministratore di Teams** (per utente o gruppo) possono essere usati per consentire la chat, consentire la chat per tutti tranne i partecipanti anonimi o disattivare la chat.
- **L'impostazione dell'etichetta di riservatezza** (per riunione) può impostare l'accensione o la disattivazione della chat solo durante la riunione. Questa impostazione può essere lasciata non configurata per essere controllata da un modello o dall'organizzatore della riunione.
- **L'impostazione del modello di riunione** (per riunione) può impostare la chat in modo che sia attiva o disattivata o consentita solo durante la riunione. Questa impostazione può essere lasciata non configurata per essere controllata dall'organizzatore della riunione.

Per i tre livelli di protezione, consentiamo la chat per le riunioni di base e sensibili e le limitiamo alle riunioni altamente riservate solo in riunione.

Per altre informazioni, vedere [Gestire la chat per le riunioni sensibili di Teams](manage-chat-sensitive-meetings.md).

## <a name="meeting-recordings"></a>Registrazioni delle riunioni

Gli amministratori possono controllare le registrazioni delle riunioni nei modi seguenti:

- Criteri per le riunioni di amministrazione **registrazione cloud** (per utente o gruppo)
- I **criteri per le riunioni** dell'amministratore (per utente o gruppo) scadono automaticamente (eliminazione delle registrazioni)
- Impostazione **Chi può registrare** in etichette di riservatezza e modelli di riunione (per riunione)
- Impostazione **Registra automaticamente** in etichette di riservatezza e modelli di riunione (per riunione)

Se l'organizzazione o determinate persone o gruppi al suo interno non dovrebbero mai essere in grado di registrare riunioni, è possibile disattivare la funzionalità usando i criteri per le riunioni di amministrazione **registrazione cloud** .

Se ci sono determinati tipi di riunione che devono essere sempre registrati, è possibile applicare l'impostazione **Registra automaticamente** usando un modello di riunione o un'etichetta di riservatezza.

All'interno dei tre livelli discussi qui, la registrazione è disabilitata in riunioni altamente riservate perché stiamo usando crittografia end-to-end e filigrane su contenuti e video condivisi. Se è necessario registrare riunioni altamente riservate, assicurarsi di non applicare filigrane o crittografia end-to-end con l'etichetta di riservatezza.If you need to be able to record highly sensitive meetings, assicurarsi di non applicare filigrane o crittografia end-to-end con l'etichetta di riservatezza. Gli organizzatori delle riunioni possono comunque usare la crittografia end-to-end e applicare filigrane se una determinata riunione non viene registrata.

Per altre informazioni sulla gestione delle opzioni di registrazione delle riunioni, vedere [Gestire le opzioni di registrazione delle riunioni di Microsoft Teams per le riunioni sensibili](manage-meeting-recording-options.md).

Per informazioni sulla registrazione delle riunioni per la conformità basata su criteri, vedere [Introduzione alla registrazione basata sui criteri di Teams per le chiamate & le riunioni](teams-recording-policy.md).

## <a name="meeting-with-guests-and-external-participants"></a>Riunione con guest e partecipanti esterni

Esistono tre tipi di partecipanti esterni che possono partecipare alle riunioni:

- Partecipanti da domini attendibili
- Utenti guest
- Partecipanti anonimi

I partecipanti provenienti da domini attendibili partecipano alle riunioni tramite la funzionalità [di accesso esterno](manage-external-access.md) . È possibile controllare quali domini, se presenti, l'organizzazione vuole considerare attendibili. Questa impostazione influisce anche su 1:1 e sulla chat di gruppo con le persone in tali domini.

Se [l'accesso guest di Teams](guest-access.md) è abilitato per la tua organizzazione, i guest potranno partecipare alle riunioni. Le impostazioni di accesso guest possono essere utilizzate anche per controllare la modalità di condivisione dello schermo dei guest, inclusa la disabilitazione della condivisione dello schermo. L'accesso guest viene usato anche per invitare guest ai team.

Se l'impostazione **Utenti anonimi possono partecipare a una riunione** di amministrazione di Teams è attivata, i partecipanti anonimi potranno partecipare alle riunioni.

Anche se è possibile disattivare completamente l'accesso anonimo senza influire su funzionalità diverse dalle riunioni, sia l'accesso guest che i domini attendibili vengono usati in scenari esterni alle riunioni. Se si vuole limitare l'accesso alla riunione a questi partecipanti, ma è necessario lasciare attivate le funzionalità per altri motivi, è necessario usare la sala di attesa.

## <a name="lobby-options"></a>Opzioni della sala di attesa

La sala di attesa della riunione consente agli organizzatori della riunione di controllare i partecipanti prima di consentire loro di parteciparvi. A seconda del tipo di riunione e dei requisiti di conformità, è consigliabile consentire a tutti i partecipanti di ignorare la sala di attesa e partecipare direttamente alla riunione oppure di tenere determinati tipi di partecipanti nella sala di attesa finché non vengono ammessi da un organizzatore della riunione. Se si vuole impedire che determinati tipi di persone, ad esempio gli ospiti, partecipino alle riunioni, è possibile fare in modo che passino nella sala di attesa e che l'organizzatore della riunione neghi l'ammissione.

Per il livello di base, tutti tranne i partecipanti anonimi possono ignorare la sala di attesa. Per le riunioni riservate, consentiamo solo alle persone con un invito a una riunione di ignorare la sala di attesa. Per le riunioni molto sensibili, è necessario che gli organizzatori ammettano ogni partecipante.

Gli amministratori possono controllare la sala di attesa nei modi seguenti:

- Criteri **per l'ammissione automatica delle riunioni** di amministrazione utenti (per utente o gruppo)
- Gli **utenti con accesso esterno possono ignorare i criteri della** riunione di amministrazione della sala di attesa (per utente o gruppo)
- **Impostazione Chi può ignorare la sala di attesa** in etichette di riservatezza e modelli di riunione (per riunione)
- Il **Persone l'accesso esterno può ignorare i** criteri di riunione dell'amministratore della sala di attesa (per utente o gruppo) o nelle etichette di riservatezza e nei modelli di riunione (per riunione)

Queste impostazioni sono disponibili anche per l'organizzatore della riunione, a meno che non siano state bloccate da un'etichetta di riservatezza o da un modello.


Anche se i criteri di amministrazione impostano un valore predefinito, è necessario un modello o un'etichetta per applicare


Se si è in un settore altamente regolamentato ed è necessario ammettere manualmente ogni partecipante a tutte le riunioni dell'organizzazione, è possibile configurare la sala di attesa usando i criteri delle riunioni di amministrazione nell'interfaccia di amministrazione di Teams. Se l'organizzazione ha diversi tipi di riunioni con requisiti di sala di attesa diversi, è consigliabile usare modelli di riunione o etichette di riservatezza per configurare queste impostazioni.

Per altre informazioni, vedere [Configurare la sala di attesa delle riunioni di Microsoft Teams per le riunioni sensibili](configure-lobby-sensitive-meetings.md)

## <a name="related-topics"></a>Argomenti correlati

[Illustrazioni di Microsoft Cloud per architetti aziendali](/microsoft-365/solutions/cloud-architecture-models)

[Usare le etichette di riservatezza per proteggere gli elementi del calendario, le riunioni e le chat di Teams](/microsoft-365/compliance/sensitivity-labels-meetings)
