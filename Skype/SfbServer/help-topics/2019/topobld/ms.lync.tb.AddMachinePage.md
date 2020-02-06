---
title: Aggiungere server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per aggiungere un nuovo server a un pool di server esistente, in cui il pool è uno dei seguenti:'
ms.openlocfilehash: c3593835fa1204b5ed4e74729a7ec369069e04f8
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798503"
---
# <a name="add-server"></a>Aggiungere server
 
Per aggiungere un nuovo server a un pool di server esistente, in cui il pool è uno dei seguenti:
  
- Server front-end Enterprise Edition
    
- Server Director
    
- Mediation Server
    
- Server di conferenza audio/video
    
- Server applicazioni attendibile
    
Ogni nuovo server del pool ha requisiti diversi. Nelle sezioni seguenti individuare il tipo di server che si sta aggiungendo al pool esistente e fornire le informazioni richieste come definito per ogni tipo di server. Fornisci le informazioni richieste per definire il nuovo server del pool.
  
 **Server front-end Enterprise Edition**
  
- Nome di dominio completo (FQDN) del nuovo server come definito in Domain Name System (DNS).
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo specifico nel nuovo server. L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.
    
- Definire un **indirizzo IP PSTN** quando un Mediation Server è collocato nel server front-end.
    
- Selezionare **Abilita IPv6** per abilitare IPv6 per il server.
    
  **Server Director**
  
- Il nome di dominio completo del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, il che significa che verrà usato qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo IP specifico nel nuovo server. L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.
    
  **Mediation Server**
  
- Il nome di dominio completo del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo IP specifico nel nuovo server come indirizzo IP principale e immettere un indirizzo IP per l'indirizzo IP PSTN (Public Switched Telephone Network). Gli indirizzi IP immessi sono l'unico indirizzo IP che risponderà per i servizi designati.
    
    > [!NOTE]
    > Per il Mediation Server, l'indirizzo IP immesso per l'indirizzo IP principale e l'indirizzo IP PSTN è lo stesso per impostazione predefinita. Gli indirizzi IP possono essere definiti separatamente se si usano interfacce di rete dedicate o indirizzi IP separati nella stessa interfaccia di rete. Se si dispone di due interfacce di rete, una per la connessione di rete locale e una per la connessione PSTN, è necessario assegnare indirizzi IP diversi. 
  
  **Server di conferenza audio/video**
  
- Il nome di dominio completo del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo specifico nel nuovo server. L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.
    
  **Server applicazioni attendibile**
  
- Il nome di dominio completo del nuovo server come definito in DNS.
    

