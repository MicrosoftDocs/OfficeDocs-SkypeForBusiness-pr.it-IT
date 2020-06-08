---
title: Funzionalità per relatori e partecipanti in un evento live di Teams
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
description: Informazioni sulle funzionalità disponibili per relatori e partecipanti in un evento live di Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 7714442be770420797df1c51a532f769eb0350a4
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565859"
---
<a name="presenter-and-participant-capabilities-in-a-teams-live-event"></a>Funzionalità per relatori e partecipanti in un evento live di Teams
======================================================

Gli eventi live di Microsoft Teams supportano molti tipi di partecipanti. I partecipanti possono accedere a varie funzionalità per gli eventi live in base ai ruoli che rivestono all'interno o all'esterno dell'organizzazione.

Le funzionalità per riunioni disponibili sono:

- Chat (include foto e adesivi)
- Note riunione
- Whiteboard
- Registrazione
- File

Questo articolo descrive le funzionalità per i partecipanti e il rispettivo accesso alle funzionalità per gli eventi live.

## <a name="presenters-and-organizers"></a>Relatori e organizzatori

Relatori e organizzatori includono:

- Relatori dell'organizzazione
- Relatori di altre organizzazioni. I relatori sono designati dall'organizzatore e hanno bisogno di un invito personale da parte dell'organizzatore.

Relatori e organizzatori hanno accesso a tutte le funzionalità di un evento live.

## <a name="participants"></a>Partecipanti

I partecipanti alla riunione possono essere di diversi tipi:

- [Partecipante interno al tenant](#in-tenant-participant)
- [Partecipante guest](#guest-participant)
- [Partecipante esterno (federato)](#external-federated-participant)
- [Partecipante anonimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Partecipante interno al tenant

Il partecipante interno al tenant appartiene all'organizzazione e dispone delle credenziali per il tenant. Altre informazioni su questo partecipante sono disponibili in [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

| Evento live |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Funzionalità**       | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D | N/D | N/D |
| Note riunione | Sì | Sì |Sì |
| Whiteboard | Sì | Sì |Sì |
| Registrazione | N/D |Sì | Sì |
| File | Sì | Sì | Sì |
|||||||


### <a name="guest-participant"></a>Partecipante guest

Un partecipante guest è una persona di un'altra organizzazione che è stata invitata ad accedere a Teams o ad altre risorse nel tenant dell'organizzazione in base alla piattaforma B2B di Azure Active Directory. Gli utenti guest possono essere invitati a partecipare alle normali riunioni e alle riunioni di canale. Altre informazioni sui partecipanti guest sono disponibili in [Com'è l'esperienza guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Evento live  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D | N/D | N/D |
| Note riunione | Sì | Sì | Sì |
| Whiteboard | No | No | No |
| Registrazione | N/D | No | No |
| File | No | No | No |
|||||||


### <a name="external-federated-participant"></a>Partecipante esterno (federato)

Un partecipante esterno è un utente che usa Teams in un'altra organizzazione, che è stato invitato a partecipare a una riunione, ma non ha accesso ad altre risorse condivise dell'organizzazione. I partecipanti esterni vengono mostrati nell'elenco dei partecipanti alla riunione con il nome identità che usano nella propria organizzazione. Altre informazioni sui partecipanti esterni sono disponibili in [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md#external-access).

| Evento live |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
|  **Funzionalità**         | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D| N/D | N/D |
| Note riunione | No | No | No |
| Whiteboard | No| No | No |
| Registrazione | N/D | No | No |
| File | Sì | Sì | Sì |
|||||||

### <a name="anonymous-participant"></a>Partecipante anonimo

Il partecipante anonimo è simile a un utente esterno, ma la sua identità non viene rivelata nella riunione. Nel momento in cui entra nella riunione, immette manualmente un nickname. Altre informazioni sui partecipanti anonimi sono disponibili in [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

| Evento live|  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D | N/D | N/D |
| Note riunione | N/D | No | N/D |
| Whiteboard | N/D | N/D | N/D |
| Registrazione | N/D | No | N/D |
| File | N/D | No | N/D |
|||||||


## <a name="related-topics"></a>Argomenti correlati

[Sicurezza e Microsoft Teams](teams-security-guide.md)

[Accesso guest in Teams](guest-access.md)

[Pianificare un evento live in Teams](teams-live-events/plan-for-teams-live-events.md)
