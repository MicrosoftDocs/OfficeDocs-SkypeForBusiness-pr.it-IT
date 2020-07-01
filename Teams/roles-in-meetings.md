---
title: Funzionalità per relatori e partecipanti in una riunione di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sulle funzionalità disponibili per relatori e partecipanti una riunione di Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0302a5c1f09e6ed6bfbb877709ed3562ce1440a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938175"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Funzionalità per relatori e partecipanti in una riunione di Teams
======================================================

Le riunioni di Microsoft Teams supportano molti tipi di partecipanti. I partecipanti possono accedere a varie funzionalità per le riunioni in base ai ruoli che rivestono all'interno o all'esterno dell'organizzazione.

Le funzionalità per riunioni disponibili sono:

- Chat (include foto e adesivi)
- Note riunione
- Whiteboard
- Registrazione
- File
    - condivisione di file nella chat di una riunione e visualizzazione/download di file dalla chat di una riunione
    - presentazione di un file PPT in una riunione (non tramite condivisione dello schermo) e visualizzazione di un file PPT in una riunione
- Pianificare una riunione (solo per le riunioni)

Questo articolo descrive le funzionalità per i partecipanti e il rispettivo accesso alle funzionalità per le riunioni.

## <a name="presenters-and-organizers"></a>Relatori e organizzatori

Relatori e organizzatori includono:

- Relatori dell'organizzazione
- Relatori di altre organizzazioni, inclusi i partecipanti anonimi ed esterni. I relatori sono designati dall'organizzatore e hanno bisogno di un invito personale da parte dell'organizzatore.

Relatori e organizzatori hanno accesso a tutte le funzionalità di una riunione o di un evento live.

## <a name="participants"></a>Partecipanti

I partecipanti alla riunione possono essere di diversi tipi:

- [Partecipante interno al tenant](#in-tenant-participant)
- [Partecipante guest](#guest-participant)
- [Partecipante esterno (federato)](#external-federated-participant)
- [Partecipante anonimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Partecipante interno al tenant

Il partecipante interno al tenant appartiene all'organizzazione e dispone delle credenziali per il tenant. Altre informazioni su questo partecipante sono disponibili in [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | Sì | Sì | Sì |
| Note riunione | Sì | Sì |Sì |
| Whiteboard | Sì | Sì |Sì |
| Registrazione | N/D |Sì | Sì |
| File - Condivisione di file nella chat di una riunione e visualizzazione/download di file dalla chat di una riunione | Sì | Sì | Sì |
| File - Presentazione di un file PPT in una riunione (non tramite condivisione dello schermo) e visualizzazione di un file PPT in una riunione | Sì | Sì | Sì |
| Pianificare una riunione | Sì | N/D | N/D |
|||||||

### <a name="guest-participant"></a>Partecipante guest

Un partecipante guest è una persona di un'altra organizzazione che è stata invitata ad accedere a Teams o ad altre risorse nel tenant dell'organizzazione in base alla piattaforma B2B di Azure Active Directory. Gli utenti guest possono essere invitati a partecipare alle normali riunioni e alle riunioni di canale. Altre informazioni sui partecipanti guest sono disponibili in [Com'è l'esperienza guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | Sì | Sì | Sì |
| Note riunione | Sì | Sì | Sì |
| Whiteboard | No | No |No |
| Registrazione | N/D |No | No |
| File - Condivisione di file nella chat di una riunione e visualizzazione/download di file dalla chat di una riunione | Sì | Sì | Sì |
| File - Presentazione di un file PPT in una riunione (non tramite condivisione dello schermo) e visualizzazione di un file PPT in una riunione | Sì | Sì | Sì |
| Pianificare una riunione | No | N/D | N/D |
|||||||

### <a name="external-federated-participant"></a>Partecipante esterno (federato)

Un partecipante esterno è un utente che usa Teams in un'altra organizzazione, che è stato invitato a partecipare a una riunione, ma non ha accesso ad altre risorse condivise dell'organizzazione. I partecipanti esterni vengono mostrati nell'elenco dei partecipanti alla riunione con il nome identità che usano nella propria organizzazione. Altre informazioni sui partecipanti esterni sono disponibili in [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md#external-access).

|  ||
|-|-|-|
| **Funzionalità** |||
| Chat | Sì |
| Note riunione | N/D |  
| Whiteboard | N/D |
| Registrazione | N/D |  
| File - Condivisione di file nella chat di una riunione e visualizzazione/download di file dalla chat di una riunione |  |  |  |
| File - Presentazione di un file PPT in una riunione (non tramite condivisione dello schermo) e visualizzazione di un file PPT in una riunione |  |  |  |
| Pianificare una riunione | N/D |
|||

### <a name="anonymous-participant"></a>Partecipante anonimo

Il partecipante anonimo è simile a un utente esterno, ma la sua identità non viene rivelata nella riunione. Nel momento in cui entra nella riunione, immette manualmente un nickname. Altre informazioni sui partecipanti anonimi sono disponibili in [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

|   | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D | Sì | N/D |
| Note riunione | N/D | No | N/D |
| Whiteboard | N/D | No | N/D |
| Registrazione | N/D | No | N/D |
| File - Condivisione di file nella chat di una riunione e visualizzazione/download di file dalla chat di una riunione |  |  |  |
| File - Presentazione di un file PPT in una riunione (non tramite condivisione dello schermo) e visualizzazione di un file PPT in una riunione |  |  |  |
| Pianificare una riunione | N/D | N/D | N/D |
|||||||

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza e Microsoft Teams](teams-security-guide.md)

[Accesso guest in Teams](guest-access.md)
