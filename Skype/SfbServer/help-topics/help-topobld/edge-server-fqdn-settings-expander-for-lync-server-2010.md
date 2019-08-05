---
title: Expander (FQDN) delle impostazioni di Edge Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Per definire le proprietà in impostazioni esterne, configurare le operazioni seguenti:'
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189551"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expander (FQDN) delle impostazioni di Edge Server per Lync Server 2010
 
Per definire le proprietà in **impostazioni esterne**, configurare le operazioni seguenti:
  
Selezionare la casella di controllo **attiva FQDN separato e indirizzo IP per le conferenze Web e a/V** se si vuole definire il nome di dominio completo del pool e gli indirizzi IP per le conferenze Web e l'audio/video.
  
> [!NOTE]
> Se si sceglie di non selezionare la casella di controllo per nomi di dominio completi e indirizzi IP separati, è necessario fornire porte distinte per ognuno dei tre servizi forniti dall'Edge Server. L'unico nome di dominio completo che deve essere configurato è l'FQDN associato al servizio Access Edge. 
  
Selezionare la casella di controllo **a/v Edge è abilitata per NAT** se si vuole che l'a/v Edge service usi un indirizzo IP e la configurazione NAT (Network Address Translation).
  
Per i servizi Edge abilitati, è possibile digitare un **nome di dominio completo del pool** e una porta in **porte**
  
- Definisci il nome di dominio completo del pool di **servizi Access Edge** e una porta che identifica in modo univoco il servizio.
    
- Definire il nome di dominio completo del pool di **servizi Web Conferencing Edge** (se è selezionata l'opzione Abilita FQDN separato e indirizzo IP per le conferenze Web e a/V non è selezionato) e una porta che identifica in modo univoco il servizio.
    
- Definire il nome di dominio completo del pool **di servizi a/v Edge** (se è selezionata l'opzione Abilita FQDN separato e indirizzo IP per le conferenze Web e a/v) e una porta che identifica in modo univoco il servizio.
    
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

