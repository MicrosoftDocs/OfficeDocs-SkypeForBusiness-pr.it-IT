---
title: Configurazione guidata certificati
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: Per richiedere, assegnare, rimuovere o visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati. A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins. Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi. Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le altre appartenenze ai gruppi di cui si ha bisogno. Durante l'attività di richiesta, è possibile immettere credenziali alternative che verranno usate per richiedere il certificato dalla CA emittente della PKI.
ms.openlocfilehash: 7bb6cd04687bab6cfad14a6f71a673adf06da4e7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705561"
---
# <a name="certificate-wizard"></a>Configurazione guidata certificati
 
Per **** richiedere, **** assegnare, **** rimuovere o **** visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati. A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins. Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi. Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le altre appartenenze ai gruppi di cui si ha bisogno. Durante l'attività di richiesta, è possibile immettere credenziali alternative che verranno usate per richiedere il certificato dalla CA emittente della PKI.
  
Per richiedere un nuovo certificato, fare clic su **Richiedi**.
  
Per assegnare un certificato non ancora assegnato, fare clic su **Assegna**.
  
Per rimuovere un certificato precedentemente assegnato, fare clic su **Rimuovi**.
  
> [!NOTE]
> Il pulsante **Rimuovi** sarà disponibile solo se in precedenza è stato assegnato un certificato. Se il pulsante **Rimuovi** risulta non disponibile (in grigio), non vi sono certificati assegnati.
  
Per visualizzare un certificato assegnato, fare clic su **Visualizza**.
  
> [!NOTE]
> Il pulsante **Visualizza** sarà disponibile solo se in precedenza è stato assegnato un certificato. Se il pulsante **Visualizza** risulta non disponibile (in grigio), non vi sono certificati assegnati.
  
Per aggiornare la schermata con le assegnazioni correnti dei certificati, fare clic su **Aggiorna**.
  
Per importare un certificato non presente nell'archivio certificati, fare clic su **Importa certificato**.
  
> [!NOTE]
> **Importa certificato** in genere viene utilizzato per elaborare un certificato ricevuto mediante un processo diverso da una richiesta della Configurazione guidata certificati. Si supponga ad esempio che l'amministratore dell'infrastruttura a chiave pubblica (PKI) crei un certificato e lo renda disponibile. Usare il **certificato di importazione** per importare il certificato nell'archivio certificati del computer e renderlo disponibile per l'assegnazione a Skype for Business Server.
  
Per completare il processo di richiesta di un certificato a una CA della propria organizzazione per cui è necessaria l'approvazione dell'amministratore CA, fare clic su **Elabora certificati in sospeso**. Per la richiesta del certificato verrà restituito lo stato In sospeso e verrà visualizzato il numero di identificazione. Per proseguire con l'elaborazione di un certificato con stato In sospeso, fare clic su **Aggiorna** per abilitare il pulsante **Elabora certificati in sospeso**. Tale pulsante **** non sarà più visualizzato in grigio. È quindi possibile tentare di recuperare la richiesta in sospeso, ma lo stato resterà invariato finché il certificato non verrà emesso o rifiutato dall'amministratore CA. Il pulsante non sarà disponibile se non vi sono richieste in sospeso valide, create dalla Configurazione guidata certificati.
  

