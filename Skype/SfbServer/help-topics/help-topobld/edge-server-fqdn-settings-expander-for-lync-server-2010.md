---
title: Espansione delle impostazioni del nome di dominio completo (FQDN) del server perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Per definire le proprietà in impostazioni esterne, configurare le operazioni seguenti:'
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684759"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del nome di dominio completo (FQDN) del server perimetrale per Lync Server 2010
 
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
  

