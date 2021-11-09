---
title: Aggiungere un server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Per aggiungere un nuovo server a un pool di server esistente di uno dei tipi seguenti:'
ms.openlocfilehash: dc09530eec1b46fd6ab357997a6c4d8be8860016
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860353"
---
# <a name="add-server"></a>Aggiungere server
 
Per aggiungere un nuovo server a un pool di server esistente di uno dei tipi seguenti:
  
- Enterprise Edition Front End Server
    
- Server Director
    
- Mediation Server
    
- Audio/Video Conferencing Server
    
- Server applicazioni attendibili
    
Ognuno dei nuovi server del pool ha requisiti diversi. Nelle sezioni riportate di seguito individuare il tipo di server che si intende aggiungere al pool esistente e specificare le informazioni richieste per il tipo di server in questione. È necessario fornire le informazioni richieste per definire il nuovo server del pool.
  
 **Enterprise Edition Front End Server**
  
- Nome di dominio completo (FQDN) del nuovo server come definito in DNS (Domain Name System).
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere utilizzato qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.
    
- Definire un **Indirizzo IP PSTN** quando un Mediation Server è collocato nel Front End Server.
    
- Selezionare **Abilita IPv6** per abilitare IPv6 per questo server.
    
  **Server Director**
  
- FQDN del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere usato qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo IP specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.
    
  **Mediation Server**
  
- FQDN del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere utilizzato qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo IP specifico per il nuovo server come indirizzo IP primario e immettere un indirizzo IP come indirizzo IP PSTN (Public Switched Telephone Network). Gli indirizzi IP immessi saranno gli unici a rispondere per i servizi designati.
    
    > [!NOTE]
    > Per il Mediation Server, l'indirizzo IP immesso come indirizzo IP primario e l'indirizzo IP PSTN sono uguali per impostazione predefinita. Gli indirizzi IP possono essere definiti separatamente se si usano interfacce di rete dedicate o indirizzi IP diversi nella stessa interfaccia di rete. Se si dispone di due interfacce di rete, una per la connessione di rete locale e l'altra per la connessione PSTN, sarà necessario assegnare indirizzi IP diversi. 
  
  **Audio/Video Conferencing Server**
  
- FQDN del nuovo server come definito in DNS.
    
- Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere usato qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.
    
  **Server applicazioni attendibili**
  
- FQDN del nuovo server come definito in DNS.
    

