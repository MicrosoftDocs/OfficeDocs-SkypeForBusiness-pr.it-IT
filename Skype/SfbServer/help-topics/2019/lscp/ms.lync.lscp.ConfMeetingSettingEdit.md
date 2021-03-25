---
title: Configurazione riunione Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dagli utenti. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano alle riunioni ad hoc create facendo clic sull'opzione Riunione ora nel client.
ms.openlocfilehash: 3d37b1894531a62f605f083cbe1e2f36953f2ff2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121130"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configurazione riunione: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dagli utenti. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano alle riunioni ad hoc create facendo clic sull'opzione **Riunione** ora nel client.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito della configurazione di riunione che si sta creando o modificando: globale, sito o pool.

- **Nome** Le configurazioni riunione sono denominate per impostazione predefinita e il nome non può essere modificato.

- **I chiamanti PSTN ignorano la sala di attesa** Selezionare questa casella di controllo per ammettere automaticamente gli utenti che stanno componendo la conferenza tramite una linea telefonica PSTN (Public Switched Telephone Network). Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.

- **Designare come relatore** Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando aderiscono a una conferenza. Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza. Le opzioni sono:

  - **Nessuno** Selezionare questa opzione se nessuno diverso dall'organizzatore viene designato automaticamente come relatore.

  - **Società** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.

  - **Tutti** Selezionare questa opzione per designare automaticamente chiunque come relatore.

- **Tipo di conferenza assegnato per impostazione predefinita** Questa impostazione controlla se il componente aggiuntivo per conferenze di Outlook pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le conferenze pianificate hanno sempre lo stesso URL di partecipazione e le stesse informazioni audio. Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione. Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.

- **Ammetti utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se gli utenti anonimi (ovvero non autenticati) sono autorizzati a partecipare alle conferenze per impostazione predefinita. Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.

- **URL logo** Digitare l'URL con l'immagine da utilizzare per gli inviti a conferenze personalizzati.

- **URL guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per partecipare alla conferenza.

- **URL testo legale** Digitare l'URL di un sito Web con le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.

- **Testo piè di pagina personalizzato** Digitare il testo da utilizzare per gli inviti a conferenze personalizzati.

Per informazioni dettagliate sull'utilizzo di configurazioni riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) nella documentazione relativa alle operazioni. Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) nella documentazione relativa alla pianificazione.