---
title: Configurazione versione client Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri delle versioni client in vigore avranno effetto quando gli utenti tenteranno di accedere. È possibile disabilitare la configurazione della versione client globale se non si desidera che si verifichi alcun controllo della versione client.
ms.openlocfilehash: 5dd3f1297ec618346a35424ca323d236b8527c62
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752315"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configurazione delle versioni client: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri delle versioni client in vigore avranno effetto quando gli utenti tenteranno di accedere. È possibile disabilitare la configurazione della versione client globale se non si desidera che si verifichi alcun controllo della versione client.

È inoltre possibile creare configurazioni di versione client specifiche del sito, consentendo di abilitare o disabilitare il controllo della versione client in base al sito. Le configurazioni specifiche del sito hanno la precedenza sulla configurazione globale.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome della configurazione della versione client.

- Abilitare o disabilitare il controllo della versione client a livello globale o per il sito specifico.

- Aggiungere o modificare l'azione predefinita per la configurazione della versione client.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (Globale o Sito) della configurazione della versione client.

- **Nome** È possibile aggiungere o modificare il nome della configurazione della versione client.

- **Abilitare il controllo della versione** È possibile abilitare o disabilitare il controllo della versione client a livello globale o per il sito, a seconda dell'ambito della configurazione.

- **Azione predefinita** È possibile selezionare l'azione predefinita che verrà applicata quando un utente tenta di accedere utilizzando un'applicazione client per la quale non sono disponibili criteri specifici per la versione client. Sono disponibili le opzioni seguenti:

  - **Consenti** Consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri della versione client.

  - **Blocco** Impedisce al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri della versione client.

  - **Blocca con URL** Impedisce al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.

  - **Consenti con URL** Consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.

  - **URL** Se è stato **selezionato Blocca con URL** o Consenti con **URL**, è possibile specificare l'URL di download del client da includere nel messaggio di errore.

Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) nella documentazione relativa alle operazioni.