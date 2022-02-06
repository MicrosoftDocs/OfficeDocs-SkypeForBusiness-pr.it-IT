---
title: Configurazione guidata certificati
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: 'NOINDEX, NOFOLLOW'
description: "Per\_richiedere,\_assegnare,\_rimuovere o\_visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati. A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins. Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi. Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le eventuali appartenenze ai gruppi aggiuntive necessarie. Durante l'attività Richiesta, è possibile immettere credenziali alternative che verranno utilizzate per richiedere il certificato all'autorità di certificazione emittente dell'infrastruttura a chiave pubblica."
---

# <a name="certificate-wizard"></a>Configurazione guidata certificati
 
Per **** richiedere,**** assegnare,**** rimuovere o **** visualizzare i certificati, è possibile utilizzare la Configurazione guidata certificati. A tale scopo, è necessario essere connessi come membri del gruppo RTCUniversalServerAdmins. Per richiedere un certificato a un'Autorità di certificazione (CA) pubblica, non è necessario appartenere ad altri gruppi. Per richiedere un certificato dall'infrastruttura a chiave pubblica (PKI) dell'organizzazione, è necessario confermare le eventuali appartenenze ai gruppi aggiuntive necessarie. Durante l'attività Richiesta, è possibile immettere credenziali alternative che verranno utilizzate per richiedere il certificato all'autorità di certificazione emittente dell'infrastruttura a chiave pubblica.
  
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
> **Importa certificato** in genere viene utilizzato per elaborare un certificato ricevuto mediante un processo diverso da una richiesta della Configurazione guidata certificati. Si supponga ad esempio che l'amministratore dell'infrastruttura a chiave pubblica (PKI) crei un certificato e lo renda disponibile. Utilizzare **Importa certificato** per importare il certificato nell'archivio certificati del computer e renderlo disponibile Skype for Business Server da assegnare.
  
Per completare il processo di richiesta di un certificato a una CA della propria organizzazione per cui è necessaria l'approvazione dell'amministratore CA, fare clic su **Elabora certificati in sospeso**. Per la richiesta del certificato verrà restituito lo stato In sospeso e verrà visualizzato il numero di identificazione. Per proseguire con l'elaborazione di un certificato con stato In sospeso, fare clic su **Aggiorna** per abilitare il pulsante **Elabora certificati in sospeso**. Tale pulsante **** non sarà più visualizzato in grigio. È quindi possibile tentare di recuperare la richiesta in sospeso, ma lo stato resterà invariato finché il certificato non verrà emesso o rifiutato dall'amministratore CA. Il pulsante non sarà disponibile se non vi sono richieste in sospeso valide, create dalla Configurazione guidata certificati.
  

