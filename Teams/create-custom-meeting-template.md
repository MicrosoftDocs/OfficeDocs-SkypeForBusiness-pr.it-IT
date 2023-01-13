---
title: Creare un modello di riunione personalizzato in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
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
description: Informazioni su come gli amministratori di Microsoft Teams possono creare un modello di riunione personalizzato per impostare o applicare le impostazioni dell'organizzatore della riunione per una maggiore sicurezza e conformità delle riunioni.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800271"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Creare un modello di riunione personalizzato in Microsoft Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

I modelli di riunione personalizzati di Microsoft Teams (una funzionalità di Teams Premium) consentono di specificare valori per molte delle impostazioni della riunione disponibili per gli organizzatori della riunione. I modelli possono configurare le impostazioni che gli organizzatori delle riunioni possono modificare o bloccare in modo che gli organizzatori delle riunioni non possano modificarle. Per altre informazioni sui modelli di riunione personalizzati, vedere [Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md).

È possibile creare fino a 50 modelli personalizzati. Vedere [Gestire i modelli di riunione in Microsoft Teams](manage-meeting-templates.md) per informazioni su come gestire i modelli disponibili per gli utenti.

Per ogni opzione del modello, è possibile definire quanto segue:

- **Valore predefinito** : valore applicato a una riunione quando si usa il modello.
- **Visibile** : determina se l'organizzatore della riunione può visualizzare questa impostazione nelle opzioni della riunione. 
- **Stato blocco** : determina se l'organizzatore della riunione può modificare l'impostazione impostata dal modello. Se l'impostazione è bloccata, l'organizzatore della riunione non può modificarla.

Per creare un modello di riunione personalizzato

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Modelli di riunione**.
1. Seleziona **Aggiungi**
1. Digitare un nome e una descrizione per il modello.
1. Scegliere le impostazioni da usare per il modello. Vedere le sezioni seguenti per le descrizioni di ogni impostazione.
1. Per impedire all'organizzatore della riunione di modificare un'impostazione, selezionarla e quindi selezionare **Blocca**.
1. Per impedire all'organizzatore della riunione di visualizzare un'impostazione, selezionarla e quindi scegliere **Nascondi**.
1. Selezionare **Salva**.

Dopo la creazione, la disponibilità del modello agli utenti può richiedere fino a 24 ore.

#### <a name="security"></a>Sicurezza

|Impostazione|Descrizione|
|:------|:----------|
|Etichetta di riservatezza|Specifica l'etichetta di riservatezza della riunione da usare per la riunione. Si noti che l'etichetta di riservatezza potrebbe ignorare determinate impostazioni nel modello.|
|Chi può evitare la sala d'attesa?|Specifica chi può ignorare la sala di attesa e partecipare direttamente alla riunione.|
|Persone chiamata in ingresso può ignorare la sala di attesa|Specifica se le persone che accedono tramite telefono possono ignorare la sala di attesa e partecipare direttamente alla riunione.|
|Inviare una notifica quando i chiamanti si uniscono e abbandonano|Specificare se si vuole riprodurre un suono quando le persone che chiamano tramite telefono accedono o abbandonano la riunione.|
|Abilitare la crittografia end-to-end delle riunioni|Specificare se si vuole che la riunione usi la crittografia end-to-end. La registrazione e la trascrizione non funzioneranno se è attivata.|
|Applicare una filigrana al contenuto condiviso|Specifica se una filigrana è sovrapposta al contenuto condiviso sullo schermo nella riunione.|
|Applicare una filigrana al feed video di tutti gli utenti|Specifica se una filigrana è sovrapposta ai feed video dei partecipanti alla riunione.|

#### <a name="audio-and-video"></a>Audio e video

|Impostazione|Descrizione|
|:------|:----------|
|Consentire il microfono per i partecipanti|Quando **è attivato**, i partecipanti possono riattivare l'audio.|
|Consentire la fotocamera per i partecipanti|Quando **l'opzione è attivata**, i partecipanti possono attivare le videocamere.|

#### <a name="recording-and-transcription"></a>Registrazione e trascrizione

|Impostazione|Descrizione|
|:------|:----------|
|Registrare le riunioni automaticamente|Quando **Le** riunioni vengono registrate automaticamente.|
|Chi può registrare le riunioni?|Specifica se le riunioni possono essere registrate solo dagli organizzatori o da organizzatori e relatori.|

#### <a name="meeting-engagement"></a>Coinvolgimento della riunione

|Impostazione|Descrizione|
|:------|:----------|
|I partecipanti possono chattare|Specifica se la chat della riunione è disponibile. Può essere usato anche per impedire la chat prima e dopo la riunione.|
|I partecipanti possono usare le reazioni|Specifica se i partecipanti possono usare le reazioni nella riunione. Questo deve essere **attivata** per il funzionamento della funzione alzata.|
|Abilita Q&A|Specifica se i partecipanti possono usare la caratteristica Q&A per porre domande durante la riunione.|
|Gestire ciò che i partecipanti vedono|Quando **l'opzione è attivata**, gli organizzatori della riunione possono visualizzare in anteprima e approvare il contenuto condiviso sullo schermo prima che gli altri partecipanti possano vederlo.|

## <a name="related-topics"></a>Argomenti correlati

[Panoramica dei modelli di riunione personalizzati in Microsoft Teams](custom-meeting-templates-overview.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme](meeting-templates-sensitivity-labels-policies.md)

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)
