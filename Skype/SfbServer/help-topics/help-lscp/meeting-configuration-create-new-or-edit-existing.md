---
title: Configurazione della riunione creare nuovi o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dall'utente. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano a riunioni ad-hoc create facendo clic sull'opzione Meet Now nel client.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803936"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configurazione riunione: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione delle riunioni definiscono l'esperienza di partecipazione degli utenti per le conferenze pianificate dall'utente. Queste impostazioni si applicano solo alle riunioni pianificate. Non si applicano a riunioni ad-hoc create facendo clic sull'opzione **Meet Now** nel client.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Ambito** Identifica l'ambito della configurazione della riunione che si sta creando o modificando: globale, sito o pool.

- **Nome** Le configurazioni delle riunioni sono denominate per impostazione predefinita e il nome non può essere modificato.

- **Lobby di bypass per i chiamanti PSTN** Selezionare questa casella di controllo per consentire l'accesso automatico agli utenti che eseguono la chiamata alla conferenza tramite una linea telefonica PSTN (Public Switched Telephone Network). Deselezionare la casella di controllo per instradare i chiamanti PSTN alla sala di attesa della conferenza, dove rimangono in attesa fino a quando un relatore non concede loro l'accesso alla conferenza.

- **Designa come relatore** Selezionare la categoria di utenti (oltre all'organizzatore della riunione) che vengono automaticamente designati come relatori quando partecipano a una conferenza. Indipendentemente da questa impostazione, i relatori possono essere designati in modo esplicito come tali quando viene pianificata la conferenza oppure possono essere promossi in modo esplicito a relatori durante la conferenza. Le opzioni sono:

  - **Nessuna** Selezionare questa opzione se nessun altro è definito automaticamente come relatore.

  - **Azienda** Selezionare questa opzione per designare automaticamente solo i membri dell'organizzazione come relatori.

  - **Tutti gli utenti** Selezionare questa opzione per designare automaticamente tutti i relatori.

- **Tipo di conferenza assegnato per impostazione predefinita** Questa impostazione consente di controllare se Outlook Conferencing AddIn Pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le conferenze pianificate hanno sempre lo stesso URL di join e le stesse informazioni audio. Selezionare questa casella di controllo per fare in modo che le conferenze pianificate usino sempre lo stesso URL per la partecipazione. Deselezionare la casella di controllo per usare un URL per la partecipazione diverso per ogni conferenza.

- **Ammetti gli utenti anonimi per impostazione predefinita** Selezionare questa casella di controllo se agli utenti anonimi, ovvero non autenticati, sono consentiti di partecipare a conferenze per impostazione predefinita. Deselezionare la casella di controllo se, per impostazione predefinita, agli utenti anonimi non è consentito partecipare alle conferenze.

- **URL logo** Digitare l'URL che contiene l'immagine da utilizzare per gli inviti alla conferenza personalizzati.

- **URL della Guida** Digitare l'URL di un sito Web in cui gli utenti possono ottenere assistenza per la partecipazione alla conferenza.

- **URL di testo legale** Digitare l'URL di un sito Web contenente le informazioni legali e le dichiarazioni di non responsabilità per la conferenza.

- **Testo del piè** di pagina personalizzato Digitare il testo da utilizzare per gli inviti alla conferenza personalizzati.

Per informazioni dettagliate sull'utilizzo di configurazioni riunioni, vedere [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) nella documentazione relativa alle operazioni. Per informazioni dettagliate sull'impostazione delle configurazioni per riunioni di grandi dimensioni, vedere [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) nella documentazione relativa alla pianificazione.


