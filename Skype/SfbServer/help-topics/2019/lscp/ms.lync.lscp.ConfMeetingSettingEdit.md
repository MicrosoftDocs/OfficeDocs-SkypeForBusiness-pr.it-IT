---
title: Configurazione della riunione creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Le impostazioni di configurazione della riunione definiscono l'esperienza di partecipazione dell'utente per le conferenze pianificate dagli utenti. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano invece alle riunioni ad hoc create facendo clic sull'opzione Riunione immediata nel client.
ms.openlocfilehash: 002550fadb845a15178567a62ad3189df7d652ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195148"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configurazione riunione: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti alle conferenze pianificate. Queste impostazioni riguardano solo le riunioni pianificate e non quelle ad hoc create facendo clic sull'opzione **Riunione immediata** nel client.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito della configurazione della riunione che si sta creando o modificando: globale, sito o pool.

- **Nome** Le configurazioni delle riunioni sono denominate per impostazione predefinita e il nome non può essere modificato.

- **Ingresso di bypass** per i chiamanti PSTN Selezionare questa casella di controllo per ammettere automaticamente gli utenti che effettuano la chiamata alla conferenza tramite una linea telefonica pubblica con Switched Telephone Network (PSTN). Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.

- **Designa come** relatore Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando partecipano a una conferenza. Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza. Le opzioni sono:

  - **Nessuno** Selezionare questa opzione se non si vuole che l'organizzatore venga indicato automaticamente come relatore.

  - **Società** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.

  - **Tutti gli utenti** Selezionare questa opzione per designare automaticamente tutti gli utenti come relatori.

- **Tipo di conferenza assegnata per impostazione predefinita** Questa impostazione controlla se Outlook Conferencing AddIn Pianifica sempre le conferenze tramite la conferenza assegnata dell'organizzatore, in modo che le conferenze pianificate abbiano sempre lo stesso URL di join e informazioni audio. Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione. Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.

- **Ammettere gli utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se gli utenti anonimi, ovvero non autenticati, sono autorizzati a partecipare alle conferenze per impostazione predefinita. Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.

- **URL del logo** Digitare l'URL che contiene l'immagine da usare per gli inviti alle conferenze personalizzate.

- **URL della Guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per partecipare alla conferenza.

- **URL di testo legale** Digitare l'URL di un sito Web che contiene le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.

- **Testo del piè** di pagina personalizzato Digitare il testo da usare per gli inviti alle conferenze personalizzati.

Per informazioni dettagliate sulle configurazioni delle riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) nella documentazione relativa alle operazioni. Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) nella documentazione relativa alla pianificazione.


