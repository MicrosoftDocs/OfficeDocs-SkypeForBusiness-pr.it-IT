---
title: Configurazione della versione client crea nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Skype for Business Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Se la configurazione globale è abilitata, tutti i criteri relativi alla versione client disponibili verranno applicati quando gli utenti tentano l'accesso. Se non si desidera che venga eseguito il controllo della versione client, è possibile disabilitare la configurazione globale della versione client.
ms.openlocfilehash: 1a42f2a355ead1d98e7e8031b43db879f271dced
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195123"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configurazione versione client: crearne una nuova o modificarne una esistente

Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Skype for Business Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. Se la configurazione globale è abilitata, tutti i criteri relativi alla versione client disponibili verranno applicati quando gli utenti tentano l'accesso. Se non si desidera che venga eseguito il controllo della versione client, è possibile disabilitare la configurazione globale della versione client.

È inoltre possibile creare configurazioni della versione client specifiche di sito, per poter abilitare o disabilitare il controllo della versione client in base al sito. Le configurazioni specifiche di sito hanno la precedenza sulla configurazione globale.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Nuova configurazione versione client** o **Modifica configurazione versione client** è possibile eseguire le attività seguenti:

- Aggiungere o modificare il nome della configurazione della versione client.

- Abilitare o disabilitare il controllo della versione client a livello globale o in base al sito.

- Aggiungere o modificare l'azione predefinita per la configurazione della versione client.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (globale o sito) della configurazione della versione client.

- **Nome** È possibile aggiungere o modificare il nome della configurazione della versione client.

- **Abilitare il controllo della versione** È possibile abilitare o disabilitare il controllo della versione client a livello globale o per il sito, a seconda dell'ambito della configurazione.

- **Azione predefinita** Puoi selezionare l'azione predefinita che verrà applicata quando un utente tenta di accedere usando un'applicazione client per cui non esistono criteri di versione client specifici. Le opzioni disponibili sono le seguenti:

  - **Consenti** Consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client.

  - **Blocco** Impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client.

  - **Blocco con URL** Impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.

  - **Consenti con URL** Consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei criteri di versione client e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.

  - **URL** Se è stato selezionato **blocca con URL** o **Consenti con URL**, è possibile specificare l'URL di download del client da includere nel messaggio di errore.

Per informazioni dettagliate su interoperabilità tra client e versioni client, vedere [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso delle configurazioni delle versioni client, vedere [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) nella documentazione relativa alle operazioni.

