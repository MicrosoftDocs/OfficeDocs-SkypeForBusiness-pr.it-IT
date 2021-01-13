---
title: Configurazione della versione client creare nuovi o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client. La configurazione globale della versione client viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso. È possibile disabilitare la configurazione della versione client globale se non si desidera che venga eseguito alcun controllo della versione client.
ms.openlocfilehash: 5567a4de26d29413c049126b90c907383916d71c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800506"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configurazione delle versioni client: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client. La configurazione globale della versione client viene installata con Skype for Business Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso. È possibile disabilitare la configurazione della versione client globale se non si desidera che venga eseguito alcun controllo della versione client.

È inoltre possibile creare configurazioni di versione client specifiche del sito, che consentono di abilitare o disabilitare il controllo della versione client per sito. Le configurazioni specifiche del sito hanno la precedenza sulla configurazione globale.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome della configurazione della versione client.

- Abilitare o disabilitare il controllo della versione client a livello globale o per il sito specifico.

- Aggiungere o modificare l'azione predefinita per la configurazione della versione client.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (globale o sito) della configurazione della versione client.

- **Nome** È possibile aggiungere o modificare il nome della configurazione della versione client.

- **Abilitare il controllo delle versioni** È possibile abilitare o disabilitare il controllo della versione client a livello globale o per il sito, a seconda dell'ambito della configurazione.

- **Azione predefinita** È possibile selezionare l'azione predefinita che verrà applicata quando un utente tenta di eseguire l'accesso utilizzando un'applicazione client per la quale non sono previsti criteri di versione client specifici. Sono disponibili le opzioni seguenti:

  - **Consenti** Consente al client di eseguire l'accesso se la versione del client non corrisponde ad alcun filtro nell'elenco dei criteri versione client.

  - **Blocca** Impedisce l'accesso del client se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client.

  - **Blocca con URL** Impedisce al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.

  - **Consenti con URL** Consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei criteri versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.

  - **URL** Se è stata selezionata l'opzione **blocca con URL** o **Consenti con URL**, è possibile specificare l'URL di download del client da includere nel messaggio di errore.

Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.

